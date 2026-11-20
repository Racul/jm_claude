---
name: prob-describe
description: Stage 1. Write docs/1_prob_describe.md to understand the task before planning. Use at the start of a new task, before any plan or code.
---

# Problem Description

## Goal
Understand the problem fully before planning. Make hidden assumptions visible.

## Steps
1. Read the task statement and list the given files. Look at data only with `head`, shape, and dtypes.
2. Write `docs/1_prob_describe.md` with the sections below (in Korean).
3. If anything is unclear, list it under open questions and ask the user before stage 2.

## Template
```markdown
# 문제 정의

## 1. 문제 요약
- 무엇을 입력받아 무엇을 출력해야 하는가 (2~3줄)

## 2. 최종 목표와 평가 지표
- 제출물 형식
- 평가 지표 (정확도, RMSE 등) 와 성공 기준

## 3. 입력 데이터
- 파일 목록, 크기, 주요 컬럼, dtype (요약만)

## 4. 필요한 개념
- 개념 이름: 한 줄 설명, 이 문제에서 왜 필요한지

## 5. 제약 조건
- 시간, 자원, 사용 가능 라이브러리, 금지 사항

## 6. 가정
- 내가 세운 가정과 그 근거

## 7. 불명확한 점
- 질문 / 확인 필요 사항
```

## Done when
- All 7 sections are filled.
- Open questions are resolved or recorded as assumptions.
