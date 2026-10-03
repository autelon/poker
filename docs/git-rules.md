# Git 규칙

이 프로젝트는 `autelon/.github`의 `git-workflow.md`(전역 Git·저장소 표준)를 따른다. 여기에는 이 프로젝트에서 정한 값만 적는다.

## 저장소

| 항목      | 값                                                                      |
| --------- | ----------------------------------------------------------------------- |
| GitHub    | `autelon/poker` (public)                                      |
| 최신화    | 머지 큐                                                       |
| 병합 방식 | merge commit                                                            |
| 필수 검사 | `git-policy / merge-commits`                                                     |
| 설정 확인 | `gh api repos/autelon/poker`, `gh api repos/autelon/poker/rulesets` |

## PR 리뷰어

리뷰어: **reviewer role**

- `director`: director(메인 세션)가 리뷰하고 머지 명령을 낸다. 기본값이다.
- `reviewer role`: director가 `reviewer` role에 리뷰를 맡긴다. reviewer가 통과로 판정하면 그 판정을 PR 코멘트로 남기고 머지 명령을 낸다.
- `사람`: 에이전트는 PR만 올리고 머지 명령을 내지 않는다. director가 사람에게 PR 링크를 알린다.

리뷰어를 바꾸려면 이 절을 고치고 `decisions/log.md`에 남긴다.

## PR 절차

1. 작업 브랜치에서 커밋하고 PR을 올린다. 작업한 role이나 세션은 자기 PR을 머지하지 않는다.
2. 리뷰어는 리뷰 결과를 PR 코멘트로 남긴다. 계정이 하나라 GitHub 승인(approve)은 쓰지 않는다.
3. 리뷰어의 머지 명령: `gh pr merge <PR> --match-head-commit <sha>` (머지 큐. 검사가 진행 중이면 auto-merge가 켜지고, 통과했으면 큐에 들어간다)
   - `--match-head-commit <리뷰한 head sha>`를 붙인다. 리뷰 뒤에 브랜치가 바뀌었으면 머지되지 않는다.
   - `--admin`은 쓰지 않는다.
4. main보다 뒤처져 막히거나 충돌이 나면 rebase 한다: `git fetch origin && git rebase origin/main && git push --force-with-lease`
