# claude-config

Claude Code를 활용한 프론트엔드 프로젝트 자동화 도구.  
`/setup` 슬래시 커맨드 하나로 React + TypeScript + Tailwind 환경을 즉시 구성합니다.

---

## 빠른 시작

```bash
git clone https://github.com/YOUR_USERNAME/claude-config ~/claude-config
```

VS Code에서 폴더를 열고 Claude Code를 실행한 뒤:

```
/setup my-project
```

```
┌─────────────────────────────────────────┐
│       claude-config Project Setup       │
└─────────────────────────────────────────┘

Project name (default: my-app): my-project

🚀 Creating 'my-project'...
✅ 'my-project' is ready!
→ cd my-project && npm run dev
```

---

## 구현 기능

### 기능 1 — `/setup` 슬래시 커맨드

`/setup <프로젝트명>`을 입력하면 새 프로젝트를 자동으로 생성합니다.

- React 18 + Vite + TypeScript 프로젝트 생성
- Tailwind CSS v4 설치 및 설정
- `CLAUDE.md` 자동 생성 (Claude Code가 프로젝트 구조를 바로 파악)

| 항목 | 내용 |
|---|---|
| 프레임워크 | React 18 + Vite |
| 언어 | TypeScript |
| 스타일 | Tailwind CSS v4 |

### 기능 2 — `/review` 슬래시 커맨드

`/review`를 입력하면 현재 변경사항을 자동으로 코드 리뷰합니다.

- `git diff main`으로 변경사항 분석
- 파일별 변경 내용 1줄 요약
- 버그 · 보안 이슈 체크
- `✅ MERGE OK` / `⚠️ 수정 권장` / `❌ 수정 필요` 판정

---

## 프로젝트 구조

```
claude-config/
├── setup.sh                      # 셸 스크립트 (선택사항)
├── CLAUDE.md                     # Claude Code용 프로젝트 가이드
├── .claude/
│   └── commands/
│       ├── setup.md              # /setup 슬래시 커맨드
│       └── review.md             # /review 슬래시 커맨드
└── README.md
```

---

## 사용 방법

1. 이 레포를 클론합니다
2. VS Code에서 폴더를 열고 Claude Code 실행
3. `/setup <프로젝트명>`으로 새 프로젝트 생성
4. `/review`로 코드 리뷰 바로 사용