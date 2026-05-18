# claude-config

Claude Code 프로젝트 자동 셋업 도구.  
`bash setup.sh` 한 줄로 React + TypeScript + Tailwind 환경을 구성합니다.

---

## 빠른 시작

```bash
git clone https://github.com/YOUR_USERNAME/claude-config ~/claude-config
bash ~/claude-config/setup.sh
```

실행하면 프로젝트 이름을 입력받고 자동으로 셋업합니다.

```
┌─────────────────────────────────────────┐
│       claude-config 프로젝트 셋업        │
└─────────────────────────────────────────┘

프로젝트 이름 (기본값: my-app): my-project

🚀 'my-project' 생성 중...
✅ 'my-project' 세팅 완료!
→ cd my-project && npm run dev
```

---

## 구현 기능

### 기능 1 — 프로젝트 자동 셋업 (`setup.sh`)

`bash setup.sh` 한 줄로 아래를 자동 처리합니다.

- React 18 + Vite + TypeScript 프로젝트 생성
- Tailwind CSS v4 설치 및 설정
- `CLAUDE.md` 자동 생성 (Claude Code가 프로젝트를 이해하는 기준 파일)

| 항목 | 내용 |
|---|---|
| 프레임워크 | React 18 + Vite |
| 언어 | TypeScript |
| 스타일 | Tailwind CSS v4 |

### 기능 2 — `/review` 슬래시 커맨드

Claude Code에서 `/review`를 입력하면 PR 코드 리뷰를 자동 수행합니다.

- `git diff main`으로 변경사항 분석
- 파일별 변경 내용 1줄 요약
- 버그 · 보안 이슈 체크
- `✅ MERGE OK` / `⚠️ 수정 권장` / `❌ 수정 필요` 판정

```
/review
```

---

## 프로젝트 구조

```
claude-config/
├── setup.sh                      # 프로젝트 자동 셋업 스크립트
├── .claude/
│   └── commands/
│       └── review.md             # /review 슬래시 커맨드
└── README.md
```

---

## 사용 방법

1. 이 레포를 클론합니다
2. `bash setup.sh` 실행 → 프로젝트 이름 입력
3. 생성된 폴더를 VS Code에서 열고 Claude Code 실행
4. `/review`로 코드 리뷰 바로 사용