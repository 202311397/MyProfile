---
title: "Firebase 환경변수 설정하기"
description: ".env.local 파일과 GitHub Repository Secrets를 이용한 Firebase 환경변수 관리 및 배포 오류 해결"
date: 2026-10-16
image: "/images/blog/firebase-secrets.png"
tags: ["React", "Firebase", "GitHub Actions"]
---

React + Firebase TODO 앱을 만들면서 Firebase 설정값을 `.env.local` 파일에 따로 넣음.GitHub Actions로 배포하니 빌드가 실패

## 왜 설정값을 따로?

Firebase에 연결하려면 API 키 같은 설정값 4개가 필요. 이걸 코드에 직접 쓰면 저장소에 그대로 올라가서 누구나 볼 수 있음. 그래서 `.env.local`이라는 파일에 따로 넣고 이 파일은 저장소에 올리지 않음.

## 원인

`.env.local`은 내 컴퓨터에만 있는 파일. 그래서 GitHub Actions가 빌드할 때는 Firebase 값을 찾을 수 없음.

## 해결

1. 저장소 **Settings → Secrets and variables → Actions**에 같은 값을 등록.
2. workflow에서 그 값을 불러와 빌드할 때 쓰도록 함.

다시 push하니 빌드와 배포가 정상

## 정리

| 어디서 실행하나 | 설정값 위치 |
|---|---|
| 내 컴퓨터 (`npm run dev`) | `.env.local` |
| GitHub Actions (배포) | Repository Secrets |
