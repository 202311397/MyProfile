# 강민아 포트폴리오 사이트

산업정보시스템공학과 · 컴퓨터공학 복수전공 강민아의 개인 포트폴리오입니다.
품질·생산·재무 데이터에 대한 관심과, 직접 만들고 배포한 활동을 정리했습니다.

- 사이트: https://202311397.github.io/MyProfile/
- 저장소: https://github.com/202311397/MyProfile

## 사용 기술

- Hugo **0.167.0 extended**
- 테마: Localcraft (`site/themes/template/`)
- GitHub Actions + GitHub Pages (main 브랜치에 push하면 자동 배포)

## 로컬에서 실행

```bash
hugo server --source site
```

브라우저에서 http://localhost:1313/MyProfile/ 을 엽니다.

## 수정하는 파일 위치

| 바꿀 것 | 파일 |
|---|---|
| 사이트 설정, 메뉴, 푸터 | `site/hugo.yaml` |
| 홈 화면 (소개 문장, 슬라이드 사진) | `site/content/ko/_index.md` |
| 홈 관심 분야 카드 | `site/data/ko/services.yaml` |
| 소개 페이지 | `site/content/ko/about/index.md` |
| 학습 목표 카드 | `site/data/ko/values.yaml` |
| 활동 | `site/content/ko/gallery/activity1~4.md` |
| 학습 기록 | `site/content/ko/blog/*.md` |
| 연락처 | `site/content/ko/contact/index.md` |
| 버튼·안내 문구 | `site/i18n/ko.yaml` |
| 디자인 | `site/assets/css/custom.css` |
| 이미지 | `site/assets/images/`, `site/static/images/` |

## 테마를 덮어쓴 파일

테마 원본(`site/themes/template/`)은 수정하지 않고 같은 이름의 파일을 `site/layouts/`에 만들어 덮어썼습니다.

| 파일 | 변경 내용 |
|---|---|
| `site/layouts/gallery/list.html` | 반려견 Before/After 슬라이더 → 활동 카드 목록 |
| `site/layouts/partials/sections/hero.html` | 홈 첫 화면 사진 자동 슬라이드쇼 (멈춤 버튼 포함) |
| `site/layouts/partials/sections/blog-preview.html` | 홈 최근 기록 날짜를 한국어 형식으로, 3개를 같은 크기로 배치 |
| `site/layouts/partials/nav.html` | 모바일 메뉴 버튼 라벨을 한국어로 |
| `site/layouts/_default/baseof.html` | 본문 바로가기 문구를 한국어로 |
| `site/layouts/shortcodes/tabs.html`, `tab.html` | 이름 버튼으로 사진을 바꿔 보는 탭 기능 (새로 추가) |

`.github/pages_build.py`는 같은 계정의 다른 저장소 사이트(movie-lab, mini-todo) 링크가 이 사이트 홈으로 바뀌던 문제를 고쳤습니다.

## 배포 확인 방법

1. main 브랜치에 push
2. 저장소 **Actions** 탭에서 build, deploy가 모두 초록 체크인지 확인
3. 사이트를 `Ctrl + Shift + R`로 새로고침해서 변경 확인

## 출처

| 자료 | 출처 | 구분 |
|---|---|---|
| 테마 | [Localcraft](https://github.com/maciejkosiarski/localcraft) by maciejkosiarski, MIT License (`LICENSE` 유지) | 외부 |
| 캐릭터 그림 `site/assets/images/mycharacter.jpg` | ★ 직접 제작 / AI 생성(도구 이름) | ★ |
| 홈 슬라이드 사진 `sky.jpg`, `book.jpg`, `bali.jpg` | 직접 촬영 | 직접 제작 |
| 홈 슬라이드 사진 `language-training.jpg` | 직접 촬영, 함께 찍힌 친구에게 게시 동의 받음 | 직접 제작 |
| ERP·학습 기록 캡처 `site/static/images/` | 직접 캡처 (사용자 이름 등 개인정보 가림) | 직접 제작 |
| 탭 기능, 슬라이드쇼, 배포 스크립트 수정, 일부 문장 정리 | Claude(AI) 도움으로 작성 후 직접 적용·확인 | AI 도움 |