---
title: "GitHub Actions 빌드 실패 해결"
description: "YAML 한 줄 오류로 배포가 멈췄을 때 로그로 원인을 찾은 과정"
date: 2026-11-02
tags: ["GitHub Actions", "Hugo"]
---

학습 기록 글을 올렸는데 Actions에 빨간 X가 떴음. 사이트도 바뀌지 않음.

## 로그 확인

실패한 Build 단계를 열어 보니 줄 생김

```
git-learning.md:3:39: value is not allowed in this context
```

파일 이름과 줄 번호(3번째 줄 39번째 글자)까지 알려 줌

## 원인

글 설정 부분에서 `description`과 `date`가 한 줄에 붙어 있었음

```yaml
description: "사이트를 만들면서 Git 활용 정"     date: 2026-10-21
```

YAML은 한 줄에 항목 하나만 쓸 수 있어서 Hugo가 이 파일을 읽지 못함.

## 해결

`date:` 앞에서 줄을 나누고 다시 push. 초록 체크가 뜨고 글도 정상

## 정리

- 빌드가 실패하면 로그에서 **파일 이름과 줄 번호**부터 찾기
- 빌드가 실패해도 사이트는 마지막으로 성공한 상태로 남음
- 설정 부분(`---` 사이)은 한 줄에 항목 하나.