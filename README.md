# 안드로이드 폰으로 AI 코딩 작업대 만들기

> Android Phone as an AI Coding Workstation  
> Termux + Gemini CLI + GitHub + Vercel 모바일 개발환경 온보딩 가이드

이 문서는 안드로이드 스마트폰에서 Termux, Gemini CLI, GitHub, Vercel을 연결해  
가벼운 모바일 AI 코딩 워크플로를 만드는 과정을 정리한 온보딩 가이드입니다.

단순 설치법이라기보다,  
“폰 하나로 작은 웹 프로젝트를 수정하고, 확인하고, 배포하는 루프”를 만드는 데 초점을 둡니다.

---

## Who is this for?

이 문서는 이런 사람에게 적합합니다.

- Gemini CLI를 처음 써보는 사람
- Termux에서 개발환경을 만들어보고 싶은 사람
- 노트북 없이 모바일에서 작은 웹 프로젝트를 수정해보고 싶은 사람
- GitHub와 Vercel을 연결해 자동 배포 흐름을 경험해보고 싶은 사람
- AI coding agent를 실제 작업 루프로 써보고 싶은 사람

---

## Tested Environment

제가 테스트한 환경은 다음과 같습니다.

- Device: Samsung Galaxy S23
- OS: Android
- Terminal: Termux
- AI Coding Agent: Gemini CLI
- Version Control: Git / GitHub
- Deploy: Vercel
- Frontend Example: Vite + React

---

## Overall Workflow

전체 흐름은 다음과 같습니다.

```text
Android Phone
  ↓
Termux
  ↓
Gemini CLI
  ↓
Local Project
  ↓
Git / GitHub
  ↓
Vercel
  ↓
Mobile Browser QA

## First 10-Minute Goal

처음부터 큰 앱을 만들려고 하기보다, 아래 목표 하나만 먼저 성공시키는 것을 추천합니다.

1. Termux에서 프로젝트 폴더로 이동한다.
2. Gemini CLI를 실행한다.
3. README나 작은 문구 하나를 수정한다.
4. `npm run dev -- --host 0.0.0.0`으로 로컬 실행한다.
5. 모바일 브라우저에서 결과를 확인한다.
6. GitHub에 push한다.
7. Vercel 배포 결과를 다시 모바일에서 확인한다.

처음 목표는 “멋진 앱 만들기”가 아니라,  
**수정 → 확인 → 저장 → 배포** 루프를 한 번 끝까지 돌려보는 것입니다.

## Quick Setup

### 1. Install Termux

- Install Termux from F-Droid
- Launch Termux once

### 2. Install basic packages

```bash
pkg update && pkg upgrade -y
pkg install git nodejs -y
```

### 3. Install Gemini CLI

```bash
npm install -g @google/gemini-cli
```

### 4. Create workspace

```bash
mkdir -p ~/workbox
cd ~/workbox
```

### 5. Start Gemini CLI

```bash
gemini
```

이후 Gemini CLI 안에서 프로젝트 생성/수정 작업을 진행할 수 있습니다.

## Run a Vite Project on Android

Vite 기반 프로젝트라면 프로젝트 폴더 안에서 아래 명령어를 실행합니다.

```bash
npm install
npm run dev -- --host 0.0.0.0
```

실행 후 Termux에 표시되는 주소를 모바일 브라우저에서 엽니다.

```text
Local:   http://localhost:5173/
Network: http://xxx.xxx.xxx.xxx:5173/
```

처음에는 배포보다 로컬 실행을 먼저 확인하는 것이 좋습니다.  
로컬에서 화면이 뜨면 그다음 GitHub push와 Vercel 배포로 넘어갑니다.

## GitHub Push Workflow

수정한 내용을 GitHub에 올리는 기본 흐름입니다.

```bash
git status
git add .
git commit -m "update"
git push
```

## Vercel Deploy Workflow

Vercel에서 GitHub repository를 연결하면, 이후에는 GitHub에 push할 때마다 자동으로 배포됩니다.

```text
Code 수정
  ↓
git add / commit / push
  ↓
GitHub 반영
  ↓
Vercel 자동 배포
  ↓
모바일 브라우저에서 확인
```

모바일에서 개발할 때는 배포 후 실제 스마트폰 브라우저에서 바로 확인할 수 있다는 점이 큰 장점입니다.

## Useful Aliases

자주 쓰는 명령어는 alias로 줄여두면 편합니다.

```bash
echo 'alias gemw="cd ~/workbox && gemini"' >> ~/.bashrc
source ~/.bashrc

이후 어디서든 아래처럼 입력하면 됩니다.

```bash
gemw

그러면 `~/workbox` 폴더로 이동한 뒤 Gemini CLI가 실행됩니다.
