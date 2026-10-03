---
task: T-PR1-SEC
role: security-reviewer
status: done
---

## 한 일

- PR autelon/poker#1 (chore/git-rules) 보안 검토. 판정: **통과**, head `f400d43c91b538c265421db94ec083e2217ffdac`.
- 판정 코멘트: https://github.com/autelon/poker/pull/1#issuecomment-5971263583 (제목 `보안 검토: 통과 (f400d43c91b538c265421db94ec083e2217ffdac)`)
- PR 범위 밖인 main 히스토리도 훑었다. 차단할 값은 없고, 참고 사항 3건을 아래에 적었다.

## 산출물

- PR 코멘트 1개(위 링크)
- 이 handoff

## 확인한 것 / 확인 못 한 것

PR 범위 (base `2fda3f1` .. head `f400d43`)
- `git fetch origin` 후 `git rev-parse origin/chore/git-rules` = `f400d43…`, `gh pr view 1` headRefOid도 같음(코멘트 직전 다시 확인).
- `git log -p origin/main..origin/chore/git-rules`: 커밋 2개(df8701b, f400d43)의 diff와 메시지 전부 읽음.
- 변경 파일 3개, 모두 수정(새 파일·이름 변경·바이너리 없음): `.claude/agents/reviewer.md`, `decisions/log.md`, `docs/git-rules.md`.
- PR 제목·본문 읽음. PR 코멘트는 검토 시점에 없었음.
- 패턴 검색(역할 지시문의 grep + UUID형 ID, 사설 IP, 개인 이메일 도메인): 커밋 헤더의 git SHA 외에는 걸린 것 없음.
- 작성자·Co-Authored-By: `noreply@anthropic.com`, GitHub noreply 주소뿐.
- diff 내용: 자리표시자를 `autelon/poker`, `git-policy / merge-commits`, 머지 명령으로 채움. 머지 조건에 보안 검토 통과를 추가. 플러그인 캐시 버전 문자열 `bbc4a4fb44cc`(12자, 경로 아님)가 decisions/log.md에 있음. 개인 정보는 없다고 판단함.
- `.gitignore`, 훅, CI, 의존성, settings 변경 없음.

main 히스토리 (PR 범위 밖, 커밋 6개, `git log -p origin/main`) — 판정과 별개인 참고 사항
1. 커밋 ffdaf0a, 0bf4494 (`.claude/settings.json`, 이후 커밋에서 삭제됨): `extraKnownMarketplaces`의 directory 소스에 홈 디렉터리 기준 경로가 히스토리에 남아 있음. 사용자 이름은 드러나지 않고 폴더 구조만 드러남. 커밋 0bf4494의 메시지에도 같은 형태 경로가 있음.
2. 같은 settings.json 히스토리(ffdaf0a~2aa6c17)에 프로젝트 settings의 `extraKnownMarketplaces`가 있었고, d4399ec에서 지워졌음. 현재 main에는 없음.
3. `.github/workflows/ci.yml`(2fda3f1): `permissions: contents: read`로 최소 권한. 재사용 워크플로를 `autelon/.github/...git-policy.yml@main`(브랜치 ref, SHA 고정 아님)으로 부름. 조직 자체 저장소이고 조직 표준(git-workflow.md)이 정한 형태임.
4. 현재 main `.gitignore`에 `.env*` 항목은 없음(`notion/`, `local/`, `.claude/settings.local.json`은 있음). 아직 `.env` 파일을 쓰는 코드는 확인하지 못함(main 파일 목록에 없음).
- main에서 비밀 값, Notion 주소·ID, 사용자 이름이 든 절대 경로, 개인 이메일은 찾지 못함.

## 사람에게 묻기

- main 참고 사항 1(홈 디렉터리 기준 경로가 public 히스토리에 남음): 사용자 이름은 없어 수정 필요로 보지 않았다. 이를 지우려면 main 히스토리 재작성(force push)이 필요하고 main ruleset이 이를 막는다. 그대로 둘지(권장 판단은 사람 몫) 정해 주세요.
- main 참고 사항 3: 재사용 워크플로를 `@main` 대신 SHA로 고정할지는 조직 표준(autelon/.github) 차원의 결정이다. 바꾸려면 git-workflow.md부터 고쳐야 한다.
- main 참고 사항 4: `.env*`를 `.gitignore`에 미리 넣을지. 비용이 작고 비밀 값 유출을 줄인다. 넣으면 별도 PR이 필요하다.

## 다음 제안

- reviewer role의 리뷰 판정이 같은 head sha(`f400d43…`)로 나오면 docs/git-rules.md 절차대로 머지 가능. 그 뒤 브랜치가 바뀌면 보안 검토를 다시 받아야 한다.
