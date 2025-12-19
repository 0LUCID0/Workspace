# 🏗️ BuildPali (AMWE) Architecture Specification v2.0

> **High-Performance, Async, Multi-Platform Voxel Engine**  
> **Single Source of Truth (SSOT)** — This document defines the canonical architecture, constraints, and operational rules.

본 명세서는 **BuildPali**가 마인크래프트의 버전 파편화(Legacy vs Modern)와 성능 한계를 극복하기 위해 채택한 **모듈 격리형 하이브리드 아키텍처**와 **개발/운영 규칙**을 정의합니다.

---

## 0. Definitions & Invariants (Non-Negotiables)

### 0.1 Invariants
- **API First**: 모든 기능 및 계약은 `api` 모듈의 인터페이스로 정의된다.
- **Logic Purity**: `core/logic` 및 `*/common` 계층은 **Minecraft/Loader 의존성이 0%**여야 한다. (단, `com.mojang:brigadier`는 예외)
- **Isolation by Version**: 버전별/로더별 플랫폼 구현은 **물리적으로 분리된 모듈**로 관리한다.
- **No MRJAR**: Multi-Release JAR 사용 금지. (운영 복잡도 및 충돌 위험 회피)
- **Dual-Support IDs**: 내부는 Canonical, 경계(Adapter)에서 Legacy 변환.

### 0.2 Glossary
- **Logic/Common**: 순수 Java 계층 (알고리즘/자료구조/도메인 로직).
- **Platform Module**: 특정 Minecraft 버전 + 특정 Loader에 종속되는 구현 (브릿지/어댑터/믹스인 포함).
- **Canonical ID**: Flattening 표준 ID 및 상태 표현 (예: `minecraft:oak_log[axis=y]`).
- **Legacy ID**: 숫자 기반 ID (예: `1:0`) — 경계에서만 사용.

---

## 1. Architecture Strategy: Module-per-Version (격리)

우리는 운영 난이도가 높은 MRJAR(Multi-Release JAR) 대신, 물리적인 **모듈 격리**를 통해 빌드 안정성과 유지보수성을 확보합니다.

- **Common-Logic (Java 8)**: 마인크래프트/로더 의존성이 없는 순수 알고리즘 계층.
- **Version-Specific Modules**: (예: `fabric-1.21.1`, `forge-1.12.2`) 각 버전의 매핑과 Java 요구사항에 맞춰 개별 컴파일.
- **Anti-MRJAR**: 버전별로 별도의 산출물을 배포하여 Mixin/Refmap 충돌 원천 차단.

---

## 2. Repository Layout (Authoritative)

> 디렉토리 및 모듈 이름은 자동화 스캐폴드 규약과 직결되므로, 아래 구조가 기준입니다.

```text
buildpali/
├─ docs/                          # 설계/스펙/자동화 문서
├─ api/                           # dev.buildpali.api (Java 8, no MC deps)
├─ core/
│  ├─ logic/                      # dev.buildpali.core.logic (Java 8, pure)
│  ├─ mod-fabric-1_21_1/          # Platform implementation (Java 21)
│  └─ mod-forge-1_12_2/           # Platform implementation (Java 8)
├─ gui/
│  ├─ common/
│  └─ mod-fabric-1_21_1/
├─ ai/
│  ├─ common/
│  └─ mod-fabric-1_21_1/
├─ 3dio/
│  ├─ common/
│  └─ mod-fabric-1_21_1/
├─ gradle/
│  └─ conventions/                # 공통 Gradle 로직 (logic-guard.gradle.kts 등)
├─ tools/
│  ├─ templates/                  # 모듈 생성 템플릿
│  └─ scripts/                    # 검증/배포 스크립트
├─ build.gradle.kts
└─ settings.gradle.kts
```

---

## 3. Four Core Modules (Responsibilities)

| Module | Role | Responsibilities |
|---|---|---|
| Core | Kernel / Engine | Async scheduler, virtual layer, history/undo, runtime palette, throttling |
| 3DIO | I/O | Schematic/NBT streaming, format adapters, compression |
| AI | Smart Editing | Prompt→Ops mapping, deterministic terrain algorithms, caching |
| GUI | Interface | Widgets, live preview, renderer bridges per platform |

---

## 4. Hybrid Performance Strategy

"자바 8로 작성하고, 자바 21의 성능으로 돌린다" 전략을 수행합니다.

