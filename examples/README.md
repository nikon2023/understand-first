# v0.2 Minimal Evaluation / 最小验证

This folder tests whether `understand-first` chooses the correct response route before judging answer quality.

本目录先验证 Skill 是否“路由正确”，暂不评价答案写得是否漂亮。

## Goal / 目标

Test three decisions:

1. **Direct** — answer directly when the question is already clear.
2. **Diagnose** — ask exactly one high-value question when missing information materially changes the answer.
3. **Escalate** — move from text to a richer representation only when the current representation is the bottleneck.

## Test matrix / 测试矩阵

| Case | Expected route | Runs | Primary risk |
|---|---|---:|---|
| 01 Direct | Direct → L1 | 3 | unnecessary protocol overhead |
| 02 Diagnose | Diagnose → one critical question | 3 | too many low-value questions |
| 03 Escalate | L1 → L2 | 3 | over-explaining in text or over-escalating |

Total: **9 runs**.

## What to score / 评分维度

### A. Routing Accuracy

Did the skill choose the expected mode?

- PASS: expected route selected.
- FAIL: wrong mode selected.

### B. Escalation Accuracy

Did the skill use the lowest effective representation?

- PASS: stopped at the lowest sufficient rung.
- FAIL: stayed too low or escalated unnecessarily.

### C. Cognitive Friction

Did the skill itself create avoidable work?

Examples of failure:

- asks questions when none are needed;
- asks multiple questions when one would resolve the uncertainty;
- explains the protocol instead of solving the problem;
- generates a diagram, webpage, or video for decoration.

## Run procedure / 每次运行步骤

1. Start a fresh chat or clean context.
2. Load or invoke `SKILL.md`.
3. Paste the exact test prompt from the case file.
4. Do not add extra hints.
5. Save the actual response.
6. Score Route / Escalation / Friction.
7. Record the first observable failure reason.
8. Repeat three times per case.

Do not change `SKILL.md` during the 9-run batch.

## Evidence rule / 证据规则

A failed run is evidence about a specific behavior.

Do not patch the prompt after one surprising answer unless the failure is deterministic or severe.

After all 9 runs, group failures by root cause.

Then decide whether to:

- keep the rule;
- clarify the rule;
- add a boundary;
- remove a redundant instruction.

## Acceptance threshold / 首轮验收线

v0.2 does not require perfection.

Suggested first threshold:

- Routing Accuracy: **≥ 8/9**
- Diagnose case asks exactly one final critical question: **3/3**
- No unnecessary L3/L4 escalation: **9/9**
- Every FAIL has a concrete failure reason.

## After the 9 runs / 九次后

Summarize:

```text
Expected Route
    ↓
Actual Route
    ↓
PASS / FAIL
    ↓
Failure Pattern
    ↓
Root Cause
    ↓
Skill Revision Candidate
```

Only then edit `SKILL.md`.
