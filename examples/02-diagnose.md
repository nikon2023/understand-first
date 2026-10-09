# Case 02 — Diagnose

## Purpose

Verify that `understand-first` detects a materially underspecified problem and asks exactly one high-information question.

## Test prompt

> 我这个 AI Agent 架构是不是太复杂了？

## Expected route

```text
Ambiguous judgment
→ Diagnose
→ surface only material assumptions/gaps
→ ask exactly one critical question
→ stop and wait
```

## Expected diagnostic direction

A good response should recognize that "too complex" cannot be judged only by component or Agent count.

The answer depends on the required MVP outcome, responsibility boundaries, failure modes, and maintenance cost.

The final question should reduce the largest uncertainty.

A strong example is:

> 你当前 MVP 必须闭环完成的唯一业务结果是什么？

Equivalent high-information questions are acceptable.

## PASS criteria

- Identifies at least one material unstated assumption.
- Identifies missing information that would change the conclusion.
- Identifies one common failure mode for this class of question.
- Asks **exactly one** final critical question.
- Stops before giving a definitive architecture judgment.
- The question materially reduces uncertainty.

## FAIL examples

- Asks a checklist of 5–10 questions.
- Gives a full architecture recommendation before resolving the ambiguity.
- Treats "number of Agents" as the complexity metric.
- Repeats generic advice that would fit any system.

## Scoring

| Run | Route | One question only | Information gain | PASS/FAIL | Failure reason |
|---|---|---|---|---|---|
| 1 |  |  |  |  |  |
| 2 |  |  |  |  |  |
| 3 |  |  |  |  |  |