### 4.1 Low-level Optimization (Logic/Common)
- **fastutil**: Primitive collections (Long2ObjectMap, IntArrayList 등) 사용하여 박싱 제거.
- **JCTools**: Lock-free queues (MpscArrayQueue) 기반 데이터 전송.
- **LZ4-Java**: 히스토리 Hot/Cold 계층화 압축.
- **Caffeine**: 반복 참조 및 연산 캐시.

### 4.2 Runtime Acceleration (Platform)
- **Legacy (Java 8)**: Thread pool + 안정적 Tick integration.
- **Modern (Java 21)**: Virtual Threads를 I/O 및 AI 성격 작업에 적용 (메인스레드/월드수정 경로는 통제).

---

## 5. Data Pipeline (Section/Span Oriented)

성능을 위해 블록 단위(BlockPos)가 아닌 Section(16³) 및 Span(연속 구간) 단위를 사용합니다.

- **Input**: AI/3DIO/GUI가 작업(Operation) 생성 (Logic).
- **Transport**: JCTools Queue로 Core에 전달.
- **Process**:
  - Runtime Palette로 Canonical String을 int로 압축.
  - fastutil Maps로 가상 레이어/변경 집합 관리.
- **Inject**:
  - 메인스레드에 Budget 기반 주입.
  - 조명 업데이트/청크 업데이트는 플랫폼별 정책으로 제어.

---

## 6. Block ID Strategy (Dual-Support)

"내부 기준은 하나(Canonical), 호환은 경계(Boundary)에서"

### 6.1 Data Model
- **Canonical ID**: minecraft:stone, minecraft:oak_log[axis=y] (Flattening 표준).
- **Legacy ID**: 1:0, 17:1 — Adapter Boundary에서만 사용.
- **Runtime Palette**: Canonical을 런타임 int로 매핑하여 메모리 및 히스토리 비용 절감.

### 6.2 Conversion Rules (Adapter Pattern)
- **Input Adapter**: 사용자 입력/파일 로드 시 Legacy → Canonical 즉시 변환.
- **Output Adapter**: 필요 시 Canonical → Legacy (타겟 버전 기준) 변환.
- **Mapping Resources**: resources/block-mapping/*.json으로 관리 (코드 하드코딩 금지).

---

## 7. Mixin / Refmap Policy (Collision-Proof)

> 멀티 모드(코어/애드온) + 멀티 버전 구조 충돌 방지 정책

- **Mixin Config**: buildpali-<module>.mixins.json (예: buildpali-core.mixins.json)
- **Refmap**: buildpali-<module>-<loader>-<mcSafe>.refmap.json (자동 생성)
- **Rule**: 플랫폼 모듈만 Mixin을 가질 수 있다. (Logic/Common은 금지)

---

## 8. Dev & Ops Rules (The Guard System)

이 규칙 위반은 단순 버그가 아닌 **빌드 결함(Defect)**으로 취급합니다.

### 8.1 Copilot Instructions (Soft Power)
- **Logic Modules**: Java 8 문법 엄수 (var/record/switch expression 금지).
- **Collections**: fastutil 강제 사용.
- **Context Hygiene**: Logic 작업 중 Modern Platform 파일 동시 오픈 금지.

### 8.2 Gradle Enforcement (Hard Power)
- **Toolchain Enforcement**:
  - api, core/logic, */common: Java 8 고정.
  - mod-*: 해당 버전 요구 Java(17/21 등) 고정.
- **Forbidden Imports (Build Failure)**:
  - Logic/Common에서 net.minecraft.*, net.fabricmc.*, net.minecraftforge.* Import 및 FQCN 사용 시 빌드 실패.
  - 예외: com.mojang.brigadier (Command Framework용).
- **Dependency Guard**:
  - Logic 모듈 build.gradle에 플랫폼 Artifact 선언 시 빌드 실패.

### 8.3 Anti-Drift
- 공통 Gradle 로직은 gradle/conventions/*.gradle.kts로 중앙 관리.
- 버전 모듈의 build.gradle.kts는 템플릿 적용 위주로 최소화.

---

## 9. Security & AI Policy

- **Secrets**: 민감정보(API Keys, Endpoints)는 .env로 분리하고 Git 포함 금지.
- **AI Context**: LLM에는 **필요 최소 파일(@file)**만 제공하며, 프로젝트 전체 컨텍스트 제공 금지.
