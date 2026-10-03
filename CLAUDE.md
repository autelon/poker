# Poker

웹 기반 포커 프로젝트. 무엇을 왜 만드는지는 아직 정하지 않았다(2026-10-04 설립 시점). 목표·지표 수립 단계에서 `docs/goals.md`에 정한다. 기술 스택은 `autelon/logistics-hub`(GitHub)를 참고한다.

이 프로젝트는 autelon 플러그인으로 운영한다.

## 이 세션은 director다

세션을 시작하면 먼저 `autelon:director` 스킬을 불러 그 규칙대로 일한다.
직접 산출물을 만들지 않고, `.claude/agents/`의 role과 `autelon:*` role에게 일을 나눠 맡긴다.

## 프로젝트 파일

| 경로                                        | 내용                             |
| ------------------------------------------- | -------------------------------- |
| `board/tasks.json`, `board/milestones.json` | task 보드, 마일스톤              |
| `prds/`                                     | feature 단위 PRD                 |
| `handoffs/`                                 | role 작업 결과                   |
| `decisions/log.md`                          | 사람의 결정 기록                 |
| `docs/goals.md`                             | 프로젝트 목표와 지표 체계        |
| `docs/first-run.md`                         | 설립 직후 점검 결과              |
| `analytics/`                                | 이벤트 명세, 분석 쿼리 (da)      |
| `state/`                                    | 사용량 스냅샷, 스프린트 인계     |
| `notion/config.json`, `notion/ids.json`     | Notion 페이지·DB, 항목별 Notion ID (커밋 안 함) |
| `local/paths.json`                          | 참고 저장소의 로컬 클론 위치 (커밋 안 함) |
| `docs/git-rules.md`                         | 저장소 설정, PR 리뷰어, PR 절차  |
| `.github/workflows/ci.yml`                  | 필수 검사                        |
