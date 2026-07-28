# Qisney market — SPECTR(스펙터) 사업자/조직 웹사이트

Google Play **조직(사업자) 개발자 계정 심사** 통과를 위한 Qisney market의 공식
웹사이트입니다. Qisney market이 개발·운영하는 이상형체 탐지 시뮬레이션 앱
**SPECTR(스펙터)** 를 소개합니다. 정적 사이트(HTML/CSS/JS)로 제작되어
**GitHub Pages에서 무료로 호스팅**할 수 있습니다.

> SPECTR 앱 소스는 별도 저장소(`kk119kr/Ghost`)에 있습니다. 이 저장소는 심사에
> 필요한 웹사이트만 담당합니다.

## 페이지 구성

| 파일 | 내용 |
|------|------|
| `index.html` | 메인 랜딩 — 앱 소개 · 실제 스크린샷 갤러리 · 주요 기능 · 이용 방법 · **사업자 소개** · FAQ · 연락처 |
| `privacy.html` | **개인정보처리방침** (Play Store 필수 — SPECTR는 서버 없이 기기 내에서만 처리) |
| `terms.html` | 서비스 이용약관 (엔터테인먼트 시뮬레이션임을 명시) |
| `support.html` | 고객지원 센터 / FAQ / 연락처 |
| `assets/img/screenshots/` | 실제 앱 화면 스크린샷 (홈, EMF, 고스트박스, EVP, 오빌러스, SLS, 설정) |
| `assets/img/app-icon.png` | SPECTR 실제 앱 아이콘 |

## GitHub Pages로 배포하기 (무료 호스팅)

1. 이 저장소의 GitHub 페이지에서 **Settings → Pages** 로 이동합니다.
2. **Build and deployment → Source** 를 **Deploy from a branch** 로 선택합니다.
3. Branch 를 이 브랜치(또는 병합 후 `main`)로, 폴더는 `/ (root)` 로 지정하고 **Save**.
4. 잠시 후 아래 주소로 사이트가 공개됩니다:

   ```
   https://kk119kr.github.io/Qisney_area/
   ```

5. 이 주소를 **Google Play Console → 개발자 계정(goldenbeard92@gmail.com) → 웹사이트**
   및 앱 스토어 등록정보의 **개인정보처리방침 URL**(`.../privacy.html`)에 입력하세요.

## Play Console 등록 정보 (SPECTR 앱 저장소 `docs/play-store.md` 기준 복붙용)

앱 저장소에 이미 정리되어 있던 스토어 등록 정보를 참고용으로 옮겨둡니다.
실제 제출 시 Play Console에 그대로 입력하면 됩니다.

- **앱 이름(스토어 제목)**: `SPECTR — 이상형체 탐지기`
- **패키지명**: `com.quinnie92.spectr` (공개 후 변경 불가)
- **카테고리**: 엔터테인먼트 (또는 시뮬레이션 게임)
- **콘텐츠 등급**: 경미한 공포 테마 → 대략 12세 등급 예상
- **데이터 보안 설문**: 데이터 수집 없음 / 제3자 공유 없음 / 위치는 기기 내 처리로 "수집 안 함"
- **개인정보처리방침 URL**: 이 사이트의 `privacy.html`

짧은 설명·전체 설명·출시노트 전문은 앱 저장소의 `docs/play-store.md`를 참고하세요.

## Play Store 제출 전 확인할 항목 ✍️

- **사업자 등록 정보**: 사업자등록번호 등 추가 정보가 확정되면
  `index.html`의 "사업자 정보" 카드와 `privacy.html`의 책임자 표를 갱신하세요.
- **그래픽 자산**: 피처 그래픽(1024×500), 고해상 아이콘(512×512)은 별도 준비가 필요합니다.
- **연락처**: 현재 `goldenbeard92@gmail.com`(Play 콘솔 계정)으로 통일되어 있습니다.

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
- 반응형 레이아웃 (모바일/데스크톱), 라이트/다크 모드 자동 대응
- 실제 앱 화면을 웹 빌드에서 렌더링해 캡처한 스크린샷 사용
- 시맨틱 HTML + Organization JSON-LD 구조화 데이터
- 접근성 고려(aria 속성, 키보드 접근 가능한 네비게이션)
