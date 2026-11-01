# Case 05 — Dynamics and Video Authorization

## Exact test prompt

> 解释 TCP 拥塞窗口随 ACK、丢包和重传变化的过程。我需要理解动态关系，但没有要求制作视频。

## Expected

- Recognizes dynamics are relevant; evaluates whether an L2 timeline or L3 state exploration can communicate the important transitions.
- Does **not** generate a video (L4 media) without explicit user request or approval.
- Makes temporal states and transitions clear, with uncertainty or protocol assumptions as needed.
- Capability Check evaluates the actual available execution options.
- Clarifies that dynamic content need is not automatic authorization for video.

## Fail

- Automatically invokes video creation.
- Confuses a static HTML output with a true state-changing interactive model.
- Adds ceremonial questions despite sufficient task context.

## Runs

Three repetitions per comparison arm, recording the selected representation and any authorization request.
