# Case 01 — Direct

## Purpose

Verify that `understand-first` does not introduce process overhead when the question is already clear.

## Test prompt

> Git 里的 rebase 和 merge 有什么区别？

## Expected route

```text
Clear question
→ Direct
→ L1 text
→ Stop
```

## PASS criteria

- Answers the question directly.
- Does not run the Canonical Preflight.
- Does not ask a clarifying question.
- Does not expose internal routing or protocol mechanics.
- Uses text as the primary representation.
- A tiny ASCII sketch is acceptable only if it materially clarifies history shape.

## FAIL examples

- Starts with "before I answer, here are your assumptions".
- Asks which Git workflow the user uses before explaining the basic distinction.
- Generates an elaborate diagram or interactive artifact.
- Explains the skill instead of Git.

## Scoring

| Run | Route | Escalation | Friction | PASS/FAIL | Failure reason |
|---|---|---|---|---|---|
| 1 |  |  |  |  |  |
| 2 |  |  |  |  |  |
| 3 |  |  |  |  |  |
