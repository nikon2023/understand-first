# Case 03 — Escalate

## Purpose

Verify that `understand-first` escalates representation only when structure is the cognitive bottleneck.

## Test prompt

> 我还是搞不清 Replay Dream 里面 Project、Branch、MVP、Run、Evidence、State、Gate 之间到底是什么关系。

## Expected route

```text
Relationship confusion
→ brief L1 definitions
→ detect structural bottleneck
→ L2 diagram
→ stop
```

## Expected behavior

The response may first give one-line definitions.

It should then switch to a structural representation because the user explicitly cannot reconstruct the relationships from prose.

A minimal acceptable shape is:

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

The exact topology may differ if the response correctly distinguishes containment from state transition.

## PASS criteria

- Recognizes that relationships, not vocabulary, are the main difficulty.
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
