---
name: data-audit
description: Stage 3. Find and fix hidden traps (errors) in the input data, and record them in docs/data_audit.md. Use before any modeling or analysis, and whenever new data is loaded or joined.
---

# Data Audit

## Goal
The data contains hidden traps. Find every one, fix it, and prove both with numbers.

## Rules
- Do this BEFORE any modeling or analysis.
- Never print full data. Use counts, `head`, `describe`, `value_counts`.
- Never silently drop or change data. Every change is recorded with before/after numbers.
- Write the checks as code (e.g. `tests/test_data.py`) so they can be re-run.

## Checklist
1. Schema / dtype: numbers stored as strings, wrong types, unexpected columns.
2. Missing values: NaN counts per column, and sentinel values that mean missing (`-1`, `0`, `999`, `""`, `"N/A"`, `"null"`).
3. Duplicates: duplicate rows, duplicate IDs, same ID with different values.
4. Out-of-range values: negative age, future dates, ratio > 100%, impossible combinations.
5. Unit / format mismatch: currency, ms vs s, date formats, timezone, decimal separators.
6. Category mismatch: case, whitespace, typos, synonyms (`"M"`, `"male"`, `"Male "`).
7. Join issues: key mismatch, rows lost or multiplied after merge. Compare row counts before and after.
8. Leakage / split issues: label leakage, overlap between train and test, distribution shift.
9. Outliers: extreme values. Decide whether they are errors or real.

## Steps
1. Run every checklist item. Record the result even if no issue is found.
2. For each trap found, decide the fix (remove / impute / flag / convert) and give the reason.
3. Apply the fix in code. Re-run the checks to confirm.
4. Write `docs/data_audit.md` (in Korean).

## Template
```markdown
# 데이터 검증

## 검사 요약
| # | 검사 항목 | 결과 | 문제 여부 |
|---|---|---|---|

## 발견한 함정
### 함정 1: <이름>
- 발견: 어떤 검사로, 어떤 값이 (예: age 컬럼에 -1 이 312건)
- 영향: 그대로 두면 어떤 문제가 생기는가
- 처리 결정: 제거 / 대체 / flag / 변환, 그리고 이유
- 처리 전후: row 수, 평균, 분포 등 수치 비교
- 검증: 재검사 결과

## 최종 데이터 상태
- 처리 후 row 수, 컬럼, 남은 이슈
```

## Done when
- All checklist items are run and recorded.
- Every trap has found / impact / fix / before-after / verification.
- Data tests pass on the cleaned data.
