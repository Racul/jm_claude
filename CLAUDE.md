# Workflow Rules

## Language
- Write this file and skills in English.
- Answer the user in Korean. Write all docs/ outputs in Korean (graders read them).
- Keep technical terms in their original English (e.g. data leakage, unit test, outlier). Do not translate them into Korean.

## Always
- Follow `skills/coding-guidelines`: state assumptions, minimal code, surgical changes, verify with tests.

## Docs Folder
- Before stage 1, create a `docs/` folder in the project root (if it does not exist).
- Create and edit every stage md file inside `docs/` only: `1_prob_describe.md`, `2_plan.md`, `3_data_audit.md`, `4_progress_record.md`, `5_result.md`.
- Never write stage md files in the project root or any other folder.

## Stage Order
Follow this order as a guide, not a strict gate. Going back to an earlier stage (e.g. checking data while planning) is fine. Each stage has a skill with details.

1. **Problem description** → `skills/prob-describe` → `docs/1_prob_describe.md`
   - Understand the task, concepts, metric, constraints, assumptions, open questions.
2. **Plan** → `skills/plan` → `docs/2_plan.md`
   - Split the goal into subgoals with tests. Freeze 2_plan.md after writing.
   - Then create `docs/4_progress_record.md` with the numbered task checklist.
3. **Data audit** → `skills/data-audit` → `docs/3_data_audit.md`
   - Check the input data for errors BEFORE any modeling or analysis.
   - Fix each error and show before/after numbers.
4. **Execution** → `skills/progress-record` → `docs/4_progress_record.md`
   - Do subgoals in order. Run the tests for each subgoal before moving on.
   - Log every step, trial and error, plan change, and AI usage.
   - Mark a task `[v]` only after its test passes.
5. **Result** → `skills/result` → `docs/5_result.md`
   - Final answer, reproduce command, limitations.

## Plan Changes
- If a stage reveals the plan is wrong, do not edit 2_plan.md. Log "Plan change: reason" in 4_progress_record.md.
