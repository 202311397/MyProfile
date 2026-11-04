---
title: "Vue 프로젝트 배포: 수동 빌드와 자동 배포 비교"
description: "같은 프로젝트를 두 방식으로 배포해 보며 알게 된 차이"
date: 2026-10-13
tags: ["Vue", "GitHub Pages"]
---

수업 과제로 같은 Vue 프로젝트(movie-lab)를 두 가지 방식으로 배포

## 왜 빌드가 필요한가

브라우저는 `.vue` 파일을 바로 읽지 못함. `npm run build`를 하면 HTML, CSS, JavaScript로 바뀐 결과물이 `dist` 폴더에 생김.

## 두 방식 비교

| | 수동 빌드 | Actions 자동 배포 |
|---|---|---|
| 저장소에 올리는 것 | 빌드 결과물 | 프로젝트 원본 |
| 수정할 때 | 직접 다시 빌드해서 올림 | push만 하면 자동 |
| 처음 설정 | 간단 | workflow 파일 필요 |
| 결과 | [movie-lab](https://202311397.github.io/movie-lab/) | [movie-lab-2](https://202311397.github.io/movie-lab-2/) |

## 막혔던 것

배포했더니 화면이 제대로 나오지 않음. GitHub Pages 주소는 `202311397.github.io/movie-lab/`처럼 저장소 이름이 뒤에 붙는데 Vite의 `base` 경로가 이 이름과 맞지 않아서 파일을 못 찾은 것임. `base`를 저장소 이름에 맞게 고치니 정상으로 보임.

## 정리

- 처음 한 번은 수동이 간단하지만 자주 고치는 프로젝트라면 자동 배포가 훨씬 편함
- GitHub Pages에 올릴 때는 저장소 이름이 주소에 들어간다는 걸 생각하고 경로를 맞추기
- 지금 포트폴리오 사이트도 같은 방식(Actions)으로 배포