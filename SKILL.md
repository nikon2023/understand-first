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

## 3. Fast Gate: choose once when possible

Start with a lightweight decision. Do not run a visible checklist by default.

- **Direct:** Enough information, no material ambiguity; answer immediately, normally at L1.
- **Diagnose:** Missing information could materially change the answer; use the unchanged Canonical Preflight and ask at most one final high-information question. Wait for the answer if it is essential.
- **Represent:** The bottleneck is how the information is expressed; directly choose L1, L2, L3, or L4 based on what the human needs to understand.

A complex topic does not by itself require a rich artifact. Do not perform L1 → L2 → L3 → L4 as mandatory sequential generation. A request for a parameter-driven simulation may go directly to L3.

**Verify** and **Learn** are optional cross-cutting checks, not mutually exclusive primary routes.

## 4. Representation Ladder (decision, not rendering instructions)

Use the lowest effective level that satisfies the actual understanding need. Distinguish **the comprehension need** from **the output file format**. An HTML page with a static flowchart is L2, not L3.

Choose directly:

- **L1 / Information:** Clear, concise native text is sufficient. Use ASD-STE100-inspired prose without claiming certified compliance; one main idea per sentence, active voice where natural, uncertainty preserved.
- **L2 / Relationships:** The reader needs to see structure, hierarchy, architecture, causal relationships, or a process. Use a native diagram when sufficient; optionally delegate to a diagram-capable renderer.
- **L3 / Manipulation:** The reader needs to change parameters, switch states, compare paths, or see feedback that is actually computed or state-dependent. A static HTML page or a choice form alone does not prove true simulation.
- **L4 / Dynamics:** Time-dependent evolution or progressive animation is essential. Suggest an appropriate dynamic representation. **Generate an actual video only when explicitly requested or approved by the user.** Otherwise use a suitable L2/L3 fallback.

Avoid unnecessary media: do not upgrade because the available tool is attractive or the topic has many sections.

## 5. Runtime Capability Check

For a chosen level above L1, check the runtime **only if needed**:

1. Availability — Is the selected tool installed or accessible in this host?
2. Capability — Does it implement the specific diagram, interaction, or animation needed?
3. Input/dependency — Are required data, paths, tools, and dependencies present?
4. Output — Can the human open and use the result in the current environment?
5. Fidelity — Can the runtime preserve source meaning and evidence status?

Capability status is an **adapter convention**, not a claimed native `answer-me-with-html` API:

- `SUPPORTED`: the actual required behavior is implementable.
- `DEGRADED`: a useful but clearly limited alternative is possible.
- `UNSUPPORTED`: the essential behavior cannot be delivered.

When a runtime is unavailable, use a native supported alternative; do not install dependencies or claim success without authorization. A failed render is a technical failure, not proof that the user's comprehension needs a higher level.

## 6. Feedback and Re-routing

After rendering, distinguish three different outcomes:

- **Render success:** an artifact was produced and opened/verified where possible.
- **Understanding success:** the human can explain, apply, or check the relevant relationship; do not infer this from silence.
- **Evidence validity:** source claims and uncertainty remain accurate.

If the human remains confused, or a runtime fails, identify the remaining cause and run Fast Gate again. Re-route only when the new evidence warrants it. A renderer may report limitations or recommend another format; it must not autonomously override the selected level or request video creation.

## 7. Runtime Adapter Reference

See [`references/representation-runtime.md`](references/representation-runtime.md) for the optional `answer-me-with-html` adapter and fallbacks. Do not copy the third-party skill into this repository. Keep its proactive/always-on preference from overriding the lowest-effective-representation rule.

The preflight, understanding goals, Evidence Gate, and capability lifecycle remain independent of any renderer.


## 8. Escalation Policy

Re-run Fast Gate and choose the directly appropriate level (not necessarily the next rung) when new evidence shows the current representation is insufficient. Useful signals include:

- the same concept was explained twice and remains unclear;
- prose requires repeated rereading to reconstruct structure;
- relationships matter more than individual facts;
- static diagrams cannot show the important state change;
- manipulation is necessary to build intuition;
- temporal causality is the core difficulty.

Do not escalate because a richer format looks more impressive. Never let a renderer override the chosen level. On runtime failure, prefer a supported fallback. Do not produce video without explicit request or approval.

---

## 9. Evidence Gate

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

## 10. Capability Extraction

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

## 11. Response Modes

### Direct

Use for simple, fully specified questions.

Answer directly.

Do not expose the full protocol.

### Diagnose

Use for ambiguous, strategic, analytical, or repeatedly blocked questions.

Expose only assumptions, missing information, the common failure mode, and one critical question that materially matter.

### Represent

Run the Fast Gate once and choose L1/L2/L3/L4 based on the comprehension need. Check actual runtime capabilities and stop at the lowest effective rung.

### Verify

Use when conclusions affect research, implementation, architecture, project state, money, or persistent rules.

Show the evidence boundary.

### Learn

Use when a repeated pattern can become a capability candidate.

Do not silently globalize it.

---

## 12. Final Check

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

## 13. v0.2 Candidate Evaluation

This routing integration is **candidate behavior**, not validated performance.

Before release, compare the same test prompts under baseline `answer-me-with-html` routing, v0.1 full instructions, and v0.2 Fast Gate. Preserve original `examples/01–03` as a 9-run smoke baseline, then use the additional L3/L4 cases and the A/B/C comparison protocol. Log the actual selected route, capability result, render status, confusion/feedback status, elapsed time where measured, and evidence fidelity. Leave unexecuted trials empty.

Failure taxonomy: F1 over-diagnosis; F2 under-diagnosis; F3 over-escalation; F4 under-escalation; F5 evidence inflation; F6 capability mismatch; F7 renderer override; F8 false understanding; F9 routing overhead.

Do not claim a speed or accuracy improvement before measuring it.

---

## Source Model

This skill synthesizes three independent ideas:

1. A Reddit prompt pattern for diagnosing assumptions and missing information before answering.
2. Terence Tao's public discussion of AI-assisted mathematical work, used here as motivation for optimizing human understanding rather than output alone.
3. Andrej Karpathy's representation ladder: STE-style text → diagram → interactive web page → explainer video.

The combined workflow, Evidence Gate, and capability lifecycle are independent design choices of this skill.

See README files for attribution and source links.
