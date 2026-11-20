---
name: plan
description: Stage 2. Write docs/2_plan.md (subgoals with tests) and create docs/4_progress_record.md checklist. Use after 1_prob_describe.md is done, before any execution.
---

# Plan

## Goal
Split the final goal into small, verifiable subgoals. Every subgoal has a test.

## Rules
- Write 2_plan.md before any execution. After writing, 2_plan.md is frozen. Never edit it.
- Results and changes go to 4_progress_record.md or 5_result.md, never 2_plan.md.
- The first subgoal is always the data audit (see `skills/data-audit`).
- Every subgoal must have a test that proves it works.
- List every file to add or change in a table, with the subgoal and purpose.

## Steps
1. Read `docs/1_prob_describe.md`.
2. Write `docs/2_plan.md` with the template below (in Korean).
3. Write unit tests as files (e.g. `tests/test_data.py`, `tests/test_<subgoal>.py`) or as clear check commands.
4. Create `docs/4_progress_record.md` with the task checklist (see `skills/progress-record`).

## Template
```markdown
# 진행 계획

## 최종 목표
- 1_prob_describe.md 의 목표와 성공 기준

## Subgoals
### 1. 데이터 무결성 검증
- 할 일: data_audit 체크리스트 수행
- test: schema, 결측, 중복, 범위 검사가 통과하는가
- 완료 기준:

### 2. <subgoal 이름>
- 할 일:
- 입력 / 출력:
- test: 무엇을 어떻게 확인하는가
- 완료 기준:

...

## 파일 변경 계획
| 파일 | 추가 / 변경 | 관련 subgoal | 내용 |
|---|---|---|---|
| `src/load_data.py` | 추가 | 1 | 데이터 로드 및 검증 |
| `tests/test_data.py` | 추가 | 1 | 데이터 무결성 test |
| `<기존 파일>` | 변경 | 2 | 무엇을 왜 바꾸는가 |

## Test 계획
- 데이터 test: 입력 데이터 무결성
- subgoal test: 각 단계 출력의 shape, 범위, 예상값
- 통합 test: 처음부터 끝까지 한 번에 실행되는가

## 위험 요소
- 실패 가능성이 큰 부분과 대안
```

## Done when
- Every subgoal has a test and a done criterion.
- The file change table lists every file to add or change.
- 4_progress_record.md exists with the checklist.
