# 📝 Git Guide

Git을 처음 접하는 사람을 위한 기초 설정, 커밋/브랜치 전략, 협업 가이드입니다.  

---

## 1. 초기 설정 (Global Config)

```bash
# 사용자 이름 설정 (커밋 기록에 표시됨)
git config --global user.name "Your Name"

# 사용자 이메일 설정 (GitHub 이메일과 동일하게 권장)
git config --global user.email "your.email@example.com"

# 기본 브랜치명을 main으로 설정 (기본은 master)
git config --global init.defaultBranch main

# alias(단축키) 등록 예시
git config --global alias.st "status"           # git st  → git status
git config --global alias.co "checkout"         # git co  → git checkout
git config --global alias.br "branch"           # git br  → git branch
git config --global alias.cm "commit -m"        # git cm "msg" → git commit -m "msg"
git config --global alias.lg "log --oneline --graph --all --decorate" 
# git lg → 예쁜 그래프 로그 보기
```

---

## 2. Git 저장소 초기화 & 첫 커밋

```bash
git init                         # 현재 폴더를 Git 저장소로 초기화
git status                       # 상태 확인 (추적되지 않은 파일, 수정된 파일 등)
git add .                        # 모든 변경사항 스테이징
git commit -m "chore: initial commit"   # 첫 커밋
git remote add origin https://github.com/<username>/<repo>.git   # 원격 저장소 연결
git push -u origin main          # main 브랜치로 푸시
```

---

## 3. 커밋 잘 쓰는 법 ✍️

- **짧고 명확하게**: 제목은 50자 이내, 끝에 마침표 X  
- **현재 시제 사용**: “Added” ❌ → “Add” ⭕  
- **하나의 커밋 = 하나의 의미** (여러 작업을 한꺼번에 넣지 말기)  
- **본문(옵션)**: 필요하다면 `왜` 수정했는지 서술  
- **Conventional Commits** 규칙 사용 권장  

예시:
```bash
feat: add user login API
fix: resolve null pointer in login handler
docs: update README with setup guide
refactor: simplify login validation logic
```

---

## 4. 브랜치 전략

```bash
git checkout -b feature/login     # 새로운 기능 브랜치 생성
git add . && git commit -m "feat: implement login form"
git push origin feature/login     # 원격으로 브랜치 push

git checkout main                 # main으로 돌아오기
git pull origin main              # 원격 최신 코드 가져오기
git merge feature/login           # 브랜치 병합
git branch -d feature/login       # 병합된 브랜치 삭제
```

---

## 5. .gitignore 관리

`.gitignore` 파일은 **버전 관리에서 제외할 파일/폴더를 지정**하는 설정 파일입니다.  
보통 빌드 결과물, 의존성, IDE 설정 파일 등을 넣습니다.  

📌 언어/플랫폼별 템플릿은 아래 사이트에서 자동 생성 가능:  
👉 [gitignore.io](https://www.toptal.com/developers/gitignore)  

예시:
```bash
# Python, Java, Node.js에 맞는 gitignore 생성
curl -s https://www.toptal.com/developers/gitignore/api/python,java,node > .gitignore
```

유용한 팁:
```bash
git rm -r --cached <file_or_folder>   # 이미 추적 중인 파일을 무시 목록에 반영
```

---

## 6. Submodule 사용법

Submodule은 **다른 Git 저장소를 현재 프로젝트 안에 포함**할 수 있게 합니다.  
(예: `Workspace` 레포 안에 `erudite-dev` 폴더를 별도의 레포로 연결)

```bash
# 서브모듈 추가
git submodule add https://github.com/<org>/<repo>.git path/to/submodule

# 서브모듈 초기화 및 업데이트
git submodule update --init --recursive

# 서브모듈 최신 코드 가져오기
git submodule update --remote

# 서브모듈 제거
git submodule deinit -f path/to/submodule
rm -rf .git/modules/path/to/submodule
git rm -f path/to/submodule
```

`.gitmodules` 파일은 서브모듈의 경로와 원격 주소를 관리합니다.  
예시:
```ini
[submodule "erudite-dev/lucid-study-java"]
    path = erudite-dev/lucid-study-java
    url = https://github.com/erudite-dev/lucid-study-java.git
```

---

## 7. 명령어 모음 (카테고리별)

### 🔹 작업 흐름
```bash
git status          # 현재 상태 확인
git diff            # 변경 사항 비교
git add <file>      # 특정 파일만 스테이징
git commit -m "msg" # 커밋
git log --oneline   # 간단 로그 보기
```

### 🔹 브랜치
```bash
git branch                  # 브랜치 목록
git checkout -b feature/x   # 새 브랜치 생성 & 이동
git switch main             # main 브랜치로 전환
git merge feature/x         # 다른 브랜치 병합
git push origin feature/x   # 원격에 브랜치 올리기
```

### 🔹 커밋 관리
```bash
git commit --amend              # 직전 커밋 메시지 수정
git reset --soft HEAD~1         # 마지막 커밋 되돌리기 (변경사항은 유지)
git reset --hard HEAD~1         # 마지막 커밋 완전 삭제 (주의!)
git revert <commit_id>          # 특정 커밋을 되돌리는 안전한 방법
```

### 🔹 임시 저장 / 복구
```bash
git stash           # 변경 사항 임시 저장
git stash list      # stash 목록 확인
git stash pop       # 가장 최근 stash 불러오기
git restore <file>  # 특정 파일 원래 상태로 복구
```

### 🔹 협업
```bash
git fetch origin             # 원격 변경 사항 가져오기
git pull --rebase origin main # 최신 main 브랜치를 현재 브랜치에 적용
git push origin <branch>     # 원격 브랜치에 푸시
```

---

## 8. 태그 & 릴리즈

```bash
git tag v1.0.0           # 버전 태그 추가
git push origin v1.0.0   # 태그 푸시
```

---

## 9. 자주 쓰는 상황별 팁

- **작업 중인데 급히 다른 브랜치로 이동해야 할 때**  
  → `git stash`로 저장 후, 돌아와서 `git stash pop`  
- **잘못된 커밋 메시지 수정**  
  → `git commit --amend -m "fix: correct typo in login message"`  
- **커밋 실수로 되돌려야 할 때**  
  → 안전하게는 `git revert <commit_id>`, 확실히 지울 땐 `git reset`  
