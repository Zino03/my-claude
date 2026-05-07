# Pull Request Guide (create-pull-request.md)

이 가이드는 GitHub CLI(`gh`)를 사용하여 우리 프로젝트에서 Pull Request를 생성하는 방법을 정의합니다.

> **⚠️ 중요**: 모든 PR 제목과 본문은 반드시 **영문(English)**으로 작성해야 합니다.

## 1. 사전 준비
- **GitHub CLI 설치**: `brew install gh` (macOS) 또는 `winget install --id GitHub.cli` (Windows)
- **인증**: `gh auth login` 명령어로 로그인 상태 확인

## 2. PR 생성 프로세스
1. **템플릿 준비**: `.github/pull_request_template.md` 파일의 내용을 확인합니다.
2. **명령어 실행**: 아래 명령어를 사용하여 Draft PR을 생성합니다.
   ```bash
   # 템플릿 파일을 본문으로 사용하여 생성
   gh pr create --draft --title "✨(scope): Your descriptive title" --body-file .github/pull_request_template.md --base main