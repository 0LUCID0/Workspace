# 📑 언어 대통합 프로그래밍 가이드

## 🗂 전체 목차
- [CHAPTER 01 프로그래밍 기초](#chapter-01-프로그래밍-기초)
  - [1.1 프로그래밍 언어 개요](#11-프로그래밍-언어-개요)
  - [1.2 개발 과정과 실행 환경](#12-개발-과정과-실행-환경)
  - [1.3 Hello World](#13-hello-world)
  - [1.4 언어별 표준 라이브러리 소개](#14-언어별-표준-라이브러리-소개)
  - [1.5 언어별 프로그램 기본 구조](#15-언어별-프로그램-기본-구조)
  - [1.6 코드 컨벤션 비교](#16-코드-컨벤션-비교)

- [CHAPTER 02 상수와 변수](#chapter-02-상수와-변수)
  - [2.1 프로그램 기초 (식별자 규칙, 예약어)](#21-프로그램-기초-식별자-규칙-예약어)
  - [2.2 상수 (리터럴, const, final, readonly)](#22-상수-리터럴-const-final-readonly)
  - [2.3 변수와 메모리 모델](#23-변수와-메모리-모델)

- [CHAPTER 03 자료형과 입출력](#chapter-03-자료형과-입출력)
  - [3.1 자료형](#31-자료형-int-float-char--언어별-확장)
  - [3.2 문자열 처리](#32-문자열-처리)
  - [3.3 입출력 함수/구문 비교](#33-입출력-함수구문-비교)

- [CHAPTER 04 연산자](#chapter-04-연산자)
  - [4.1 산술, 대입, 비교, 논리](#41-산술-대입-비교-논리)
  - [4.2 증감, 조건 (?:)](#42-증감-조건-)
  - [4.3 형 변환 연산자](#43-형-변환-연산자)
  - [4.4 연산자 오버로딩](#44-연산자-오버로딩)
  - [4.5 연산자 우선순위](#45-연산자-우선순위)

- [CHAPTER 05 조건과 반복](#chapter-05-조건과-반복)
  - [5.1 제어문 개요](#51-제어문-개요)
  - [5.2 조건문 if / switch](#52-조건문-if--switch)
  - [5.3 반복문 for / while / do-while](#53-반복문-for--while--do-while)
  - [5.4 foreach 스타일 반복](#54-foreach-스타일-반복)
  - [5.5 분기문 goto / break / continue](#55-분기문-goto--break--continue)

- [CHAPTER 06 함수와 실행 환경](#chapter-06-함수와-실행-환경)
  - [6.1 함수 정의와 호출](#61-함수-정의와-호출)
  - [6.2 재귀 함수](#62-재귀-함수)
  - [6.3 표준 라이브러리 함수](#63-표준-라이브러리-함수)
  - [6.4 동적 메모리](#64-동적-메모리)
  - [6.5 예외 처리](#65-예외-처리)
  - [6.6 비동기 & 병렬 처리](#66-비동기--병렬-처리)

- [CHAPTER 07 객체지향 프로그래밍](#chapter-07-객체지향-프로그래밍)
  - [7.1 클래스와 객체](#71-클래스와-객체)
  - [7.2 생성자 / 소멸자](#72-생성자--소멸자)
  - [7.3 접근 지정자](#73-접근-지정자)
  - [7.4 상속](#74-상속-단일다중인터페이스)
  - [7.5 다형성](#75-다형성-오버로딩-오버라이딩)
  - [7.6 추상 클래스와 인터페이스](#76-추상-클래스와-인터페이스)
  - [7.7 캡슐화](#77-캡슐화-프로퍼티-c-gettersetter-java-c-@property-python)
  - [7.8 특별 기능](#78-특별-기능)

- [CHAPTER 08 파일과 라이브러리](#chapter-08-파일과-라이브러리)
  - [8.1 파일 입출력 기초](#81-파일-입출력-기초)
  - [8.2 텍스트 / 바이너리 파일 처리](#82-텍스트--바이너리-파일-처리)
  - [8.3 표준 라이브러리 활용](#83-표준-라이브러리-활용)
  - [8.4 네트워크 / 소켓 (기본 소개)](#84-네트워크--소켓-기본-소개)

- [CHAPTER 09 확장 개념과 심화](#chapter-09-확장-개념과-심화)
  - [9.1 제네릭 & 템플릿](#91-제네릭--템플릿)
  - [9.2 스레드와 동시성](#92-스레드와-동시성)
  - [9.3 리플렉션](#93-리플렉션-java-c)
  - [9.4 고급 컬렉션](#94-고급-컬렉션)
  - [9.5 언어별 최신 기능](#95-언어별-최신-기능)

---

# CHAPTER 01 프로그래밍 기초
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 01 목차
- [1.1 프로그래밍 언어 개요](#11-프로그래밍-언어-개요)
- [1.2 개발 과정과 실행 환경](#12-개발-과정과-실행-환경)
- [1.3 Hello World](#13-hello-world)
- [1.4 C 언어 개요 & 라이브러리 소개](#14-c-언어-개요--라이브러리-소개)
- [1.5 C 프로그램의 기본 구조](#15-c-프로그램의-기본-구조)
- [1.6 코드 컨벤션 비교](#16-코드-컨벤션-비교)

### 1.1 프로그래밍 언어 개요

프로그래밍 언어는 **컴퓨터와 소통하기 위해 고안된 언어**로, 명령을 사람이 이해하기 쉽게 작성한 후 기계가 이해할 수 있는 형태로 변환합니다.  
각 언어는 실행 방식, 문법적 특징, 활용 분야에 따라 차이가 있습니다.

#### 주요 특징 비교

| 언어 | 실행 방식 | 주요 특징 | 활용 분야 |
|------|-----------|-----------|-----------|
| **C** | 컴파일러가 기계어로 변환 → 실행 파일 생성 | 저수준 제어 가능, 빠른 실행 속도 | 시스템 프로그래밍(OS, 드라이버), 임베디드 |
| **C++** | C 기반 + 객체지향, 컴파일 후 실행 | 클래스/객체, 템플릿, 연산자 오버로딩 지원 | 게임 엔진, 성능 중심 애플리케이션 |
| **Java** | 컴파일 → JVM 바이트코드 실행 | 플랫폼 독립성(Write Once, Run Anywhere), 가비지 컬렉션 | 웹, 모바일(Android), 엔터프라이즈 서버 |
| **C#** | CLR(Common Language Runtime)에서 JIT 컴파일 | .NET 프레임워크와 통합, 이벤트/델리게이트 지원 | 윈도우 앱, 게임(Unity), 클라우드 |
| **Python** | 인터프리터 언어 (한 줄씩 실행) | 간결한 문법, 동적 타이핑, 방대한 라이브러리 | 데이터 과학, 인공지능, 웹 백엔드 |

---

📌 **정리**  
- **C/C++**: 빠르고 강력하나 메모리 관리가 까다로움  
- **Java/C#**: 객체지향 언어, 가비지 컬렉션으로 메모리 관리 자동화  
- **Python**: 배우기 쉽고 범용적이나 속도는 다소 느림  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


### 1.2 개발 과정과 실행 환경

프로그래밍 언어는 소스 코드를 작성한 후, 각 언어의 **실행 환경**에 맞게 변환되어 실행됩니다.  
언어마다 **컴파일/인터프리트 방식**과 **실행 구조**가 다릅니다.

#### 언어별 실행 과정

| 언어 | 실행 과정 | 실행 환경/특징 |
|------|-----------|----------------|
| **C** | 소스코드(.c) → 컴파일(Compile) → 어셈블(Assemble) → 링킹(Linking) → 실행 파일(.exe) | 운영체제 종속적 실행 파일, 성능 우수 |
| **C++** | C와 동일 (컴파일 → 어셈블 → 링킹 → 실행 파일) | g++, Visual Studio 등 IDE 지원, 객체지향 확장 |
| **Java** | 소스코드(.java) → 컴파일 → JVM 바이트코드(.class) → JVM이 해석 후 실행 | 플랫폼 독립성 보장 (JVM만 있으면 실행 가능) |
| **C#** | 소스코드(.cs) → 컴파일 → CIL(Common Intermediate Language) → CLR(JIT 컴파일) → 실행 | .NET Framework / .NET Core 환경 필요 |
| **Python** | 소스코드(.py) → 인터프리터가 한 줄씩 실행 (바이트코드 변환 후 실행) | 빠른 개발, 디버깅 용이, 속도는 상대적으로 느림 |

---

📌 **정리**  
- **C/C++**: 직접 실행 파일을 만들어 속도가 빠름  
- **Java**: JVM 덕분에 OS 독립적  
- **C#**: CLR 기반, Windows/.NET 환경 최적화  
- **Python**: 별도 컴파일 없이 즉시 실행 가능  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


### 1.3 Hello World

각 언어에서 가장 기본적인 출력 예제는 `"Hello, World!"`를 화면에 출력하는 것입니다.  
이는 문법, 실행 방식의 차이를 가장 단순하게 보여줍니다.

#### 언어별 Hello World 예제

```c
// C
#include <stdio.h>
int main() {
    printf("Hello, World!\n");
    return 0;
}
```

```cpp
// C++
#include <iostream>
using namespace std;
int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

```java
// Java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        Console.WriteLine("Hello, World!");
    }
}
```

```python
# Python
print("Hello, World!")
```

---

📌 **정리**  
- **C/C++**: 헤더 포함 필요, main 함수에서 시작  
- **Java**: 클래스와 main 메서드 필요  
- **C#**: 클래스 구조 + `Main()` 진입점 필요  
- **Python**: 한 줄만 작성하면 실행 가능  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


### 1.4 언어별 표준 라이브러리 소개

각 언어는 **표준 라이브러리(Standard Library)**를 제공하여,  
파일 입출력, 문자열 처리, 수학 연산 등 **공통 기능**을 쉽게 사용할 수 있게 합니다.

| 언어 | 표준 라이브러리/패키지 | 주요 기능 | 예시 |
|------|------------------------|-----------|------|
| **C** | `<stdio.h>`, `<stdlib.h>`, `<string.h>`, `<math.h>` | 입출력, 메모리 관리, 문자열, 수학 함수 | `printf`, `malloc`, `strcpy`, `sqrt` |
| **C++** | STL(Standard Template Library), `<iostream>`, `<vector>` | 컨테이너, 알고리즘, 입출력 | `cout`, `vector`, `map`, `sort` |
| **Java** | `java.lang`, `java.util`, `java.io`, `java.nio` | 기본 자료형, 유틸, 입출력, 네트워크 | `ArrayList`, `Scanner`, `Files` |
| **C#** | .NET Framework Class Library (`System.*`) | 콘솔, 컬렉션, 파일 IO, 네트워크 | `Console.WriteLine`, `List<T>`, `File` |
| **Python** | 내장 함수 + 표준 모듈(`math`, `os`, `sys`, `datetime`) | 문자열, 수학, 파일 처리, 시스템 | `print`, `len`, `math.sqrt`, `os.path` |

---

📌 **정리**  
- 모든 언어는 **표준 라이브러리**를 제공해 **반복적인 기능 구현을 단순화**  
- C/C++은 헤더 및 STL, Java/C#은 클래스 기반 라이브러리, Python은 모듈/패키지로 구성  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---

### 1.5 언어별 프로그램 기본 구조

모든 프로그램은 기본적으로 **진입점(entry point)**을 갖습니다.  
언어에 따라 구조는 다르지만, 공통적으로 **시작 지점(main 또는 진입 함수)**이 존재합니다.

#### 언어별 기본 구조 예제

```c
// C
#include <stdio.h>
int main() {
    printf("Hello\n");
    return 0;
}
```

```cpp
// C++
#include <iostream>
using namespace std;
int main() {
    cout << "Hello" << endl;
    return 0;
}
```

```java
// Java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        Console.WriteLine("Hello");
    }
}
```

```python
# Python
print("Hello")
```

---

📌 **정리**  
- **C/C++**: `main()` 함수에서 시작  
- **Java**: 클래스 내부의 `main()` 메서드가 진입점  
- **C#**: 클래스 내 `Main()` 메서드가 진입점  
- **Python**: 별도의 `main` 필요 없이 스크립트 실행 시 첫 줄부터 실행  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)
---
### 1.6 코드 컨벤션 비교

코드 컨벤션(Code Convention)은 **가독성 향상**과 **유지보수 편의성**을 위해  
각 언어/커뮤니티에서 권장하는 작성 규칙입니다.

#### 언어별 주요 코드 컨벤션

| 언어 | 네이밍 규칙 | 중괄호 스타일 | 주석 | 특징 |
|------|-------------|----------------|------|------|
| **C** | 함수/변수: `snake_case` | K&R 스타일 권장<br>`int main() { ... }` | `// 한 줄`, `/* 여러 줄 */` | 간결, 전통적 C 스타일 |
| **C++** | 클래스: `PascalCase`<br>변수/함수: `camelCase` 또는 `snake_case` | K&R / Allman 혼용 | `//`, `/* */` | STL/템플릿 코드 컨벤션 다양 |
| **Java** | 클래스: `PascalCase`<br>메서드/변수: `camelCase`<br>상수: `UPPER_SNAKE_CASE` | K&R 스타일 고정 | `//`, `/* */`, `/** Javadoc */` | **Javadoc** 사용 필수 |
| **C#** | 클래스/메서드: `PascalCase`<br>변수: `camelCase` | Allman 스타일 권장<br>`{` 새 줄 시작 | `//`, `/* */`, `/// XML 주석` | **XML 문서 주석** 지원 |
| **Python** | 함수/변수: `snake_case`<br>클래스: `PascalCase`<br>상수: `UPPER_SNAKE_CASE` | 들여쓰기 기반(중괄호 없음) | `# 한 줄`, `""" 여러 줄 """` | **PEP 8** 스타일 가이드 따름 |

---

📌 **정리**  
- **C/Java/C++/C#**은 중괄호 `{}`로 블록을 구분하지만, **Python**은 **들여쓰기**로 구분  
- **Java**는 Javadoc, **C#**은 XML 주석, **Python**은 Docstring으로 문서화 지원  
- 네이밍은 언어마다 다르지만 **클래스는 PascalCase, 상수는 대문자 스네이크**가 공통적  

---

🔗 [챕터 01 목차](#-챕터-01-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---

# CHAPTER 02 상수와 변수
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 02 목차
- [2.1 프로그램 기초 (식별자 규칙, 예약어)](#21-프로그램-기초-식별자-규칙-예약어)
- [2.2 상수 (리터럴, const, final, readonly)](#22-상수-리터럴-const-final-readonly)
- [2.3 변수와 메모리 모델](#23-변수와-메모리-모델)

---

### 2.1 프로그램 기초 (식별자 규칙, 예약어)

모든 언어에는 **식별자(identifier)**를 정의하는 규칙과 **예약어(keyword)**가 있습니다.  
식별자는 변수, 함수, 클래스 등의 이름으로 사용되며, 예약어는 언어에서 이미 정해진 의미가 있어 식별자로 쓸 수 없습니다.

| 언어 | 식별자 규칙 | 예약어 예시 |
|------|-------------|-------------|
| **C** | 알파벳, 숫자, `_` 사용 가능 (숫자로 시작 불가, 대소문자 구분) | `int`, `return`, `if`, `while` |
| **C++** | C와 동일 + 새로운 키워드 추가 | `class`, `new`, `delete`, `namespace` |
| **Java** | 유니코드 지원, 대소문자 구분, 숫자로 시작 불가 | `class`, `public`, `static`, `void` |
| **C#** | 예약어 앞에 `@` 붙이면 식별자로 사용 가능 | `class`, `namespace`, `using`, `return` |
| **Python** | 대소문자 구분, 예약어는 `keyword` 모듈에서 확인 가능 | `def`, `class`, `lambda`, `import` |

---

### 2.2 상수 (리터럴, const, final, readonly)

상수(Constant)는 **한 번 정의하면 값이 변하지 않는 데이터**입니다.  
언어마다 정의 방식이 다르며, 일부는 **런타임 상수**까지 지원합니다.

```c
// C
const int a = 10;   // 컴파일 상수
#define PI 3.14     // 매크로 상수
```

```cpp
// C++
const int b = 20;       
constexpr int c = 30;   // 컴파일 시간 상수(C++11~)
```

```java
// Java
final int d = 40;       // 상수 (재할당 불가)
static final double PI = 3.14; // 클래스 상수
```

```csharp
// C#
const int e = 50;       // 컴파일 상수
readonly int f = 60;    // 런타임 초기화 상수
```

```python
# Python (상수 키워드 없음)
PI = 3.14      # 관례적으로 대문자 변수명을 상수처럼 사용
```

📌 **정리**  
- **C/C++**: `const`, `#define` 사용  
- **Java**: `final` 키워드, 클래스 상수는 `static final`  
- **C#**: `const`(컴파일 상수), `readonly`(런타임 상수)  
- **Python**: 별도 키워드 없음, 네이밍 규칙으로 구분  

---

### 2.3 변수와 메모리 모델

변수는 데이터를 저장하기 위한 공간으로, 언어마다 **메모리 관리 방식**이 다릅니다.

| 언어 | 메모리 영역/모델 | 특징 |
|------|-----------------|------|
| **C** | 스택(Stack), 힙(Heap), 데이터(Data) 영역 구분 | 수동 메모리 관리 (`malloc`, `free`) |
| **C++** | C와 동일 + 참조자(Reference) 지원 | `new/delete`, 스마트 포인터(`unique_ptr`) |
| **Java** | JVM 메모리 모델: Heap, Stack, Method Area | 가비지 컬렉션(GC) 자동 메모리 관리 |
| **C#** | Value Type(스택), Reference Type(힙) 구분 | CLR이 GC로 자동 관리 |
| **Python** | 모든 것이 객체, 참조 기반 메모리 관리 | GC + 동적 바인딩 |

---

📌 **정리**  
- **C/C++**: 메모리 영역 구분이 명확하며, 직접 관리해야 함  
- **Java/C#**: 가비지 컬렉션이 메모리 해제 담당  
- **Python**: 모든 데이터가 객체로 관리되며, 매우 유연  

---

🔗 [챕터 02 목차](#-챕터-02-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


# CHAPTER 03 자료형과 입출력
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 03 목차
- [3.1 자료형](#31-자료형)
- [3.2 문자열 처리](#32-문자열-처리)
- [3.3 입출력 함수/구문 비교](#33-입출력-함수구문-비교)

---

### 3.1 자료형

각 언어는 기본 자료형(숫자, 문자, 논리형 등)을 제공하며, 언어마다 확장 자료형도 존재합니다.

| 언어 | 기본 자료형 | 확장 자료형/특징 |
|------|-------------|------------------|
| **C** | `int`, `float`, `double`, `char`, `bool(C99)` | `wchar_t` (유니코드), 포인터 |
| **C++** | C 자료형 + `string`, `bool` | `auto` 타입 추론(C++11~), STL 컨테이너 |
| **Java** | 기본형: `int`, `double`, `char`, `boolean`<br>참조형: `String`, 배열, 객체 | Wrapper 클래스 (`Integer`, `Double`) |
| **C#** | `int`, `float`, `double`, `char`, `bool`, `decimal` | `Nullable<T>` 지원 |
| **Python** | `int`, `float`, `str`, `bool`, `None` | 동적 타입, `list`, `dict`, `tuple`, `set` |

---

### 3.2 문자열 처리

문자열은 언어별로 다르게 취급됩니다.  
C는 **문자 배열**, C++/Java/C#/Python은 **문자열 객체**로 다룹니다.

```c
// C (문자 배열 기반)
#include <stdio.h>
#include <string.h>
int main() {
    char str[20] = "Hello";
    strcat(str, " World");   // 문자열 연결
    printf("%s\n", str);
    return 0;
}
```

```cpp
// C++ (string 객체)
#include <iostream>
#include <string>
using namespace std;
int main() {
    string str = "Hello";
    str += " World";   // 문자열 연결
    cout << str << endl;
    return 0;
}
```

```java
// Java (String 클래스)
public class Main {
    public static void main(String[] args) {
        String str = "Hello";
        str += " World";
        System.out.println(str);
    }
}
```

```csharp
// C# (System.String 클래스)
using System;
class Program {
    static void Main() {
        string str = "Hello";
        str += " World";
        Console.WriteLine(str);
    }
}
```

```python
# Python (str 객체)
str = "Hello"
str += " World"
print(str)
```

---

### 3.3 입출력 함수/구문 비교

언어별로 **표준 입출력 방식**이 다릅니다.

```c
// C (stdio.h)
#include <stdio.h>
int main() {
    int x;
    printf("Enter a number: ");
    scanf("%d", &x);
    printf("You entered: %d\n", x);
    return 0;
}
```

```cpp
// C++ (iostream)
#include <iostream>
using namespace std;
int main() {
    int x;
    cout << "Enter a number: ";
    cin >> x;
    cout << "You entered: " << x << endl;
    return 0;
}
```

```java
// Java (Scanner)
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int x = sc.nextInt();
        System.out.println("You entered: " + x);
    }
}
```

```csharp
// C# (Console)
using System;
class Program {
    static void Main() {
        Console.Write("Enter a number: ");
        int x = int.Parse(Console.ReadLine());
        Console.WriteLine("You entered: " + x);
    }
}
```

```python
# Python (input)
x = int(input("Enter a number: "))
print("You entered:", x)
```

---

📌 **정리**  
- **C**: `printf/scanf`  
- **C++**: `cin/cout`  
- **Java**: `System.out` + `Scanner`  
- **C#**: `Console.WriteLine`, `ReadLine`  
- **Python**: `print`, `input`  

---

🔗 [챕터 03 목차](#-챕터-03-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


---

# CHAPTER 04 연산자
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 04 목차
- [4.1 산술, 대입, 비교, 논리](#41-산술-대입-비교-논리)
- [4.2 증감, 조건 (?:)](#42-증감-조건-)
- [4.3 형 변환 연산자](#43-형-변환-연산자)
- [4.4 연산자 오버로딩](#44-연산자-오버로딩)
- [4.5 연산자 우선순위](#45-연산자-우선순위)

---

### 4.1 산술, 대입, 비교, 논리

| 구분 | C / C++ / Java / C# | Python |
|------|----------------------|--------|
| 산술 | `+ - * / %` | 동일 |
| 대입 | `=, +=, -=, *=, /=` | 동일 |
| 비교 | `==, !=, >, <, >=, <=` | 동일 |
| 논리 | `&&, \|\|, !` | `and, or, not` |

---

### 4.2 증감, 조건 (?:)

```c
// C / C++
#include <stdio.h>
int main() {
    int x = 5;
    x++;         // 후위 증가
    ++x;         // 전위 증가
    int y = (x > 5) ? 10 : 20;  // 조건 연산자
    printf("%d %d\n", x, y);
    return 0;
}
```

```java
// Java
class Main {
    public static void main(String[] args) {
        int x = 5;
        x++;
        ++x;
        int y = (x > 5) ? 10 : 20;
        System.out.println(x + " " + y);
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        int x = 5;
        x++;
        ++x;
        int y = (x > 5) ? 10 : 20;
        Console.WriteLine($"{x} {y}");
    }
}
```

```python
# Python (증감 연산자 없음)
x = 5
x += 1   # 증가
y = 10 if x > 5 else 20
print(x, y)
```

---

### 4.3 형 변환 연산자

```c
// C (명시적 캐스팅)
#include <stdio.h>
int main() {
    double a = 3.14;
    int b = (int)a;   // 강제 형변환
    printf("%d\n", b);
    return 0;
}
```

```cpp
// C++ (C 스타일 + C++ 스타일)
#include <iostream>
using namespace std;
int main() {
    double a = 3.14;
    int b = (int)a;        // C 스타일
    int c = static_cast<int>(a); // C++ 스타일
    cout << b << " " << c << endl;
    return 0;
}
```

```java
// Java
public class Main {
    public static void main(String[] args) {
        double a = 3.14;
        int b = (int)a;
        System.out.println(b);
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        double a = 3.14;
        int b = (int)a;
        Console.WriteLine(b);
    }
}
```

```python
# Python (함수 이용)
a = 3.14
b = int(a)
print(b)
```

---

### 4.4 연산자 오버로딩

| 언어 | 지원 여부 | 방법 |
|------|-----------|------|
| **C** | ❌ 없음 | - |
| **C++** | ✅ 지원 | `operator+`, `operator==` 등 정의 가능 |
| **Java** | ❌ 없음 (단, `String +`만 지원) | `"Hello" + "World"` |
| **C#** | ✅ 일부 지원 | `public static T operator+` 등 |
| **Python** | ✅ 지원 | 매직 메서드 (`__add__`, `__eq__`) |

---

### 4.5 연산자 우선순위

연산자 우선순위는 언어마다 거의 동일하지만, Python은 일부 차이가 있습니다.

| 우선순위 (높음→낮음) | C / C++ / Java / C# | Python |
|-----------------------|----------------------|--------|
| 괄호 | `( )` | `( )` |
| 단항 | `++`, `--`, `!` | `not`, 단항 `+ -` |
| 곱셈/나눗셈 | `* / %` | `* / // %` |
| 덧셈/뺄셈 | `+ -` | `+ -` |
| 비교 | `< > <= >=` | 동일 |
| 동등 | `== !=` | `== !=` |
| 논리 | `&& \|\|` | `and or` |
| 대입 | `= +=` | `= +=` |

---

📌 **정리**  
- **C/C++/Java/C#**은 증감 연산자(`++ --`) 지원, Python은 없음  
- **형 변환**: C/C++은 캐스팅, Java/C#도 `(타입)` 사용, Python은 함수(`int()`, `float()`) 사용  
- **연산자 오버로딩**: C++/C#/Python 가능, Java는 문자열 연결만 지원  

---

🔗 [챕터 04 목차](#-챕터-04-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---

# CHAPTER 05 조건과 반복
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 05 목차
- [5.1 제어문 개요](#51-제어문-개요)
- [5.2 조건문 if / switch](#52-조건문-if--switch)
- [5.3 반복문 for / while / do-while](#53-반복문-for--while--do-while)
- [5.4 foreach 스타일 반복](#54-foreach-스타일-반복)
- [5.5 분기문 goto / break / continue](#55-분기문-goto--break--continue)

---

### 5.1 제어문 개요

제어문(Control Statement)은 **프로그램 실행 흐름을 제어**하는 문법입니다.  
- 조건문: `if`, `switch`  
- 반복문: `for`, `while`, `do-while`, `foreach`  
- 분기문: `break`, `continue`, `goto`  

---

### 5.2 조건문 if / switch

```c
// C
#include <stdio.h>
int main() {
    int x = 10;
    if (x > 5) {
        printf("x is greater than 5\n");
    } else {
        printf("x is 5 or less\n");
    }

    switch (x) {
        case 10: printf("x is 10\n"); break;
        default: printf("x is not 10\n");
    }
    return 0;
}
```

```cpp
// C++
#include <iostream>
using namespace std;
int main() {
    int x = 10;
    if (x > 5) cout << "x > 5" << endl;
    else cout << "x <= 5" << endl;

    switch (x) {
        case 10: cout << "x == 10" << endl; break;
        default: cout << "x != 10" << endl;
    }
    return 0;
}
```

```java
// Java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        if (x > 5) {
            System.out.println("x > 5");
        } else {
            System.out.println("x <= 5");
        }

        switch (x) {
            case 10: System.out.println("x == 10"); break;
            default: System.out.println("x != 10");
        }
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        int x = 10;
        if (x > 5) Console.WriteLine("x > 5");
        else Console.WriteLine("x <= 5");

        switch (x) {
            case 10: Console.WriteLine("x == 10"); break;
            default: Console.WriteLine("x != 10"); break;
        }
    }
}
```

```python
# Python (switch 없음, if만 존재)
x = 10
if x > 5:
    print("x > 5")
else:
    print("x <= 5")
```

---

### 5.3 반복문 for / while / do-while

```c
// C
#include <stdio.h>
int main() {
    for (int i = 0; i < 3; i++) printf("%d\n", i);

    int j = 0;
    while (j < 3) {
        printf("%d\n", j);
        j++;
    }

    int k = 0;
    do {
        printf("%d\n", k);
        k++;
    } while (k < 3);

    return 0;
}
```

```java
// Java
public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 3; i++) System.out.println(i);

        int j = 0;
        while (j < 3) {
            System.out.println(j);
            j++;
        }

        int k = 0;
        do {
            System.out.println(k);
            k++;
        } while (k < 3);
    }
}
```

```python
# Python (do-while 없음)
for i in range(3):
    print(i)

j = 0
while j < 3:
    print(j)
    j += 1
```

---

### 5.4 foreach 스타일 반복

| 언어 | foreach 지원 여부 | 예시 |
|------|------------------|------|
| **C** | ❌ 없음 (배열 인덱스 사용) | - |
| **C++** | ✅ `for (auto x : arr)` (C++11~) | `for (auto n : v)` |
| **Java** | ✅ Enhanced for | `for (int n : arr)` |
| **C#** | ✅ foreach | `foreach (int n in arr)` |
| **Python** | ✅ for-in | `for n in arr:` |

---

### 5.5 분기문 goto / break / continue

```c
// C (goto, break, continue 모두 지원)
#include <stdio.h>
int main() {
    for (int i = 0; i < 5; i++) {
        if (i == 2) continue;
        if (i == 4) break;
        printf("%d\n", i);
    }

    goto END;
    printf("This will be skipped\n");

END:
    printf("Program End\n");
    return 0;
}
```

```python
# Python (goto 없음, break/continue만 있음)
for i in range(5):
    if i == 2:
        continue
    if i == 4:
        break
    print(i)
print("Program End")
```

---

📌 **정리**  
- **if/switch**: Python은 `switch` 없음  
- **for/while/do-while**: Python은 `do-while` 없음  
- **foreach**: C 제외 전부 지원  
- **goto**: C/C++ 지원, Java/C#/Python은 없음  

---

🔗 [챕터 05 목차](#-챕터-05-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


# CHAPTER 06 함수와 실행 환경
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 06 목차
- [6.1 함수 정의와 호출](#61-함수-정의와-호출)
- [6.2 재귀 함수](#62-재귀-함수)
- [6.3 표준 라이브러리 함수](#63-표준-라이브러리-함수)
- [6.4 동적 메모리](#64-동적-메모리)
- [6.5 예외 처리](#65-예외-처리)
- [6.6 비동기 & 병렬 처리](#66-비동기--병렬-처리)

---

### 6.1 함수 정의와 호출

```c
// C
#include <stdio.h>
int add(int a, int b) {
    return a + b;
}
int main() {
    printf("%d\n", add(2, 3));
    return 0;
}
```

```cpp
// C++
#include <iostream>
using namespace std;
int add(int a, int b) { return a + b; }
int main() {
    cout << add(2, 3) << endl;
    return 0;
}
```

```java
// Java
public class Main {
    static int add(int a, int b) {
        return a + b;
    }
    public static void main(String[] args) {
        System.out.println(add(2, 3));
    }
}
```

```csharp
// C#
using System;
class Program {
    static int Add(int a, int b) => a + b;
    static void Main() {
        Console.WriteLine(Add(2, 3));
    }
}
```

```python
# Python
def add(a, b):
    return a + b

print(add(2, 3))
```

---

### 6.2 재귀 함수

```c
// C (팩토리얼)
#include <stdio.h>
int fact(int n) {
    if (n <= 1) return 1;
    return n * fact(n - 1);
}
int main() { printf("%d\n", fact(5)); }
```

```python
# Python
def fact(n):
    return 1 if n <= 1 else n * fact(n-1)
print(fact(5))
```

---

### 6.3 표준 라이브러리 함수

| 언어 | 대표 함수 | 예시 |
|------|-----------|------|
| **C** | `printf`, `scanf`, `strlen`, `malloc` | `printf("%d", 10);` |
| **C++** | `cout`, `cin`, STL `sort`, `vector` | `sort(v.begin(), v.end());` |
| **Java** | `System.out.println`, `Math.max`, `Arrays.sort` | `Math.max(3, 5)` |
| **C#** | `Console.WriteLine`, `Math.Max`, `Array.Sort` | `Math.Max(3, 5)` |
| **Python** | `print`, `len`, `sum`, `sorted` | `sorted([3,1,2])` |

---

### 6.4 동적 메모리

```c
// C
#include <stdlib.h>
#include <stdio.h>
int main() {
    int *arr = (int*)malloc(3 * sizeof(int));
    arr[0] = 1; arr[1] = 2; arr[2] = 3;
    printf("%d\n", arr[1]);
    free(arr);
    return 0;
}
```

```cpp
// C++
#include <iostream>
using namespace std;
int main() {
    int* arr = new int[3]{1,2,3};
    cout << arr[1] << endl;
    delete[] arr;
}
```

```java
// Java (GC가 관리)
public class Main {
    public static void main(String[] args) {
        int[] arr = new int[]{1,2,3};
        System.out.println(arr[1]);
    }
}
```

```python
# Python (자동 관리)
arr = [1, 2, 3]
print(arr[1])
```

---

### 6.5 예외 처리

```cpp
// C++ (try-catch)
#include <iostream>
using namespace std;
int main() {
    try {
        throw 1;
    } catch (int e) {
        cout << "Error: " << e << endl;
    }
}
```

```java
// Java (checked exception)
public class Main {
    public static void main(String[] args) {
        try {
            int x = 5/0;
        } catch (Exception e) {
            System.out.println("Error: " + e);
        }
    }
}
```

```csharp
// C#
using System;
class Program {
    static void Main() {
        try {
            int x = 5/0;
        } catch (Exception e) {
            Console.WriteLine(e.Message);
        } finally {
            Console.WriteLine("Done");
        }
    }
}
```

```python
# Python
try:
    x = 5 / 0
except ZeroDivisionError as e:
    print("Error:", e)
finally:
    print("Done")
```

---

### 6.6 비동기 & 병렬 처리

| 언어 | 방법 | 예시 |
|------|------|------|
| **C** | POSIX Threads (pthread) | `pthread_create()` |
| **C++** | `std::thread`, `async` | `thread t(func);` |
| **Java** | `Thread`, `ExecutorService` | `new Thread(r).start();` |
| **C#** | `async/await`, `Task` | `await Task.Run(...)` |
| **Python** | `asyncio`, `threading` | `async def func(): ...` |

---

📌 **정리**  
- **C/C++**: 수동 메모리 관리, `try-catch`는 C++부터  
- **Java/C#**: GC, 예외 처리 강력, 병렬 지원 풍부  
- **Python**: 모든 것이 객체, 비동기 지원(`asyncio`)  

---

🔗 [챕터 06 목차](#-챕터-06-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---

# CHAPTER 07 객체지향 프로그래밍
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 07 목차
- [7.1 클래스와 객체](#71-클래스와-객체)
- [7.2 생성자 / 소멸자](#72-생성자--소멸자)
- [7.3 접근 지정자](#73-접근-지정자)
- [7.4 상속](#74-상속)
- [7.5 다형성](#75-다형성)
- [7.6 추상 클래스와 인터페이스](#76-추상-클래스와-인터페이스)
- [7.7 캡슐화](#77-캡슐화)
- [7.8 특별 기능](#78-특별-기능)

---

### 7.1 클래스와 객체

```cpp
// C++
#include <iostream>
using namespace std;
class Dog {
public:
    string name;
    void bark() { cout << name << " says Woof!\n"; }
};
int main() {
    Dog d;
    d.name = "Buddy";
    d.bark();
}
```

```java
// Java
class Dog {
    String name;
    void bark() { System.out.println(name + " says Woof!"); }
}
public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.name = "Buddy";
        d.bark();
    }
}
```

```python
# Python
class Dog:
    def __init__(self, name):
        self.name = name
    def bark(self):
        print(self.name, "says Woof!")

d = Dog("Buddy")
d.bark()
```

---

### 7.2 생성자 / 소멸자

```cpp
// C++
class Cat {
public:
    Cat() { cout << "Constructor called\n"; }
    ~Cat() { cout << "Destructor called\n"; }
};
```

```java
// Java
class Cat {
    Cat() { System.out.println("Constructor called"); }
}
```

```csharp
// C#
class Cat {
    public Cat() { Console.WriteLine("Constructor called"); }
    ~Cat() { Console.WriteLine("Destructor (finalizer) called"); }
}
```

```python
# Python
class Cat:
    def __init__(self):
        print("Constructor called")
    def __del__(self):
        print("Destructor called")
```

---

### 7.3 접근 지정자

| 언어 | 접근 지정자 |
|------|-------------|
| **C++** | `public`, `private`, `protected` |
| **Java** | `public`, `private`, `protected`, (default: package-private) |
| **C#** | `public`, `private`, `protected`, `internal`, `protected internal` |
| **Python** | 규약 기반: `_protected`, `__private` (실제 강제 아님) |

---

### 7.4 상속

객체지향 언어는 **상속(Inheritance)**을 통해 코드 재사용과 다형성을 지원합니다.  
언어별로 **가상 함수**, **다중 상속** 여부가 다릅니다.

```cpp
// C++ (단일 상속 + 가상 함수 + 다중 상속)
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() { cout << "Some sound\n"; } // 가상 함수
};

class Dog : public Animal {
public:
    void sound() override { cout << "Woof\n"; }
};

// 다중 상속 예시
class Pet { public: void play(){ cout << "Play\n"; } };
class Bulldog : public Dog, public Pet {};

int main() {
    Animal* a = new Dog();
    a->sound(); // 가상 함수 → "Woof"

    Bulldog b;
    b.sound();  // "Woof"
    b.play();   // 다중 상속
}
```

```java
// Java (단일 상속 + 인터페이스 다중 구현)
class Animal {
    void sound() { System.out.println("Some sound"); }
}
interface Pet { void play(); }
class Dog extends Animal implements Pet {
    @Override void sound() { System.out.println("Woof"); }
    public void play() { System.out.println("Play"); }
}
```

```csharp
// C# (단일 상속 + 인터페이스 다중 구현)
class Animal {
    public virtual void Sound() { Console.WriteLine("Some sound"); }
}
interface IPet { void Play(); }
class Dog : Animal, IPet {
    public override void Sound() { Console.WriteLine("Woof"); }
    public void Play() { Console.WriteLine("Play"); }
}
```

```python
# Python (다중 상속 지원)
class Animal:
    def sound(self): print("Some sound")

class Pet:
    def play(self): print("Play")

class Dog(Animal, Pet):
    def sound(self): print("Woof")

d = Dog()
d.sound()
d.play()
```

---

📌 **정리**  
- **C++**: 단일/다중 상속 모두 지원, `virtual`로 가상 함수 지정  
- **Java**: **단일 상속**만 허용, 다중 기능은 **인터페이스**로 해결  
- **C#**: **단일 상속** + **여러 인터페이스 구현 가능**  
- **Python**: 다중 상속 지원, 메서드 탐색 순서(MRO) 적용  

---

🔗 [챕터 07 목차](#-챕터-07-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---

### 7.5 다형성 (오버로딩, 오버라이딩, 가상 함수, MRO)

다형성(Polymorphism)은 **동일한 인터페이스로 다양한 동작을 수행**하는 개념입니다.  
- **오버로딩(Overloading)**: 같은 이름의 메서드, 매개변수 다름  
- **오버라이딩(Overriding)**: 부모 클래스 메서드를 자식이 재정의  
- **가상 함수(Virtual Function, C++)**: 런타임 다형성  
- **MRO (Python)**: 다중 상속 시 메서드 탐색 순서  

---

#### C++ (가상 함수 기반 다형성)

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() { cout << "Some sound\n"; }
};

class Dog : public Animal {
public:
    void sound() override { cout << "Woof\n"; }
};

class Cat : public Animal {
public:
    void sound() override { cout << "Meow\n"; }
};

int main() {
    Animal* a1 = new Dog();
    Animal* a2 = new Cat();
    a1->sound();  // Woof
    a2->sound();  // Meow
}
```

---

#### Java (오버로딩 + 오버라이딩)

```java
class Animal {
    void sound() { System.out.println("Some sound"); }
}

class Dog extends Animal {
    @Override void sound() { System.out.println("Woof"); }
}

public class Main {
    // 오버로딩
    static int add(int a, int b) { return a+b; }
    static double add(double a, double b) { return a+b; }

    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound(); // 오버라이딩 → "Woof"
        System.out.println(add(3, 4));   // 오버로딩
        System.out.println(add(3.1, 4.2));
    }
}
```

---

#### C# (오버라이딩 + 가상 메서드)

```csharp
using System;
class Animal {
    public virtual void Sound() { Console.WriteLine("Some sound"); }
}

class Dog : Animal {
    public override void Sound() { Console.WriteLine("Woof"); }
}

class Program {
    static void Main() {
        Animal a = new Dog();
        a.Sound(); // Woof
    }
}
```

---

#### Python (오버라이딩 + MRO)

```python
class Animal:
    def sound(self): print("Some sound")

class Dog(Animal):
    def sound(self): print("Woof")

class Cat(Animal):
    def sound(self): print("Meow")

# 다중 상속 + MRO 확인
class Bulldog(Dog, Cat):
    pass

b = Bulldog()
b.sound()           # "Woof" (Dog → Cat 순서)
print(Bulldog.mro()) # [Bulldog, Dog, Cat, Animal, object]
```

---

📌 **정리**  
- **C++**: `virtual` 키워드로 가상 함수, 런타임 다형성  
- **Java**: 오버로딩 + 오버라이딩, @Override 필수  
- **C#**: `virtual/override`로 다형성 구현  
- **Python**: 동적 언어 특성상 유연, 다중 상속 시 **MRO** 규칙 적용  

---

🔗 [챕터 07 목차](#-챕터-07-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)
### 7.6 추상 클래스와 인터페이스

추상 클래스(Abstract Class)와 인터페이스(Interface)는 **공통 규격을 정의**하는 역할을 합니다.  
- **추상 클래스**: 일부 메서드는 구현 가능, 일부는 추상 메서드  
- **인터페이스**: 메서드 시그니처만 정의 (언어에 따라 상수/기본 메서드 허용)  
- **C++**: 추상 클래스 = 순수 가상 함수만 가진 클래스 → 인터페이스처럼 사용  

---

#### C++ (추상 클래스 = 순수 가상 함수)

```cpp
#include <iostream>
using namespace std;

// 추상 클래스
class Animal {
public:
    virtual void sound() = 0; // 순수 가상 함수
};

class Dog : public Animal {
public:
    void sound() override { cout << "Woof\n"; }
};

int main() {
    Animal* a = new Dog();
    a->sound(); // Woof
}
```

---

#### Java (추상 클래스 + 인터페이스)

```java
// 추상 클래스
abstract class Animal {
    abstract void sound();
    void eat() { System.out.println("Eating..."); } // 구현 가능
}

// 인터페이스
interface Pet {
    void play();
}

class Dog extends Animal implements Pet {
    @Override void sound() { System.out.println("Woof"); }
    public void play() { System.out.println("Play"); }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound();  // Woof
    }
}
```

---

#### C# (추상 클래스 + 인터페이스)

```csharp
using System;

// 추상 클래스
abstract class Animal {
    public abstract void Sound();
    public void Eat() => Console.WriteLine("Eating...");
}

// 인터페이스
interface IPet {
    void Play();
}

class Dog : Animal, IPet {
    public override void Sound() => Console.WriteLine("Woof");
    public void Play() => Console.WriteLine("Play");
}

class Program {
    static void Main() {
        Animal a = new Dog();
        a.Sound(); // Woof
    }
}
```

---

#### Python (ABC 모듈, 인터페이스 유사 구현)

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self): pass

class Pet(ABC):
    @abstractmethod
    def play(self): pass

class Dog(Animal, Pet):
    def sound(self): print("Woof")
    def play(self): print("Play")

d = Dog()
d.sound()
d.play()
```

---

📌 **정리**  
- **C++**: 추상 클래스(순수 가상 함수) → 인터페이스 역할 가능  
- **Java**: 추상 클래스 + 다중 인터페이스 구현 가능  
- **C#**: 추상 클래스 + 다중 인터페이스 구현 가능  
- **Python**: `abc` 모듈로 추상 클래스 구현, 다중 상속으로 인터페이스 대체  

---

🔗 [챕터 07 목차](#-챕터-07-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)

---
### 7.7 캡슐화

캡슐화(Encapsulation)는 **데이터를 외부에서 직접 접근하지 못하도록 보호**하고,  
**getter/setter 또는 프로퍼티**를 통해 제어하는 기법입니다.  

---

#### C++ (getter/setter)

```cpp
#include <iostream>
using namespace std;
class Person {
private:
    string name;
public:
    void setName(string n) { name = n; }
    string getName() { return name; }
};
int main() {
    Person p;
    p.setName("Alice");
    cout << p.getName() << endl;
}
```

---

#### Java (getter/setter)

```java
class Person {
    private String name;

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
}

public class Main {
    public static void main(String[] args) {
        Person p = new Person();
        p.setName("Alice");
        System.out.println(p.getName());
    }
}
```

---

#### C# (Property)

```csharp
using System;
class Person {
    public string Name { get; set; }   // 자동 구현 프로퍼티
}
class Program {
    static void Main() {
        Person p = new Person();
        p.Name = "Alice";              // set
        Console.WriteLine(p.Name);     // get
    }
}
```

---

#### Python (@property)

```python
class Person:
    def __init__(self, name):
        self._name = name   # protected 관례 (_)

    @property
    def name(self):         # getter
        return self._name

    @name.setter
    def name(self, value):  # setter
        self._name = value

p = Person("Alice")
print(p.name)   # getter
p.name = "Bob"  # setter
print(p.name)
```

---

📌 **정리**  
- **C++/Java**: 명시적 `getter/setter` 작성  
- **C#**: `property` 문법으로 간결  
- **Python**: `@property` 데코레이터, 필요 시 `__private` 네임 맹글링 사용 (`_ClassName__var`)  

---

🔗 [챕터 07 목차](#-챕터-07-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)
---
### 7.8 특별 기능

객체지향 언어마다 고유한 기능이 존재하며,  
이 기능들은 **다형성 확장, 이벤트 처리, 메타 프로그래밍** 등에 활용됩니다.

---

#### C++ (연산자 오버로딩, 템플릿)

```cpp
#include <iostream>
using namespace std;

class Complex {
    double r, i;
public:
    Complex(double r, double i): r(r), i(i) {}
    Complex operator+(const Complex& other) {
        return Complex(r + other.r, i + other.i);
    }
    void print() { cout << r << " + " << i << "i\n"; }
};

int main() {
    Complex a(1,2), b(3,4);
    Complex c = a + b;  // 연산자 오버로딩
    c.print();
}
```

---

#### Java (리플렉션, 다중 인터페이스 구현)

```java
import java.lang.reflect.*;

interface A { void foo(); }
interface B { void bar(); }

class C implements A, B {
    public void foo() { System.out.println("foo"); }
    public void bar() { System.out.println("bar"); }
}

public class Main {
    public static void main(String[] args) throws Exception {
        C obj = new C();
        // 리플렉션 사용
        Method m = obj.getClass().getMethod("foo");
        m.invoke(obj);  // "foo"
    }
}
```

---

#### C# (Delegate, Event, LINQ)

```csharp
using System;
using System.Linq;

class Program {
    // 델리게이트 정의
    delegate void MyDelegate(string msg);

    // 이벤트 정의
    static event MyDelegate OnMessage;

    static void Main() {
        OnMessage += (msg) => Console.WriteLine("Event: " + msg);
        OnMessage("Hello");  // 이벤트 호출

        // LINQ 예제
        var nums = new int[]{1,2,3,4};
        var even = nums.Where(x => x%2==0);
        foreach (var n in even) Console.WriteLine(n);
    }
}
```

---

#### Python (매직 메서드, 데코레이터)

```python
# 매직 메서드 (__add__)
class Complex:
    def __init__(self, r, i): self.r, self.i = r, i
    def __add__(self, other):
        return Complex(self.r + other.r, self.i + other.i)
    def __str__(self):
        return f"{self.r}+{self.i}i"

a = Complex(1,2)
b = Complex(3,4)
print(a+b)   # 4+6i

# 데코레이터
def logger(func):
    def wrapper(*args, **kwargs):
        print("Calling", func.__name__)
        return func(*args, **kwargs)
    return wrapper

@logger
def greet(name): print("Hello", name)

greet("Alice")
```

---

📌 **정리**  
- **C++**: 연산자 오버로딩, 템플릿으로 고성능 추상화  
- **Java**: 인터페이스 다중 구현 + 강력한 리플렉션  
- **C#**: Delegate & Event로 이벤트 중심 프로그래밍, LINQ로 데이터 질의  
- **Python**: 매직 메서드로 연산자 오버로딩, 데코레이터로 함수/클래스 확장  

---

🔗 [챕터 07 목차](#-챕터-07-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)
---
# CHAPTER 08 파일과 라이브러리
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 08 목차
- [8.1 파일 입출력 기초](#81-파일-입출력-기초)
- [8.2 텍스트--바이너리-파일-처리](#82-텍스트--바이너리-파일-처리)
- [8.3 표준 라이브러리 활용](#83-표준-라이브러리-활용)
- [8.4 네트워크--소켓-기본-소개](#84-네트워크--소켓-기본-소개)

---

### 8.1 파일 입출력 기초

```c
// C
#include <stdio.h>
int main() {
    FILE *fp = fopen("test.txt", "w");
    fprintf(fp, "Hello File\n");
    fclose(fp);
    return 0;
}
```

```cpp
// C++
#include <fstream>
using namespace std;
int main() {
    ofstream out("test.txt");
    out << "Hello File" << endl;
    out.close();
}
```

```java
// Java
import java.io.*;
public class Main {
    public static void main(String[] args) throws Exception {
        FileWriter fw = new FileWriter("test.txt");
        fw.write("Hello File\n");
        fw.close();
    }
}
```

```csharp
// C#
using System.IO;
class Program {
    static void Main() {
        File.WriteAllText("test.txt", "Hello File\n");
    }
}
```

```python
# Python
with open("test.txt", "w") as f:
    f.write("Hello File\n")
```

---

### 8.2 텍스트 / 바이너리 파일 처리

```c
// C (바이너리 파일)
#include <stdio.h>
int main() {
    FILE *fp = fopen("data.bin", "wb");
    int n = 123;
    fwrite(&n, sizeof(int), 1, fp);
    fclose(fp);
}
```

```cpp
// C++ (바이너리 파일)
#include <fstream>
using namespace std;
int main() {
    ofstream out("data.bin", ios::binary);
    int n = 123;
    out.write((char*)&n, sizeof(n));
    out.close();
}
```

```java
// Java (바이너리 파일)
import java.io.*;
public class Main {
    public static void main(String[] args) throws Exception {
        DataOutputStream out = new DataOutputStream(new FileOutputStream("data.bin"));
        out.writeInt(123);
        out.close();
    }
}
```

```csharp
// C#
using System.IO;
class Program {
    static void Main() {
        using (BinaryWriter bw = new BinaryWriter(File.Open("data.bin", FileMode.Create))) {
            bw.Write(123);
        }
    }
}
```

```python
# Python
with open("data.bin", "wb") as f:
    f.write((123).to_bytes(4, "little"))
```

---

### 8.3 표준 라이브러리 활용

| 언어 | 라이브러리 | 기능 |
|------|------------|------|
| **C** | `<stdio.h>`, `<stdlib.h>` | 파일 IO, 메모리 관리 |
| **C++** | `<fstream>`, STL | 파일 IO, 컨테이너 |
| **Java** | `java.io`, `java.nio.file` | 파일, 네트워크 IO |
| **C#** | `System.IO` | 파일, 디렉토리 관리 |
| **Python** | `open()`, `os`, `shutil`, `pathlib` | 파일/디렉토리 관리 |

---

### 8.4 네트워크 / 소켓 (기본 소개)

```c
// C (POSIX 소켓)
#include <stdio.h>
#include <sys/socket.h>
int main() {
    int sock = socket(AF_INET, SOCK_STREAM, 0);
    if (sock < 0) printf("Socket error\n");
}
```

```java
// Java
import java.net.*;
class Main {
    public static void main(String[] args) throws Exception {
        Socket s = new Socket("example.com", 80);
        System.out.println("Connected");
        s.close();
    }
}
```

```csharp
// C#
using System.Net.Sockets;
class Program {
    static void Main() {
        TcpClient client = new TcpClient("example.com", 80);
        client.Close();
    }
}
```

```python
# Python
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(("example.com", 80))
s.close()
```

---

📌 **정리**  
- 파일 입출력은 모든 언어에서 공통 지원  
- **C/C++**: 저수준 파일 처리 함수 사용  
- **Java/C#**: 클래스 기반 고수준 API 제공  
- **Python**: 간결한 `with open` 구문 지원  
- 네트워크 프로그래밍도 모든 언어에서 가능하나 **Python/Java/C#은 고수준 API**가 많음  

---

🔗 [챕터 08 목차](#-챕터-08-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)


---

# CHAPTER 09 확장 개념과 심화
🔗 [전체 목차로 돌아가기](#-언어-대통합-프로그래밍-가이드)

## 📌 챕터 09 목차
- [9.1 제네릭 & 템플릿](#91-제네릭--템플릿)
- [9.2 스레드와 동시성](#92-스레드와-동시성)
- [9.3 리플렉션](#93-리플렉션)
- [9.4 고급 컬렉션](#94-고급-컬렉션)
- [9.5 언어별 최신 기능](#95-언어별-최신-기능)

---

### 9.1 제네릭 & 템플릿

```cpp
// C++ 템플릿
#include <iostream>
using namespace std;
template <typename T>
T add(T a, T b) { return a + b; }
int main() { cout << add(3, 4) << endl; }
```

```java
// Java 제네릭
import java.util.*;
class Main {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<>();
        list.add(10);
        System.out.println(list.get(0));
    }
}
```

```csharp
// C# 제네릭
using System;
using System.Collections.Generic;
class Program {
    static void Main() {
        List<int> list = new List<int>();
        list.Add(10);
        Console.WriteLine(list[0]);
    }
}
```

```python
# Python (typing)
from typing import List
def first(xs: List[int]) -> int:
    return xs[0]
print(first([10, 20]))
```

---

### 9.2 스레드와 동시성

```cpp
// C++11 thread
#include <iostream>
#include <thread>
using namespace std;
void func() { cout << "Hello from thread\n"; }
int main() {
    thread t(func);
    t.join();
}
```

```java
// Java Thread
class Main {
    public static void main(String[] args) {
        Thread t = new Thread(() -> System.out.println("Hello from thread"));
        t.start();
    }
}
```

```csharp
// C#
using System;
using System.Threading;
class Program {
    static void Main() {
        Thread t = new Thread(() => Console.WriteLine("Hello from thread"));
        t.Start();
    }
}
```

```python
# Python
import threading
def func(): print("Hello from thread")
t = threading.Thread(target=func)
t.start()
t.join()
```

---

### 9.3 리플렉션

| 언어 | 리플렉션 지원 여부 | 예시 |
|------|------------------|------|
| **Java** | ✅ `Class`, `Method`, `Field` | `Class.forName("java.util.Date")` |
| **C#** | ✅ `System.Reflection` | `typeof(string).GetMethods()` |
| **Python** | ✅ `getattr`, `hasattr` | `getattr(obj, "method")` |
| **C/C++** | ❌ 직접 지원 X (런타임 타입 정보만 일부) | `typeid(var).name()` (C++) |

```java
// Java
import java.lang.reflect.*;
class Main {
    public static void main(String[] args) throws Exception {
        Class<?> cls = Class.forName("java.util.Date");
        for (Method m : cls.getMethods()) {
            System.out.println(m.getName());
        }
    }
}
```

---

### 9.4 고급 컬렉션

| 언어 | 고급 컬렉션 |
|------|-------------|
| **C++** | `vector`, `map`, `set`, `unordered_map` |
| **Java** | `ArrayList`, `HashMap`, `HashSet`, `Stream` |
| **C#** | `List<T>`, `Dictionary<K,V>`, `HashSet<T>`, `LINQ` |
| **Python** | `list`, `dict`, `set`, `tuple`, `collections` (`deque`, `Counter`) |

```python
# Python 고급 컬렉션 예시
from collections import Counter
cnt = Counter("banana")
print(cnt)  # {'a':3, 'b':1, 'n':2}
```

---

### 9.5 언어별 최신 기능

| 언어 | 최신 기능 |
|------|-----------|
| **C++** | `auto`, 람다식, 스마트 포인터 |
| **Java** | 람다식, Stream API, `var` (Java 10~) |
| **C#** | LINQ, async/await, 튜플, 패턴 매칭 |
| **Python** | f-string, async/await, typing |

```cpp
// C++ 람다
auto add = [](int a, int b){ return a+b; };
```

```java
// Java Stream
import java.util.*;
class Main {
    public static void main(String[] args) {
        List<Integer> nums = Arrays.asList(1,2,3);
        nums.stream().map(x->x*2).forEach(System.out::println);
    }
}
```

```csharp
// C# LINQ
using System;
using System.Linq;
class Program {
    static void Main() {
        var nums = new int[]{1,2,3};
        var doubled = nums.Select(x => x*2);
        foreach (var n in doubled) Console.WriteLine(n);
    }
}
```

```python
# Python f-string + async
name = "World"
print(f"Hello {name}")
```

---

📌 **정리**  
- **제네릭/템플릿**: 타입 안정성과 코드 재사용성 제공  
- **스레드/동시성**: 모든 언어에서 지원, Python은 GIL로 한계 있음  
- **리플렉션**: Java/C#/Python은 강력 지원, C++은 RTTI 수준  
- **고급 컬렉션**: 언어별로 컨테이너/컬렉션 라이브러리 차별화  
- **최신 기능**: 람다식, async/await, 스트림 API 등 현대적 문법 공통 채택  

---

🔗 [챕터 09 목차](#-챕터-09-목차) | [전체 목차](#-언어-대통합-프로그래밍-가이드)
