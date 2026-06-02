# classday

`classday` HTML 문서를 GitHub Pages로 공유하기 위한 저장소입니다.

이 저장소는 이미 기본 설정이 끝난 상태를 기준으로 사용합니다.

- GitHub 저장소 생성 완료
- 로컬 폴더와 저장소 연결 완료
- GitHub Pages 설정 완료

이후부터는 HTML 파일을 추가하거나 수정한 뒤, Git에 올리기만 하면 자동으로 배포됩니다.

## 작업 전 알아둘 점

- 새 파일을 올린 뒤 Pages 배포 버튼을 다시 누를 필요는 없습니다.
- `git push`만 하면 GitHub Pages가 자동으로 다시 배포합니다.
- 배포 반영까지 보통 30초에서 2분 정도 걸립니다.
- 파일명은 링크 주소에 그대로 들어가므로 공백 없이 관리하는 것을 권장합니다.

권장 파일명 예시:

- `classday-photo-shoot-conti.html`
- `classday-brand-strategy-1.html`

현재처럼 언더스코어가 들어가도 동작은 합니다.

## .gitignore란?

`.gitignore`는 Git이 굳이 추적하지 않아도 되는 파일을 제외하기 위한 설정 파일입니다.

이 저장소에서는 아래 항목이 들어 있습니다.

```text
.DS_Store
```

`.DS_Store`는 macOS가 자동으로 만드는 숨김 파일이고, 웹페이지 배포에는 필요하지 않습니다.

즉, `.gitignore`를 두는 이유는 아래와 같습니다.

- 배포에 필요 없는 파일이 GitHub에 올라가는 것을 막기 위해
- `git status`에 불필요한 파일이 계속 잡히지 않게 하기 위해
- 저장소를 깔끔하게 유지하기 위해

중요한 점은 `.gitignore`는 배포 필수 설정은 아니라는 것입니다.
없어도 HTML 파일 업로드와 GitHub Pages 배포는 됩니다.
다만 관리 편의를 위해 넣어두는 것을 권장합니다.

## 기본 작업 순서

### 1. HTML 파일 추가 또는 수정

이 폴더 안에서 HTML 파일을 새로 만들거나 기존 파일을 수정합니다.

예시:

- 새 파일 추가: `new-page.html`
- 기존 파일 수정: `classday-photo-shoot-conti.html`

### 2. 로컬에서 먼저 확인

가장 간단한 방법:

```bash
open 파일명.html
```

예시:

```bash
open classday-photo-shoot-conti.html
```

또는 Finder에서 HTML 파일을 더블클릭해도 됩니다.

### 3. 변경 내용을 GitHub에 업로드

터미널에서 아래 명령을 순서대로 실행합니다.

> macOS에서 VS Code를 쓰는 경우, `⌘ + J`를 누르면 터미널이 열립니다.

> `⌘ + /`를 누르면 선택한 코드나 줄을 주석 처리하거나 주석 해제할 수 있습니다.

> 또한 `⌘ ⇧ P`를 누른 뒤 `Developer: Reload Window`를 선택하면 개발자 창을 포함한 VS Code 창을 새로고칠 수 있습니다.

```bash
cd /Users/imac/Desktop/classday
git add .
git commit -m "작업 내용 설명"
git push
```

커밋 메시지 예시:

```bash
git commit -m "Add new landing page"
git commit -m "Update classday shooting script"
```

### 4. 링크 접속

배포가 끝나면 아래 형식으로 접속할 수 있습니다.

메인 주소:

```text
https://ssinaz-creator.github.io/classday.day/
```

개별 HTML 주소:

```text
https://ssinaz-creator.github.io/classday.day/파일명.html
```

GitHub Pages는 파일명을 그대로 URL로 쓰기 때문에, 파일명을 바꾸면 URL도 자동으로 바뀝니다.

- 권장: `-`(하이픈) 사용
- 가능: `_`(언더스코어) 사용

예시:

```text
https://ssinaz-creator.github.io/classday.day/classday-photo-shoot-conti.html
https://ssinaz-creator.github.io/classday.day/classday-brand-strategy_1.html
https://ssinaz-creator.github.io/classday.day/classday-shooting-script.html
```

## 새 파일을 추가했을 때 링크 찾는 법

예를 들어 `new-page.html` 파일을 만들고 `git push`까지 끝냈다면 접속 주소는 아래와 같습니다.

```text
https://ssinaz-creator.github.io/classday.day/new-page.html
```

즉, 아래 규칙으로 생각하면 됩니다.

```text
https://ssinaz-creator.github.io/classday.day/파일명.html
```

## 자주 쓰는 명령어

현재 변경 상태 확인:

```bash
git status
```

파일 열기:

```bash
open 파일명.html
```

업로드:

```bash
git add .
git commit -m "작업 내용 설명"
git push
```

## 자주 생기는 상황

### 1. 새 파일을 올렸는데 바로 안 열릴 때

- 아직 배포 중일 수 있습니다.
- 1~2분 정도 기다린 뒤 다시 접속합니다.

### 2. 링크가 404로 뜰 때

아래를 확인합니다.

- 파일명이 정확한지
- 대소문자가 링크와 같은지
- `git push`까지 끝났는지

### 3. 수정했는데 예전 화면이 보일 때

- 브라우저 새로고침을 다시 해봅니다.
- 필요하면 강력 새로고침을 합니다.

### 4. Pages 설정을 다시 눌러야 하는지

아니요. 한 번 설정이 끝난 뒤에는 매번 다시 누를 필요 없습니다.

## 현재 파일 목록 예시

- `classday_photo-shoot-conti.html`
- `classday-brand-strategy_1.html`
- `classday-brand-strategy_2.html`
- `classday-character-strategy_0.html`
- `classday-character-strategy_1.html`
- `classday-character-strategy_2.html`
- `classday-character-strategy_3.html`
- `classday-progress-design-process_1.html`
- `classday-shooting-script.html`

## 추천 작업 방식

매번 아래 순서만 지키면 됩니다.

1. HTML 파일 수정 또는 추가
2. 브라우저에서 로컬 확인
3. `git add .`
4. `git commit -m "작업 내용 설명"`
5. `git push`
6. GitHub Pages 링크 확인