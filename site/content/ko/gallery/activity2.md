---
title: "React + Firebase TODO 관리 앱"
description: "React와 Firebase로 로그인과 데이터 저장이 되는 TODO 앱을 만들고 GitHub Pages에 배포했습니다."
date: 2026-10-15
period: "2026.10"
status: "완료"
---

## 활동 시기와 진행 상태

2026년 10월 13일 (개인 실습), 완료

## 활동 목적

실습을 통해 React와 Firebase를 활용한 TODO 관리 웹앱을 만들어 보았습니다. 개발 환경을 설정하고 Firebase를 연결한 뒤 GitHub Pages에 배포하는 과정을 경험했습니다.

## 본인 역할과 기여 범위

개인 실습으로 진행했으며, React 개발 환경 설정부터 Firebase 연결, GitHub 저장소 관리와 배포까지 직접 진행했습니다.

## 수행 과정과 선택 이유

- **개발 환경**: Node.js와 npm을 사용해 개발 환경을 구성하고 `npm ci` 명령어로 필요한 패키지를 설치했습니다. 정해진 버전의 패키지를 설치해 다른 환경에서도 동일하게 실행할 수 있도록 했습니다.
- **Firebase 연결**: Firebase 설정값을 `.env.local` 파일로 관리하고 GitHub Actions에서는 Repository Secrets에 등록하여 배포 과정에서 사용할 수 있도록 설정했습니다. 설정값을 코드에 직접 작성하지 않고 저장소에도 노출되지 않게 관리하기 위해서였습니다.
- **로그인 기능**: Firebase Authentication을 이용해 이메일과 비밀번호 방식의 로그인을 설정했습니다.
- **데이터 저장**: Firestore를 연결하고 `firestore.rules`를 통해 데이터 접근 규칙을 설정했습니다. 사용자 데이터가 다른 사람에게 함부로 공개되지 않도록 접근 권한을 관리하는 과정이었습니다.
- **배포**: GitHub Actions를 이용해 코드를 push하면 자동으로 빌드하고 GitHub Pages에 배포되도록 설정했습니다.

## 산출물과 결과 설명

- 사이트: [202311397.github.io/mini-todo](https://202311397.github.io/mini-todo/)
- 저장소: [github.com/202311397/mini-todo](https://github.com/202311397/mini-todo)

React와 Firebase를 연결한 할 일 관리 앱을 완성하고 GitHub Pages에 배포했습니다. 주요 기능은 다음과 같습니다.

- 회원가입 및 로그인
- 할 일 추가, 완료 및 삭제
- 로그인한 사용자별 데이터 저장 및 불러오기

## 학습 결과와 개선 방향

- **배운 점**: 처음에는 React로 화면만 만들면 앱이 완성되는 줄 알았는데 실제로 데이터를 저장하고 로그인 기능을 사용하려면 Firebase 같은 서비스와 연결해야 한다는 것을 알게 되었습니다. 또한 배포할 때도 환경변수와 경로 설정이 중요하다는 것을 배웠습니다.
- **어려웠던 점**: `.env.local`은 내 컴퓨터에만 있는 파일이라 GitHub Actions에서 빌드할 때는 Firebase 값이 전달되지 않아 실패했습니다. 같은 값을 Repository Secrets에 등록하고 workflow에서 불러오도록 수정해 해결했습니다. Vite의 배포 경로 문제도 발생해 `base` 설정을 확인하면서 해결했습니다.
- **개선 방향**: 이번에는 일반적인 TODO 관리 앱을 만들었지만 나중에는 품질 데이터를 입력하고 불량률을 확인할 수 있는 앱으로 발전시켜 보고 싶습니다.