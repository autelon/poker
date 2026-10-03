# first-run 점검

2026-10-04, 설립 직후. 플러그인 자체의 동작 확인 결과는 autelon/company 쪽 문서에 있다.

- role: 설립한 세션에서는 `/reload-plugins` 뒤에 프로젝트 role(`.claude/agents/`)과 공용 role을 부를 수 있었다.
- role 메모리: 프로젝트 `.claude/agent-memory/<role>/`에 생긴다. 커밋하지 않는다.
- Notion: notion-sync가 프로젝트 Milestones DB에 항목을 만들었다. 연결 정보는 `notion/`(커밋 안 함)에 있다.
- 승인 루프: 폰 푸시가 오고 폰에서 고른 답이 세션에 들어왔다. 푸시가 안 오면 `/config inputNeededNotifEnabled=true`로 다시 켠다.
- PR 흐름: security-reviewer 보안 검토와 reviewer 리뷰가 같은 head에서 통과한 뒤 reviewer가 머지 큐에 넣었다.
- 미확인: developer worktree(handoff 위치, `.claude/agent-memory/developer/` 위치). 첫 구현 task 때 본다.
