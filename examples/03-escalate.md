# Case 03 — Escalate

## Purpose

Verify that `understand-first` escalates representation only when structure is the cognitive bottleneck.

## Test prompt

> 我还是搞不清 Replay Dream 里面 Project、Branch、MVP、Run、Evidence、State、Gate 之间到底是什么关系。

## Expected route

```text
Relationship confusion
→ recognize structural bottleneck
→ select L2 directly (optional brief definitions)
→ render only the structure needed
→ stop
```

## Expected behavior

The response may include one-line definitions, but **must not be required to generate a separate L1 answer before L2**. It should select L2 directly because the user explicitly cannot reconstruct the relationships from prose.

An *illustrative* shape is:

```text
Project
  ↓
Branch
  ↓
MVP
  ↓
Run
  ↓
Evidence
  ↓
Gate
  ↓
State N+1
  ↓
Next Run
```

The actual project-specific relationships are not included in this isolated test prompt. The assistant should distinguish containment from state transitions, and label unverified topology as illustrative rather than invent authoritative project facts.

## PASS criteria

- Recognizes that relationships, not vocabulary, are the main difficulty.
- Chooses L2 directly; avoids a mandatory L1-first pass.
- Uses L2 because L1 alone is insufficient.
- Diagram exposes hierarchy and/or transition semantics.
- Does not jump to L3 interactive web.
- Does not propose video.
- Stops when L2 is sufficient.

## FAIL examples

- Writes several more paragraphs without revealing structure.
- Generates L3/L4 without evidence that L2 is insufficient.
- Produces a decorative diagram that does not clarify object relationships.
- Collapses containment and state transition into one misleading chain without qualification.

## Scoring

| Run | Route | Lowest effective rung | Structure clarity | PASS/FAIL | Failure reason |
|---|---|---|---|---|---|
| 1 |  |  |  |  |  |
| 2 |  |  |  |  |  |
| 3 |  |  |  |  |  |
