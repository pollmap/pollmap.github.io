# Security Policy

## 보안 이슈 발견 시

개인 포트폴리오 허브(정적 사이트)이므로 심각한 보안 표면은 작지만, 혹시 발견하신다면:

1. **공개 이슈로 등록하지 마세요** (GitHub Issues).
2. GitHub 계정 [@pollmap](https://github.com/pollmap)에 private security advisory를 열어주세요:
   `https://github.com/pollmap/pollmap.github.io/security/advisories/new`
3. 구체적 재현 단계, 영향 범위, 제안하는 수정 방향을 포함해 주세요.

## 대응 시간

- **초기 응답**: 72시간 이내
- **패치 배포**: 심각도에 따라 1~14일

## 범위

이 저장소에서 보안 검토 범위:

- `index.html` XSS/CSP 이슈
- `style.css` / `deploy.yml` 의도치 않은 외부 요청
- `projects.json` 의도치 않은 리디렉션/피싱 링크

**범위 밖**:
- 링크된 외부 repo (각 프로젝트의 SECURITY.md 참조)
- GitHub Pages 인프라 자체 (GitHub Security 팀 대상)

## 보안 설계 원칙

본 저장소는 다음을 준수합니다:

- **정적 전용** — 서버 사이드 코드/DB/API 없음
- **CSP 헤더** — `index.html`에 meta로 명시
- **외부 의존 최소** — Google Fonts 2개 외 CDN 호출 없음
- **secret 금지** — API 키, 토큰, 자격증명 저장 금지 (`.gitignore`로 차단)
- **HTTPS 강제** — GitHub Pages 기본값

## 보안 커밋 체크리스트

커밋 전 확인:

- [ ] `.env`, `.pem`, credentials 파일 포함 안 됨 (`git status`)
- [ ] `index.html`에 인라인 secret 없음
- [ ] `projects.json` URL 전부 신뢰 가능한 도메인
- [ ] 외부 fetch 추가 시 CSP `connect-src` 업데이트
