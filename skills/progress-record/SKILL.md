---
name: progress-record
description: Stage 4. Execute subgoals in order and log everything in docs/4_progress_record.md, including trial and error, plan changes, and AI usage. Use during all execution work.
---

# Progress Record

## Goal
Anyone can reproduce the whole process by reading 4_progress_record.md alone.

## Rules
- Do subgoals in 2_plan.md order.
- Mark a task `[v]` only after its test passes. Never mark it before.
- Log failures and dead ends too, not only successes.
- If the plan turns out wrong, do not edit 2_plan.md. Add a "계획 변경" entry with the reason.
- Log after every subgoal, not at the end.

## Steps (per subgoal)
1. Write what you will do.
2. Do it. Record commands, code files, and key outputs (summaries only).
3. Run the subgoal's test. Record pass / fail.
4. If fail: record the cause and the fix, then retry.
5. If pass: mark `[v]` in the checklist.

## Template
```markdown
# 진행 기록

## Checklist
1. "데이터 무결성 검증" -> [ ]
2. "<task_name>" -> [ ]
3. "<task_name>" -> [ ]

## 기록
### 1. <task_name>
- 수행 내용:
- 실행 명령 / 파일:
- 결과 (요약):
- test 결과: pass / fail
- 시행착오: 무엇을 시도했고 왜 실패했고 어떻게 고쳤는가

### 계획 변경 (있을 경우)
- 변경 내용:
- 이유:

## AI 활용 기록
| 단계 | AI에게 맡긴 일 | 검증 방법 | AI 오류와 수정 |
|---|---|---|---|
```

## Done when
- Every checklist item is `[v]` or has a recorded reason why not.
- AI usage table covers every stage.
