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
| 2026-10-04 | first-run 1 | role 인식 | `autelon:director`·`autelon:found-company` 스킬과 `autelon:finance`·`autelon:notion-sync` agent는 보였다. 설립 중에 만든 프로젝트 role(reviewer 등)은 같은 세션에서 호출되지 않았다(`Agent type 'reviewer' not found`) | 새 세션(reload)에서 다시 확인. 그 전까지 PR 리뷰 보류(사람의 지시) |
| 2026-10-04 | first-run 3 (T-SMOKE-1) | finance 호출과 메모리 | 호출됨. handoff는 메인 checkout `handoffs/T-SMOKE-1.md`에 생김. 메모리는 프로젝트 루트 아래 `.claude/agent-memory/autelon-finance/`에 생김(폴더 이름은 `autelon:` 의 콜론이 하이픈으로 바뀜) | `.claude/agent-memory/`를 커밋할지는 미정 |
| 2026-10-04 | first-run 4 (T-SMOKE-2) | notion-sync가 Notion 커넥터를 쓰는가 | 쓴다. notion-fetch·notion-create-pages로 Milestones DB에 M-00을 만들었고 director가 Notion에서 직접 확인함. `로컬 ID → URL`은 `notion/ids.json`(커밋 안 함)에 씀. 단 "handoff에 URL을 쓰지 말라"는 지시를 어기고 handoff에 URL을 적음 | 스모크 handoff는 커밋하지 않음. M-00은 사람이 Notion에서 지움 |
| 2026-10-04 | first-run 1 (reload 뒤) | role 인식 | 사람이 `/reload-plugins`를 실행한 뒤 프로젝트 role 8개와 `autelon:security-reviewer`가 agent 목록에 들어왔고, reviewer·security-reviewer를 실제로 호출함 | 설립한 세션에서 role을 쓰려면 reload가 필요함 |
| 2026-10-04 | first-run 2 | 승인 루프(폰 푸시) | 확인함(4회차). 1회차: 푸시가 데스크톱보다 늦게 옴(사람이 다른 세션을 통해 전달), 답은 데스크톱. 2회차: 답은 데스크톱. 3회차: Remote Control 켜짐, 사용자 설정의 `inputNeededNotifEnabled`·`agentPushNotifEnabled`가 true였는데도 30분 동안 푸시 없음. 사람이 `/config inputNeededNotifEnabled=true`(Push when actions required), `/config agentPushNotifEnabled=true`(Push when Claude decides)를 실행한 뒤 4회차: 폰 푸시가 왔고 폰에서 고른 답이 세션에 들어옴 | 3회차에 푸시가 오지 않은 원인은 확인 못 함 |
| 2026-10-04 | first-run 5 | developer worktree | 코드가 없어 생략(플레이북대로) | 첫 구현 task 때 handoff 위치와 `.claude/agent-memory/developer/` 위치 확인 |
| 2026-10-04 | first-run 6 | 스모크 정리 | 스모크 handoff 2개와 보드의 M-00·T-SMOKE task를 지움. Notion의 M-00은 사람이 지운다 | 플러그인 리포 `docs/design.md` 7절 갱신은 사람에게 알림 |
| 2026-10-04 | first-run | role 메모리와 PR handoff 커밋 여부 | 둘 다 커밋한다 | `.claude/agent-memory/`, `handoffs/T-PR1-*.md` 커밋 |
| 2026-10-04 | PR #1 보안 검토 후속 | 예전 커밋의 홈 상대 경로가 public 히스토리에 남음 | 지우는 방법을 따로 검토한다(이번에는 손대지 않음) | director가 절차와 영향을 정리해 보고 |
| 2026-10-04 | PR #1 보안 검토 후속 | `.env*`를 .gitignore에 넣을지 | first-run PR에 넣는다 | `.gitignore`에 추가 |
| 2026-10-04 | PR #1 보안 검토 후속 | 재사용 워크플로를 SHA로 고정할지 | 조직 표준(autelon/.github) 차원의 일이라 이 프로젝트에서 정하지 않음 | 사람에게 보고 |
| 2026-10-04 | PR #2 보안 검토 후속 | `state/quota.json`(플랜·사용률)을 커밋할지 | 커밋하지 않는다. 재무 판정 스크립트의 입력일 뿐 올릴 필요가 없다 | `.gitignore`에 추가 |
| 2026-10-04 | PR #2 보안 검토 후속 | finance role 메모리(사용률 포함)를 커밋할지 | finance 메모리 전체를 커밋하지 않는다 | `.gitignore`에 `.claude/agent-memory/autelon-finance/` 추가 |
| 2026-10-04 | PR #2 후속 | role 메모리 전체를 커밋할지 | 커밋하지 않는다(앞의 "둘 다 커밋"과 finance 메모리 결정을 바꿈). PR handoff는 커밋한다 | `.gitignore`에 `.claude/agent-memory/`. 다른 프로젝트에도 반영되도록 autelon/company에 이슈를 남김 |
| 2026-10-04 | first-run 후속 | `.gitignore`를 플러그인 템플릿(autelon/company#9 반영)과 맞춤 | `.claude/agent-memory-local/` 추가 | PR #2 리뷰 handoff도 함께 커밋 |
