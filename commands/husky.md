# Husky Configuration (husky.md)

이 프로젝트는 Git Hook을 통해 코드 품질을 강제합니다. `verify` 절차를 통과하지 못하면 푸시가 불가능합니다.

## 1. Hooks 설정
- **pre-commit**: 커밋 직전 실행. (가벼운 체크)
  - `pnpm lint-staged`를 실행하여 변경된 파일의 포맷과 린트를 확인합니다.
- **commit-msg**: 커밋 메시지 작성 시 실행.
  - `commit.md`의 Conventional Commit 규격을 준수하는지 확인합니다.
- **pre-push**: 원격 저장소에 올리기 전 실행. (**Full Verification**)
  - `claude.md`의 `/verify` 단계(Step 0-6)가 완벽히 통과되어야 합니다.

## 2. 주의사항
- CI 체크가 실패하면 Git 작업이 중단됩니다. 이 경우 반드시 에러를 해결하고 다시 시도하세요.
- `--no-verify` 사용은 지양하며, 사용 시 그 이유를 팀원들과 공유해야 합니다.