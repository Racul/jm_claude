# Workflow Rules

## Language
- Write this file and skills in English.
- Answer the user in Korean. Write all docs/ outputs in Korean (graders read them).

## Always
- Follow `skills/coding-guidelines`: state assumptions, minimal code, surgical changes, verify with tests.
- Never print full large data or files. Use `head`, shape, and summary statistics.
- Use snake_case file names.

## Docs Folder
- Before stage 1, create a `docs/` folder in the project root (if it does not exist).
- Create and edit every stage md file inside `docs/` only: `prob_describe.md`, `plan.md`, `data_audit.md`, `progress_record.md`, `result.md`.
- Never write stage md files in the project root or any other folder.

## Stage Order
Run the stages in this order. Do not skip ahead. Each stage has a skill with details.

1. **Problem description** → `skills/prob-describe` → `docs/prob_describe.md`
   - Understand the task, concepts, metric, constraints, assumptions, open questions.
2. **Plan** → `skills/plan` → `docs/plan.md`
   - Split the goal into subgoals with tests. Freeze plan.md after writing.
   - Then create `docs/progress_record.md` with the numbered task checklist.
3. **Data audit** → `skills/data-audit` → `docs/data_audit.md`
   - Check the input data for traps BEFORE any modeling or analysis.
   - Fix each trap and show before/after numbers.
4. **Execution** → `skills/progress-record` → `docs/progress_record.md`
   - Do subgoals in order. Run the tests for each subgoal before moving on.
   - Log every step, trial and error, plan change, and AI usage.
   - Mark a task `[v]` only after its test passes.
5. **Result** → `skills/result` → `docs/result.md`
   - Final answer, reproduce command, limitations.

## Stage Gates
- Do not start stage N+1 until stage N's doc exists and its checks pass.
- If a stage reveals the plan is wrong, do not edit plan.md. Log "Plan change: reason" in progress_record.md.
