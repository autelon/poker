# Git 규칙

공통 규칙(브랜치 전략, main 보호, PR 절차, rebase, `--admin` 금지 등)은 `autelon/.github`의 `git-workflow.md`를 따른다. 여기에는 이 프로젝트에서 정한 값만 적는다.

## 저장소

| 항목      | 값                                                                  |
| --------- | ------------------------------------------------------------------- |
| GitHub    | `autelon/poker` (public)                                            |
| 최신화    | 머지 큐                                                             |
| 병합 방식 | merge commit                                                        |
| 필수 검사 | `git-policy / merge-commits`                                        |
| 설정 확인 | `gh api repos/autelon/poker`, `gh api repos/autelon/poker/rulesets` |

## 리뷰와 머지

- PR 리뷰어: **reviewer role**. director가 `reviewer` role에 리뷰를 맡기고, reviewer가 판정을 PR 코멘트로 남긴다.
- 보안 검토(항상): 모든 PR은 `autelon:security-reviewer`가 검토하고 `보안 검토: 통과 (<sha>)` 또는 `보안 검토: 수정 필요 (<sha>)` 코멘트를 남긴다.
- 머지 조건: 같은 head sha에 리뷰 통과와 보안 검토 통과가 둘 다 있을 때만 reviewer가 머지 명령을 낸다.
- 머지 명령: `gh pr merge <PR> --match-head-commit <리뷰한 head sha>` (머지 큐라 `--auto`·병합 방식 옵션을 붙이지 않는다)

리뷰어를 바꾸려면 이 절을 고치고 `decisions/log.md`에 남긴다. 보안 검토는 바꾸지 않는다.
