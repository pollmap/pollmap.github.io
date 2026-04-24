# Contributing

이 저장소는 **개인 포트폴리오 허브**이므로 일반적 외부 기여는 받지 않습니다. 다만 아래 유형의 제보/제안은 환영합니다.

## 환영하는 기여

- **오타·깨진 링크 제보** — GitHub Issue에 간단히
- **`projects.json` 실제 repo URL 변경사항** — repo 이름 변경/archive 시 PR 또는 Issue
- **접근성 개선** — alt 누락, 키보드 네비게이션, 색 대비 등
- **성능 이슈** — Lighthouse 스코어 하락 재현 가능한 경우
- **보안 이슈** — [SECURITY.md](SECURITY.md) 참조 (public issue 금지)

## 받지 않는 기여

- 디자인 전면 교체 제안 (개인 취향 영역)
- 새 프로젝트 카드 추가 제안 (`projects.json`은 저자 본인 프로젝트만)
- 이력/자기소개 텍스트 수정 제안 (사실 오류가 아닌 경우)
- 기능 추가 (예: 댓글 시스템, 검색, DB 연동) — 정적 전용 유지

## PR 규칙

혹시 PR 을 보내주실 경우:

1. **branch**: `fix/<short-description>` 또는 `chore/<short>`
2. **commit**: Conventional Commits 포맷 (`fix:`, `chore:`, `docs:`)
3. **scope 최소화** — 한 PR = 한 목적
4. **테스트**: 로컬에서 `python3 -m http.server 8000`로 동작 확인
5. **linter**: 불필요 (vanilla HTML/CSS)

## 커밋 전 체크

```bash
# projects.json 유효성
python3 -c "import json; json.load(open('projects.json', encoding='utf-8'))"

# 링크 유효성 (선택)
# grep -oE 'https?://[^"]+' index.html | xargs -I {} curl -sI {} | grep -i "^HTTP"

# grep ban (개인 정보/VPS IP 방지) — 실제 패턴은 저자 환경에 맞춰 치환
# 예: <VPS-IP>, <USER-HANDLE>, 로컬 사용자명(C:\Users\<NAME>), private key 등
# 저자 환경 보안 규정은 ~/.claude 내부에 별도 정의됨
! grep -rE "<VPS-IP>|<USER-HANDLE>|C:[\\/]Users[\\/]<USERNAME>" . --exclude-dir=.git
```

## 라이선스

기여분은 이 저장소의 라이선스([LICENSE](LICENSE))에 따라 배포됩니다:

- 소스 코드 = MIT
- 이력/설명 텍스트 = CC BY 4.0

질문은 [@pollmap](https://github.com/pollmap) DM/Issue로.
