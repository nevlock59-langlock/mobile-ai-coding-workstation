# Android Phone as an AI Coding Workstation

> Termux + Gemini CLI + GitHub + Vercel mobile onboarding guide

This repository is a beginner-friendly guide for building a lightweight mobile AI coding workflow on Android.

The goal is not to replace a full desktop IDE.
The goal is to create a small code edit-check cycle on a phone.

## Tested Environment

- Samsung Galaxy S23
- Android
- Termux
- Gemini CLI
- GitHub
- Vercel
- Vite + React

## Quick Setup

```bash
pkg update && pkg upgrade -y
pkg install git nodejs -y
mkdir -p ~/workbox
cd ~/workbox
npm install -g @google/gemini-cli
gemini
```

## Useful Alias

```bash
echo 'alias gemw="cd ~/workbox && gemini"' >> ~/.bashrc
source ~/.bashrc
```

After this, run:

```bash
gemw
```

## Run a Vite Project

```bash
npm install
npm run dev -- --host 0.0.0.0
```

Open the Local or Network URL in your mobile browser.

## GitHub Push Workflow

```bash
git status
git add .
git commit -m "update"
git push
```

## Vercel Deploy Workflow

Connect your GitHub repository to Vercel.
After that, every git push can trigger an automatic deployment.

## Good Use Cases

- Small UI updates
- CSS tweaks
- Mobile layout checks
- README editing
- Quick deployment QA
- Small feature patches

## Limitations

- Large refactoring
- Long debugging sessions
- Multi-file comparison
- Heavy desktop-style workflows

## Conclusion

This setup is not a full mobile IDE.

It is a lightweight workflow that connects AI agent, Git, cloud deploy, and mobile QA for fast code edit-check cycles on Android.

## Keywords

Android, Termux, Gemini CLI, GitHub, Vercel, Mobile Development, AI Coding Agent
