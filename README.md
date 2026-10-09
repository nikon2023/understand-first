# Understand First

**Diagnose before answering. Optimize for understanding. Escalate representation only when needed. Verify before turning an answer into a rule.**

`understand-first` is a Human–AI problem-solving skill for questions where a plausible answer is not enough.

It is designed for work where the human must understand:

- what is happening;
- why it is happening;
- how to check the result;
- what can be reused next time.

## Core loop

```text
Question
  ↓
Preflight diagnosis
  ↓
Reasoning / answer
  ↓
Lowest effective representation
  ↓
Evidence Gate
  ↓
Capability candidate
```

## Three source ideas

This skill is a synthesis of three independent sources.

### 1. Reddit: diagnose before committing

A widely shared Reddit prompt asks the model to identify:

1. unstated assumptions;
2. missing information that could change the answer;
3. the most common mistake for this class of problem;
4. one critical question before producing the final answer.

In this skill, that preflight is treated as canonical.

Its job is not to make every answer longer.

Its job is to reduce the chance of confidently answering the wrong problem.

### 2. Terence Tao: correct output is not the same as understanding

Terence Tao's public discussions of AI-assisted mathematical work motivate a distinction between obtaining a result and understanding it.

Humans still need to evaluate, connect, explain, and internalize results.

This skill operationalizes that goal as:

```text
Pattern
  ↓
Root cause
  ↓
Verification
  ↓
Transfer
```

This four-part formulation is this skill's synthesis, not a quotation from Tao.

### 3. Andrej Karpathy: change the representation when text is the bottleneck

Karpathy proposed a ladder for understanding LLM output:

```text
STE-style writing
  ↓
Diagram
  ↓
Interactive web page
  ↓
Explainer video
```

`understand-first` uses this as a representation escalation ladder.

It starts at the cheapest rung and climbs only when the current representation is itself blocking understanding.

## Operating principle

Use the smallest intervention that materially improves understanding.

- Simple question → answer directly.
- Ambiguous or strategic question → run the preflight.
- Structural confusion → use a diagram.
- State or parameter confusion → use an interactive model.
- Dynamic or temporal confusion → use a progressive explainer.
- High-impact conclusion → run the Evidence Gate.
- Repeated successful mechanism → extract a capability candidate.

## Understanding test

A response is successful when the human can answer four questions:

1. **Pattern** — What repeats?
2. **Root cause** — Why does it happen?
3. **Verification** — How can I check this?
4. **Transfer** — What can I do next time without starting from zero?

## Evidence boundary

Better presentation does not make weak evidence stronger.

The skill distinguishes:

- Fact
- Supported judgment
- Inference
- Assumption
- Unknown

Uncertainty must survive the climb from text to diagram to web page to video.

## Capability lifecycle

One successful answer does not become a global rule.

Reusable learning should move through:

```text
Candidate
  ↓
Trial
  ↓
Evidence
  ↓
Review
  ↓
Adopt / Revise / Reject
```

## Recommended use cases

Use `understand-first` for:

- architecture decisions;
- research design;
- root-cause analysis;
- project blockers;
- repeated debugging;
- complex reading;
- workflow redesign;
- evidence review;
- decisions that may become reusable rules.

Do not force it onto trivial factual questions.

## Repository structure

```text
understand-first/
├── SKILL.md
├── README.md
├── README.zh-CN.md
└── CHANGELOG.md
```

## Suggested invocation

```text
Use understand-first on this problem.
```

or:

```text
先理解，不要急着回答。用 understand-first 分析这个问题。
```

## Sources

- Reddit prompt pattern:
  https://www.reddit.com/r/PromptEngineering/comments/1rrhrh0/this_is_the_most_useful_thing_ive_found_for/
- Terence Tao with Dwarkesh Patel, *How the world's top mathematician uses AI*:
  https://www.youtube.com/watch?v=Q8Fkpi18QXU
- Andrej Karpathy, post on understanding LLM outputs:
  https://x.com/karpathy/status/2105819303471976479

## Attribution note

`understand-first` is an independent synthesis.

The Reddit preflight, Tao's discussion of human understanding, and Karpathy's representation ladder are separate source ideas.

The combined workflow, Evidence Gate, and capability-transfer lifecycle are the design of this skill.

The repository is not affiliated with or endorsed by the cited authors or platforms.
