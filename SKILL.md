---
name: understand-first
description: >
  Use when a question is ambiguous, strategic, analytical, repeatedly blocked, or likely to become a reusable rule.
  Diagnose before answering, optimize for human understanding rather than answer volume, use the lowest effective
  representation rung, verify important claims, and extract reusable capability candidates.
---

# Understand First / 先理解，再回答

## Purpose

Help the human and AI understand a problem before optimizing the answer.

The goal is not only to produce a correct-looking output.

The goal is to improve four capabilities:

1. See the pattern.
2. Identify the root cause.
3. Verify the result.
4. Transfer the learning.

Use the smallest amount of process that materially improves understanding.

Do not force the full protocol on simple questions.

---

## 1. Canonical Preflight

For ambiguous, strategic, analytical, or repeatedly blocked questions, use this preflight before the final answer.

Preserve its intent and order unless the user explicitly changes it.

> Don't answer my question yet.
>
> First do this:
>
> 1. Tell me what assumptions I'm making that I haven't stated out loud.
> 2. Tell me what information would significantly change your answer if you had it.
> 3. Tell me the most common mistake people make when asking you this type of question.
>
> Then ask me the one question that would make your answer actually useful for my specific situation rather than anyone who might ask this.
>
> Only after I answer, give me the output.

Do not use the full preflight when:

- the question is simple and fully specified;
- a direct factual answer is sufficient;
- missing information cannot materially change the answer;
- asking another question would only add friction.

If the user already supplied enough context, continue without asking.

---

## 2. Understanding Goal

A successful answer should increase understanding, not only deliver output.

Check four dimensions.

### Pattern

Can the human see the recurring structure?

Do not infer a stable pattern from one isolated case.

### Root Cause

Can the human explain why the problem occurs?

Distinguish symptoms from mechanisms.

### Verification

Can the human check whether the conclusion is correct?

For material claims, provide a concrete check, evidence path, test, or falsification condition.

### Transfer

Can the human handle the next similar case with less assistance?

If yes, extract a reusable capability candidate.

---

## 3. Representation Ladder

Use the lowest effective rung.

Do not generate all four levels by default.

### L1 — Clear Text

Default to concise, low-ambiguity prose.

Use ASD-STE100-inspired writing rather than claiming formal STE100 compliance.

Prefer:

- one main idea per sentence;
- active voice where natural;
- short sentences;
- explicit subjects and actions;
- minimal decoration;
- preserved uncertainty.

If text resolves the problem, stop.

### L2 — Diagram

Escalate when structure is the main difficulty.

Use a diagram for hierarchy, process, causal chains, architecture, state transitions, or branching logic.

The diagram must expose relationships.

Do not merely put paragraphs into boxes.

### L3 — Interactive Web

Escalate when understanding requires manipulation or comparison.

Use an interactive page for:

- changing parameters;
- switching states;
- comparing alternatives;
- exploring paths;
- observing feedback;
- testing what-if scenarios.

The interaction must answer a specific question.

### L4 — Dynamic Explainer

Escalate when the main difficulty is temporal or dynamic.

Use animation or video for:

- evolving systems;
- time-dependent causality;
- spatial transformation;
- progressive concept construction.

Build the explanation step by step.

---

## 4. Escalation Rules

Escalate one rung when at least one condition is true:

- the same concept was explained twice and remains unclear;
- prose requires repeated rereading to reconstruct structure;
- relationships matter more than individual facts;
- static diagrams cannot show the important state change;
- manipulation is necessary to build intuition;
- temporal causality is the core difficulty.

Do not escalate because a richer format looks more impressive.

---

## 5. Evidence Gate

Clear presentation does not imply correctness.

For material conclusions, distinguish:

- Fact
- Supported judgment
- Inference
- Assumption
- Unknown

State a verification path for high-impact claims.

Preserve uncertainty across every representation rung.

Do not let a diagram, webpage, or video convert a hedge into a fact.

---

## 6. Capability Extraction

After solving a meaningful recurring problem, test whether the result can become a reusable capability.

Use:

`blocker → root cause → mechanism → verification → transfer rule`

Treat the result as a candidate.

Do not promote one success directly into a permanent rule.

Recommended lifecycle:

`Candidate → Trial → Evidence → Review → Adopt / Revise / Reject`

A reusable rule should include:

- applicability conditions;
- known boundaries;
- verification method.

---

## 7. Response Modes

### Direct

Use for simple, fully specified questions.

Answer directly.

Do not expose the full protocol.

### Diagnose

Use for ambiguous, strategic, analytical, or repeatedly blocked questions.

Expose only assumptions, missing information, the common failure mode, and one critical question that materially matter.

### Explain

Use the Representation Ladder.

Stop at the lowest effective rung.

### Verify

Use when conclusions affect research, implementation, architecture, project state, money, or persistent rules.

Show the evidence boundary.

### Learn

Use when a repeated pattern can become a capability candidate.

Do not silently globalize it.

---

## 8. Final Check

Before finishing a substantive answer, silently check:

- Did we identify the real problem?
- Can the human see the pattern?
- Did we reach the root cause?
- Can the result be verified?
- Is the current representation sufficient?
- Can any learning transfer?
- Are we overgeneralizing from one case?

Expose only the checks that improve the user's decision or understanding.

---

## Source Model

This skill synthesizes three independent ideas:

1. A Reddit prompt pattern for diagnosing assumptions and missing information before answering.
2. Terence Tao's public discussion of AI-assisted mathematical work, used here as motivation for optimizing human understanding rather than output alone.
3. Andrej Karpathy's representation ladder: STE-style text → diagram → interactive web page → explainer video.

The combined workflow, Evidence Gate, and capability lifecycle are independent design choices of this skill.

See README files for attribution and source links.
