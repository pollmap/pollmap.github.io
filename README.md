# pollmap.github.io

> 이찬희 (Chan-hee Lee) · 충북대 경영 24학번 · KDA 4기 (2026.5.7~8.21)
> Financial Data & Research Automation Portfolio
> 28.6 졸업 · 단일 채널 빌드로그

`https://pollmap.github.io/` — 면접관이 단일 URL 하나로 5분 내 정체성·궤도·관제 전부 열람 가능한 포트폴리오 허브.

## 디자인 톤

**ODYSSEY BEYOND** — Kubrick 2001: A Space Odyssey × Palantir Foundry 기하학.

| 레이어 | 적용 |
|---|---|
| 색조 | `--void` `#000` · `--starlight` `#f5f5f5` · `--orbital` `#1565c0` · `--hal` `#ff0000` |
| 폰트 | Orbitron (display) · Pretendard Variable (sans) · JetBrains Mono (mono) |
| 후처리 | `filter: contrast(1.04) saturate(0.85)` — ENR 은잔류 (silver-retention) |
| 모션 | starfield 3-layer drift (480/720/600s) · station 회전 360s · sun-line 90s · glacial-fade 4-8s |
| 인터랙션 | airlock CTA — 8s seal pressurization on hover |

세부 모티프: HAL 9000 mark (4s 펄스), one-point perspective, conic-gradient station spokes, CSS-only 우주.

## 4-Section 구조

| 섹션 | 제목 | 콘텐츠 |
|---|---|---|
| §01 | **DESTINATIONS** | Featured 5 — `nexus-finance-mcp` · `cufa-equity-report` · `equity-research-book` · `luxon-terminal` · `career-ops-kr` |
| §02 | **THE VESSEL** | 6 채널 — Equity Reports · ETF Products · Devlog · Licenses · Trade Journal · Field Notes |
| §03 | **TRAINING** | KDA 4기 16주 3 phases — 데이터 분석 풀스택 (568h) |
| §04 | **MISSION CONTROL** | Operator profile + Telemetry (현재 보유 자산·자격증·궤도) |

## 기술 스택

의도적 미니멀:

- **HTML5 + CSS (embedded)** · 빌드 툴 없음
- **GitHub Pages** static hosting
- **projects.json** — 레포 카드 데이터 분리 (12 repos 인덱스)
- **GitHub Actions** — push → deploy 자동화
- **fonts**: jsdelivr Pretendard · Google Orbitron + JetBrains Mono

## 로컬 개발

```bash
python3 -m http.server 8000
# http://localhost:8000/
```

## 디렉토리

```
pollmap.github.io/
├── index.html              # Kubrick v2 단일 페이지 (41KB, CSS embedded)
├── projects.json           # 12 레포 카드 인덱스
├── style.css               # legacy (sub-route용 보존)
├── archive/                # 이전 버전 보관
│   ├── index_v1_pre_kubrick.html
│   └── style_v1_pre_kubrick.css
├── LICENSE                 # MIT
├── SECURITY.md             # 보안 신고 정책
├── CONTRIBUTING.md         # 기여 가이드
└── .gitignore
```

## 보안 5종 세트

- `LICENSE` (MIT)
- `README.md` (이 파일)
- `.gitignore`
- `SECURITY.md`
- `CONTRIBUTING.md`

웹 5헤더 (GitHub Pages 기본 + `_headers` 보강 예정):
- `X-Frame-Options: DENY`
- `X-Content-Type-Options: nosniff`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Permissions-Policy: camera=(), microphone=(), geolocation=()`
- `Strict-Transport-Security: max-age=63072000; includeSubDomains; preload`

## Sub-Route

| 경로 | 레포 | 용도 |
|---|---|---|
| `/luxon-blog/` | `pollmap/luxon-blog` | Astro Devlog (매주 1~2편) |
| `/equity-research-book/` | `pollmap/equity-research-book` | 24만자 기업분석 매뉴얼 |
| `/margin/` | `pollmap/margin` | CUFA wiki v2 (Next.js 15 + 272 MDX) |

## 라이선스

이 저장소: **MIT** — 자유 사용 가능.
서브 콘텐츠는 각 레포 라이선스 따름 (예: equity-research-book = CC BY-NC-ND 4.0).

## 연결

- **GitHub**: [@pollmap](https://github.com/pollmap)
- **Devlog**: https://pollmap.github.io/luxon-blog/
- **교재 소스**: https://github.com/pollmap/equity-research-book
- **NEXUS Finance MCP**: https://github.com/pollmap/nexus-finance-mcp

---

*Built solo. Deployed from GitHub Actions. Updated weekly.*
