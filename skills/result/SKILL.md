---
name: result
description: Stage 5. Write docs/result.md with the final result, reproduce command, and limitations. Use after all subgoals in progress_record.md are done.
---

# Result

## Goal
State the final outcome clearly. A grader reads only this file and understands what was achieved.

## Rules
- Only final results here. Minor trial and error stays in progress_record.md.
- Every claim has a number or evidence (metric, test output, file path).
- Run the full pipeline from scratch once and confirm it works before writing.

## Steps
1. Check all items in progress_record.md checklist are `[v]`.
2. Run the full pipeline from scratch with one command. Confirm all tests pass.
3. Write `docs/result.md` (in Korean).

## Template
```markdown
# 결과

## 1. 최종 결과
- 과제 목표에 대한 답 / 산출물 경로
- 평가 지표 값

## 2. 핵심 과정 요약
- 3~5줄. 상세는 progress_record.md 참조

## 3. 데이터 함정과 처리
- data_audit.md 의 함정 목록 요약 (함정 → 처리 → 효과)

## 4. 재현 방법
- 실행 명령어 한 줄
- 필요한 환경 / 패키지

## 5. 검증
- 통과한 test 목록

## 6. 한계 및 남은 이슈
- 해결하지 못한 문제, 가정에 의존하는 부분, 개선 방향
```

## Done when
- The reproduce command runs from scratch and tests pass.
- All 6 sections are filled.
