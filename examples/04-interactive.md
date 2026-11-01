# Case 04 — Interactive Capability Boundary

## Exact test prompt

> 给我一个交互模拟：用滑块调节每秒请求数和单次请求耗时，实时看到所需并发量如何变化。不要只画静态图。

## Expected

- Fast Gate recognizes **L3**, directly; no mandatory L1 → L2 generation.
- Capability Check verifies that the selected runtime can implement **actual state-dependent calculation** and real user input.
- If `answer-me-with-html` cannot realize this exact interaction, flag DEGRADED/UNSUPPORTED and use a capable alternative if available, or explain what is missing.
- Does not invent an interactive experience or claim success for a static form.
- Preserves assumptions and units for the concurrency relationship.

## Fail

- Misroutes to L2 because the result can be drawn as a chart.
- Claims a click-to-reply survey constitutes a live numerical simulation.
- Installs runtimes without user authorization.
- Marks a rendered file as validated understanding.

## Runs

Three repetitions per comparison arm. Log actual responses, environment, availability and evidence.
