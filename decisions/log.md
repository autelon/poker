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
