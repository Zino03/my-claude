# Claude Collaboration Guide (claude.md)

이 파일은 진호(@Jin-ho)의 코딩 스타일, 프로젝트 규칙 및 자동화 워크플로우를 정의합니다. 모든 답변은 이 가이드를 최우선으로 참고하여 수행하세요.

## 1. 전역 코딩 규칙 (General Rules)
- **언어 및 도구**: React, TypeScript, pnpm을 기본으로 사용합니다.
- **TypeScript**: `any` 사용 금지, 인터페이스(Interface) 기반의 엄격한 타입을 선호합니다.
- **컴포넌트**: 함수형 컴포넌트와 Hooks를 사용하며, 가독성 높은 선언적 UI 패턴을 지향합니다.
- **언어 원칙**: 모든 **Git 커밋 메시지 및 PR 제목/내용은 영문(English)**으로, 그 외 **설명은 한국어(Korean)**로 작성합니다.

## 2. 프로젝트 관리 커맨드 (Custom Commands)

### 🔍 `/verify` (CI Check & Debugging)
저장소의 무결성을 검증합니다. **실패 시 다음 단계로 넘어가지 마세요.**
1. **Step 0**: `pnpm i` (의존성 최신화)
2. **Step 1**: `pnpm lint` (전체 코드 린트)
3. **Step 2**: `pnpm nx run-many --targets=build:types,build:dist,build:app,generate:docs,dev:run,typecheck` (빌드 및 타입 체크)
4. **Step 3**: `pnpm nx run-many --target=test:coverage` (테스트 실행, `.env` 로드 확인)
5. **Step 4**: `pnpm run sort-package-json` (패키지 정렬)
6. **Step 5**: `pnpm nx run-many --targets=lint:package,lint:deps` (패키지 린트)
7. **Step 6 (Double Check)**: 수정 발생 시 Step 1~3 재실행하여 회귀 버그 방지.
8. **Step 7**: `git status` 확인 후 `git add .` (단, `lib/*` 서브모듈 제외)

### ✍️ `/commit` (Atomic Staging)
- **규격**: `<Emoji> <Type>: <Description>` (영문 현재 시제/명령조)
- **절차**: 변경 사항 분석 후 논리적 단위로 커밋을 분할 제안합니다. 직접 커밋하지 말고 **메시지만 제안**하세요.
- **규칙**: Conventional Commits와 Gitmoji를 엄격히 준수합니다.

### 🚀 `/pr` (Pull Request)
- **도구**: GitHub CLI(`gh`) 명령어를 생성합니다.
- **형식**: `gh pr create --draft --title "<Emoji> <Type>: <Title>" --body-file .github/pull_request_template.md`
- **필수**: 템플릿의 `pr_agent` 섹션을 보존하고, 모든 내용을 영문으로 채웁니다.

### 🐕 `/husky` (Git Hooks)
- **설정**: `pre-commit`(lint-staged), `commit-msg`(commitlint), `pre-push`(/verify 절차)를 관리합니다.
- **대응**: Husky가 Hook 에러를 발생시키면 아래의 '에러 대응 프로토콜'을 즉시 실행합니다.

## 3. 에러 대응 프로토콜 (Break-Fix Protocol)
CI/CD 단계에서 문제가 발생하면 다음 순서를 따릅니다.
1. **Explain**: 로그와 소스 코드를 인용하여 무엇이, 왜 깨졌는지 논리적으로 설명합니다.
2. **Fix**: 해결책을 제안하고, 수정 후 다시 검증 단계를 밟습니다.
3. **Global Check**: 동일한 버그가 다른 모듈에도 존재할 가능성을 검토합니다.
4. **Clean up**: 디버깅을 위해 추가한 `console.log` 등은 반드시 제거합니다.

## 4. 프론트엔드 & 보안 가이드
- **State**: Zustand, TanStack Query 또는 Context API를 적절히 선택합니다.
- **UX**: 모바일 퍼스트 반응형 디자인과 성능 최적화(Lighthouse)를 고려합니다.
- **Security**: 금융/빅테크 타겟 프로젝트임을 인지하고 데이터 노출 및 보안 취약점을 상시 검토합니다.

---
*Last Updated: 2026-05-07*