# 결담 브로우 관찰기 — 블로그형 눈썹문신 에디토리얼

이 ZIP을 풀어 **안의 파일 전체**를 한 GitHub 저장소의 최상위에 올리세요. 첫 화면은 긴 포스팅이며 각 글은 `/blog/글주소/`에 저장됩니다. 사진은 제작용 자료 이미지이며 글은 상담 장면을 가정해 에디터의 기준을 설명합니다. 실제 고객 방문 후기나 시술 결과를 나타내지 않습니다.

## Cloudflare Pages 연결

Workers & Pages → Create application → Pages → Connect to Git에서 저장소를 연결합니다. Framework preset `None`, Build command **비움**, Build output directory `.`, Production branch `main`을 사용합니다.

## 새 글 추가

`content/example-post.json`을 복사해 `content/posts/new-post.json`을 만들고 `slug`를 `new-post`로 맞춥니다. 본문은 `body` 배열에 문단별로 작성합니다. 사진은 `assets/images/`의 파일명을 확장자 없이 `image`, `image2`에 적습니다. 필요하면 `comments` 배열에 `name`, `text`를 적어 고정 댓글을 편집할 수 있습니다. 방문자용 댓글 작성 폼은 없습니다.

`main`에 push하면 GitHub Actions가 첫 화면과 `/blog/new-post/` 파일을 재생성해 커밋합니다. Actions 쓰기가 허용되지 않는 저장소에서는 `python3 scripts/build.py`를 실행하고 생성된 `index.html`, `blog/`를 직접 커밋하세요.

이름과 색은 `site.json`, 스타일은 `assets/style.css`, 글 내용은 `content/posts/*.json`에서 수정합니다.
