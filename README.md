# pollmap.github.io

> 이찬희 (Chan-hee Lee) — Luxon AI Founder · CUFA 2대 회장 · 충북대 경영 학부생.
> 이 저장소는 `https://pollmap.github.io/` 루트 도메인을 서빙하는 **개인 포트폴리오 허브**다.

## 무엇인가

2028년 졸업 공채까지의 5년 공개 빌드로그 포트폴리오. 면접관이 **단일 URL 하나로 15분** 안에 전부 열람 가능하도록 설계된 3단 funnel:

1. **관문 (이 페이지)** — 누구인가 / 뭘 만드는가 / 어디로 갈까 (15초 훑기)
2. **발행 엔진** — [`/luxon-blog/`](https://pollmap.github.io/luxon-blog/) 매주 1~2편 Devlog
3. **완성품** — [`/equity-research-book/`](https://pollmap.github.io/equity-research-book/) 『한국 시장 실전 기업분석』 (24만자)
4. **쇼케이스** — 19+ GitHub repo 카드 인덱스 (projects.json)

## 기술 스택

의도적으로 최소 스택 유지:

- **HTML5 + CSS + vanilla JS** (빌드 툴 없음)
- **GitHub Pages** static hosting
- **projects.json** — 레포 카드 데이터 분리
- **GitHub Actions** — push → deploy 자동화

## 로컬 개발

```bash
# 어떤 정적 서버든 사용 가능
python3 -m http.server 8000
# 또는
npx http-server .
```

브라우저에서 `http://localhost:8000/`.

## 프로젝트 카드 추가

`projects.json`의 `projects[]` 배열에 객체 한 개 추가:

```json
{
  "name": "repo-slug",
  "title": "표시 제목",
  "description": "한 줄 설명",
  "url": "https://github.com/pollmap/repo-slug",
  "language": "Python",
  "tags": ["tag1", "tag2"],
  "featured": false
}
```

커밋 → push → GitHub Actions가 자동 배포.

## 라이선스

- **소스 코드** (HTML/CSS/JS/YAML): MIT
- **본인 이력·프로젝트 설명 텍스트**: CC BY 4.0 (attribution appreciated)
- **링크된 외부 콘텐츠** (블로그 포스트, 교재, 기타 repo): 각 대상의 개별 라이선스 적용

## 연결

- **GitHub**: [@pollmap](https://github.com/pollmap)
- **Devlog**: https://pollmap.github.io/luxon-blog/
- **교재 소스**: https://github.com/pollmap/equity-research-book
- **NEXUS Finance MCP**: https://github.com/pollmap/nexus-finance-mcp

---

*Built solo. Deployed from GitHub Actions. Updated roughly weekly.*
