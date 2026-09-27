# 결담 브로우 관찰기 — 눈썹문신 에디토리얼 예시

블로그/카페 형태의 **글 화면**입니다. 첫 화면 `index.html`은 최신 글 본문이며, 각 글은 `/blog/slug/`에 쌓입니다. 사진은 이 프로젝트를 위해 생성한 연출 이미지입니다. 글 속 뷰티샵, 상담 장면과 평가는 **가상 시나리오**이며 실제 방문이나 시술 결과를 주장하지 않습니다.

## GitHub → Cloudflare Pages

ZIP을 풀어 내용물 전체를 별도 GitHub 저장소의 최상위에 올립니다. Cloudflare Pages에서 해당 저장소를 연결하고 Framework preset `None`, Build command **비움**, Build output directory `.` 및 Production branch `main`을 선택합니다. 첫 배포에는 별도 설치가 필요하지 않습니다.

## 글 추가하기

`content/example-post.json`을 참고해 `content/posts/new-post.json`을 만들고 `slug`를 `new-post`로 맞춥니다. 제목, 카테고리, `YYYY-MM-DD` 날짜, 본문 문단, `image`와 `image2`를 바꿉니다. 이미지는 `assets/images/`에 있는 webp 파일명을 확장자 없이 적거나 새 이미지를 해당 폴더에 추가하세요. 글 내용이 실제 업체에 관한 경우 확인 가능한 사실과 사진 사용 권한을 먼저 확인하세요.

`main`에 push하면 포함된 GitHub Actions가 `index.html`과 `/blog/new-post/`를 생성해 커밋합니다. Actions 쓰기 권한이 없는 저장소에서는 `python3 scripts/build.py`를 로컬에서 실행한 뒤 생성된 파일을 직접 커밋합니다.

색상과 이름은 `site.json`, 레이아웃은 `assets/style.css`, 글 원본은 `content/posts/*.json`입니다. 댓글과 공감은 현재 방문자의 브라우저에만 저장되는 데모 기능입니다.
