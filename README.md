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
