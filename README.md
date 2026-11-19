# themurlylabs.github.io

더멀리랩스 회사 웹사이트 (GitHub Pages). Play Console 조직 웹사이트 인증, 앱 개인정보처리방침·이용약관, AdMob `app-ads.txt` 용도.

## 구조

| 경로 | 내용 | 공개 URL |
|---|---|---|
| `index.html` | 회사 소개 | https://themurlylabs.github.io/ |
| `makoname/index.html` | 앱 소개 | /makoname/ |
| `makoname/privacy.html` | 개인정보처리방침 (Play Console·AdMob·앱 설정에 링크) | /makoname/privacy.html |
| `makoname/terms.html` | 이용약관 | /makoname/terms.html |
| `app-ads.txt` | AdMob 판매자 인증. 지금은 주석만 있음 | /app-ads.txt |
| `assets/` | 공통 CSS, 워드마크·아이콘 SVG (MaKoName/design/brand 복사본) | |
| `.nojekyll` | GitHub Pages가 Jekyll 처리 안 하게 | |

## 처음 올리기

1. GitHub에서 `themurlylabs` 계정 또는 조직 생성
2. 저장소 이름을 정확히 `themurlylabs.github.io` 로 생성 (Public)
3. 이 폴더에서:
   ```bash
   git init -b main
   git add .
   git commit -m "chore: initial company site"
   git remote add origin https://github.com/themurlylabs/themurlylabs.github.io.git
   git push -u origin main
   ```
4. 저장소 Settings → Pages → Source: `Deploy from a branch`, Branch `main` / `/ (root)` 확인
5. 1~2분 뒤 https://themurlylabs.github.io 접속 확인

## 웹사이트 인증 (Search Console → Play Console)

1. Search Console → 속성 추가 → **URL 접두어** → `https://themurlylabs.github.io/`
2. 인증 방법 **HTML 파일** → `googleXXXX.html` 다운로드 → 이 폴더 루트에 넣고 push
3. Search Console에서 확인
4. Play Console → 계정 세부정보 → 웹사이트 `https://themurlylabs.github.io` → 인증 요청 → Search Console에서 승인

`googleXXXX.html` 파일은 지우지 않는다 (지우면 인증이 풀림).

## 출시 전 할 일

- [ ] AdMob 앱 등록 후 `app-ads.txt`에 발급된 줄 넣기
- [ ] 개인정보처리방침 최종 검토: 실제 들어간 SDK·권한·수집 항목과 맞는지, 연령 정책(13세 이상) 확정 반영
- [ ] 한국 이용자 대상이면 한국어 개인정보처리방침 추가 검토
- [ ] 앱 설정(S7) Privacy policy·Terms 링크를 위 URL로

## 나중에 유료 도메인으로 옮길 때

1. 도메인 구매 (예: themurlylabs.com)
2. 저장소 Settings → Pages → Custom domain 입력 (`CNAME` 파일 자동 생성), DNS에 GitHub Pages 레코드 추가, Enforce HTTPS
3. Search Console에 **도메인** 속성 추가 (DNS TXT 인증)
4. Play Console 웹사이트 변경 → 재인증, 스토어 등록정보 웹사이트·개인정보처리방침 URL 변경
5. AdMob이 새 도메인의 app-ads.txt를 다시 크롤링할 때까지 며칠 걸릴 수 있음

github.io 주소는 커스텀 도메인 연결 후 자동으로 새 도메인으로 리다이렉트된다.
