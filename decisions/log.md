# 결정 기록

| 날짜 | 대상 | 질문 | 답  | 후속 조치 |
| ---- | ---- | ---- | --- | --------- |
| 2026-10-04 | 설립 | 프로젝트 이름 | Poker | CLAUDE.md·Notion 제목 |
| 2026-10-04 | 설립 | 무엇을 왜 만드는가 | 아직 정하지 않음 | 목표·지표 수립 단계(strategist)에서 정한다 |
| 2026-10-04 | 설립 | 알려진 제약 | 웹 기반. 기술 스택은 `autelon/logistics-hub`(GitHub)를 참고 | role 페르소나에 참고 스택으로 적음. 백엔드 유무는 미정 |
| 2026-10-04 | 설립 | GitHub 저장소 | `autelon/poker`, public(머지 큐 사용) | 6단계 |
| 2026-10-04 | 설립 | PR 리뷰어 | reviewer role | `docs/git-rules.md`, reviewer 페르소나에 PR 리뷰 규칙 |
| 2026-10-04 | 설립 | role 구성 | po, strategist, designer, developer, reviewer, da, poker-expert, playtester (8개) | 보안·봇·게임 경제·규제 role은 제품 방향이 정해진 뒤 다시 판단 |
| 2026-10-04 | 설립 | notion/config.json 커밋 여부 | 공개 저장소라 커밋하지 않고 로컬에만 둔다 | `.gitignore`에 추가 |
| 2026-10-04 | 설립 | 항목별 Notion ID 위치 | `notion/ids.json`(커밋 안 함)에 둔다. board/*.json·PRD의 notion_id는 비워 둔다 | `.gitignore`에 추가, first-run notion-sync 지시문에 반영 |
| 2026-10-04 | 설립 | 개인 리소스 정보 공개 여부 | 로컬 절대 경로와 Notion URL·ID는 커밋하지 않는다. 다른 저장소는 GitHub 이름으로 가리키고, 로컬 클론 위치는 `local/paths.json`(커밋 안 함)에 둔다 | `.gitignore`에 `local/` 추가, 커밋 전 `git diff --cached`로 로컬 절대 경로와 Notion 도메인 검사 |
| 2026-10-04 | 설립 | Notion 루트 페이지 | 사용자 설정(`pluginConfigs`)의 값을 쓴다(사람이 읽기를 허락함). 그 아래에 Poker 페이지와 Milestones·PRDs·Tasks DB, Tasks 보드 뷰 2개를 만들었다 | ID는 `notion/config.json`(커밋 안 함) |
| 2026-10-04 | 설립 | GitHub 저장소 표준 적용 | 승인. `setup-repo.sh`로 merge commit만 허용, auto-merge·Update branch·브랜치 자동 삭제, main ruleset(삭제·force push 금지, PR 필수, 필수 검사 `git-policy / merge-commits`, 머지 큐) | `docs/git-rules.md` 자리표시자 채움 |
| 2026-10-04 | 설립 | 보안 검토 | 모든 PR은 리뷰어와 상관없이 `autelon:security-reviewer`의 보안 검토를 받고, 같은 head sha에 리뷰 통과와 보안 검토 통과가 둘 다 있을 때만 머지한다(모든 autelon 프로젝트 공통. 플러그인 작업 세션을 통해 전달된 사람의 결정) | `docs/git-rules.md`를 플러그인 bbc4a4fb44cc 템플릿 문구로 갱신, reviewer 페르소나의 머지 조건 갱신 |
| 2026-10-04 | PR #1 보안 검토 후속 | `.env*`를 .gitignore에 넣을지 | first-run PR에 넣는다 | `.gitignore`에 추가 |
| 2026-10-04 | PR #1 보안 검토 후속 | 재사용 워크플로를 SHA로 고정할지 | 조직 표준(autelon/.github) 차원의 일이라 이 프로젝트에서 정하지 않음 | 사람에게 보고 |
| 2026-10-04 | PR #2 보안 검토 후속 | `state/quota.json`(플랜·사용률)을 커밋할지 | 커밋하지 않는다. 재무 판정 스크립트의 입력일 뿐 올릴 필요가 없다 | `.gitignore`에 추가 |
| 2026-10-04 | 설립 후속 | role 메모리(`.claude/agent-memory/`)를 커밋할지 | 커밋하지 않는다 | `.gitignore`에 추가 |
| 2026-10-04 | 설립 후속 | `.gitignore`를 플러그인 템플릿(autelon/company#9 반영)과 맞춤 | `.claude/agent-memory-local/` 추가 | PR #2 리뷰 handoff도 함께 커밋 |
| 2026-10-04 | 저장소 정리 | 예전 커밋에 남은 홈 디렉터리 기준 경로와 force push 전 커밋 처리 | 저장소를 지우고 다시 만든다(사람의 결정). 히스토리는 설립 커밋을 루트로 다시 썼고, 경로는 repo 루트 기준 상대 경로나 저장소 이름으로만 쓴다 | 이 기록의 PR #1~#3, PR 코멘트 링크, 커밋 SHA는 지운 저장소를 가리킨다 |
| 2026-10-04 | 저장소 정리 | 전역 Git 표준 문서 위치 | `autelon/.github`의 `git-workflow.md`로 옮긴다(사람의 결정) | `docs/git-rules.md`가 그 문서를 가리킨다 |
| 2026-10-04 | 기록 정리 | 무엇을 decisions와 handoffs에 남길지 | decisions에는 사람이 정한 것만 둔다. 점검 결과는 `docs/first-run.md`에 짧게 쓴다. 리뷰·보안 검토 결과는 PR 코멘트가 기록이고 그 handoff는 커밋하지 않는다 | first-run 관찰 행과 PR #1~#3 리뷰 handoff를 지움(지운 저장소의 기록이라 git 히스토리에만 남음) |
