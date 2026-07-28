# 스펙터 (Spector) — 사업자/조직용 웹사이트

Google Play 스토어의 **조직(사업자) 개발자 계정 심사**를 통과하기 위한 공식 웹사이트입니다.
정적 사이트(HTML/CSS/JS)로 제작되어 **GitHub Pages에서 무료로 호스팅**할 수 있습니다.

Google Play는 조직 계정을 심사할 때 실제로 접속 가능한 웹사이트, 명확한 **사업자 소개**,
**앱 소개**, **개인정보처리방침**, 일관된 **연락처**를 확인합니다. 이 사이트는 그 요소를
모두 포함하도록 구성했습니다.

## 페이지 구성

| 파일 | 내용 |
|------|------|
| `index.html` | 메인 랜딩 — 앱 소개, 주요 기능, 이용 방법, **사업자 소개**, FAQ, 연락처 |
| `privacy.html` | **개인정보처리방침** (Play Store 필수) |
| `terms.html` | 서비스 이용약관 |
| `support.html` | 고객지원 센터 / FAQ / 연락처 |
| `assets/` | CSS, JS, 로고(SVG) |
| `robots.txt`, `.nojekyll` | 검색엔진 및 GitHub Pages 설정 |

## GitHub Pages로 배포하기 (무료 호스팅)

1. 이 저장소의 GitHub 페이지에서 **Settings → Pages** 로 이동합니다.
2. **Build and deployment → Source** 를 **Deploy from a branch** 로 선택합니다.
3. Branch 를 이 브랜치(또는 병합 후 `main`)로, 폴더는 `/ (root)` 로 지정하고 **Save**.
4. 잠시 후 아래 주소로 사이트가 공개됩니다:

   ```
   https://kk119kr.github.io/Qisney_area/
   ```

5. 이 주소를 **Google Play Console → 개발자 계정 → 웹사이트** 및 앱 스토어 등록정보의
   **개인정보처리방침 URL**(`.../privacy.html`)에 입력하세요.

> 참고: `index.html` 안의 JSON-LD `url`/`logo` 값도 실제 배포 도메인에 맞춰 이미 설정되어 있습니다.
> 사용자 정의 도메인을 연결하면 해당 도메인으로 바꿔 주세요.

## Play Store 제출 전 채워 넣을 항목 ✍️

심사 통과 확률을 높이려면 아래 **자리표시(placeholder)** 정보를 실제 값으로 교체하세요.
현재는 정직하게 "정식 출시 시 갱신"이라고 표기해 두었습니다.

- **사업자 등록 정보**: 상호, 사업자등록번호, 대표자명, 주소
  - `index.html` → `#company` 섹션의 "사업자 정보" 카드
- **개인정보 수탁 업체**: 실제 사용하는 클라우드/분석 도구 상호
  - `privacy.html` → "5. 개인정보 처리의 위탁"
- **앱 실제 기능/설명**: Play Store 등록정보의 앱 설명과 **내용이 일치**하도록 맞추세요
  - `index.html` → `#product`, `#features`
- **연락처 이메일**: 현재 `hyhk230128@gmail.com` 로 통일되어 있습니다. 변경 시 전체 파일에서 교체.

> ⚠️ 중요: 웹사이트의 앱 설명과 사업자명이 **Play Console에 등록한 정보와 일치**해야
> 심사에서 불일치로 반려되지 않습니다.

## 로컬에서 미리보기

```bash
# 저장소 루트에서
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## 기술 사양

- 순수 정적 사이트 (빌드 과정 불필요, 의존성 없음)
- 반응형 레이아웃 (모바일/데스크톱)
- 라이트/다크 모드 자동 대응
- 시맨틱 HTML + Organization JSON-LD 구조화 데이터
- 접근성 고려(aria 속성, 키보드 접근 가능한 네비게이션)
