---
title: "Git 기본 명령 정리"
description: "수업에서 배운 Git 흐름과 사이트를 만들며 헷갈렸던 것"
date: 2026-10-21
tags: ["Git"]
---

## 전체 흐름

```
작업 폴더(wd) --add--> stage --commit--> 내 repo --push--> 원격 repo(GitHub)
```

## 시작하기

| 명령 | 하는 일 |
|---|---|
| `git init .` | 지금 폴더를 Git 저장소로 만듦 |
| `git clone 주소` | 원격 저장소를 내려받기 (원격 연결도 자동) |
| `git remote add origin 주소` | 내 저장소에 원격 주소를 연결 |
| `git remote -v` | 연결된 원격 주소를 확인 |

## 기록하고 올리기

| 명령 | 하는 일 |
|---|---|
| `git status` | 무엇이 바뀌었고 무엇이 stage에 있는지 확인 |
| `git add .` | 바뀐 파일을 전부 stage에 올림 |
| `git commit -m "메시지"` | stage에 있는 것을 기록으로 저장 |
| `git push origin main` | 기록을 GitHub의 main 브랜치에 올람 |
| `git log` | 커밋 기록 확인 |
| `git show` | 커밋 하나의 자세한 변경 내용 |

`.gitignore`에 적은 파일은 Git이 무시

## 브랜치

| 명령 | 하는 일 |
|---|---|
| `git switch -c 이름` | 새 브랜치를 만들고 그 브랜치로 이동 |
| `git switch 이름` | 다른 브랜치로 이동 |
| `git branch -M 이름` | 지금 브랜치의 이름을 바꿈 |
| `git push origin 이름` | 그 브랜치를 GitHub에 올림 |

## 정적 웹페이지 배포

```
git init .
git remote add origin https://github.com/202311397/.........
git add .
git commit -m "init"
git push origin main
```

GitHub 저장소 **Settings → Pages**에서 배포할 브랜치를 main으로 설정하면 사이트 열림

## 사이트를 만들며 헷갈렸던 것

- `git rm`은 파일 삭제와 add를 같이 해 준다.
- `mkdir`은 폴더, `touch`는 빈 파일
- 이미 push한 커밋 메시지를 `--amend`로 고치면 일반 push가 거부된다. 이때는 `git push --force-with-lease`