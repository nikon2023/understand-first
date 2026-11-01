# v0.2 A/B/C Evaluation Protocol — Candidate

## Arms

- **A**: `answer-me-with-html` upstream routing policy, including its documented rendering bias, without `understand-first`.
- **B**: `understand-first` v0.1 at an immutable pinned commit, using renderer tools available in that environment.
- **C**: `understand-first` v0.2 Fast Gate + optional Runtime Capability Check, at an immutable pinned commit.

Do not treat differences in tools, model, host, or input context as causal effects of the routing design.

## Phases

1. **Smoke baseline:** Cases 01–03, three repetitions each = **9 runs** in the v0.2 integration. Keep separately from historical v0.1 tests; don't relabel unexecuted old cases as evidence.
2. **Paired comparison:** Cases 01–03 × 3 repetitions × 3 arms = **27 runs**.
3. **L3/L4 extension:** Cases 04–05 × 3 repetitions × 3 arms = **18 runs**.

Total planned paired comparison = **45 runs**. The 9-run smoke is a separate preliminary gate, not extra completed evidence.

## Controls

- Same model/version/effort, task prompt, temperature if controllable, tools, and available runtime per arm.
- Fresh context, equivalent instructions except tested policy, no extra hints.
- Timestamp, host, commit SHA, skill version, runtime version and availability, input prompt hash/ID, actual response link, output artifact link.
- Avoid changing `SKILL.md` during a complete batch.
- Blinded human evaluation when practicable; classify disagreement and note evaluator.

## Primary metrics

- Routing Accuracy = correct initial routes / scored prompts, with explicit expected-route rubric.
- Unnecessary Render Rate = rich artifacts judged unnecessary / eligible prompts.
- Capability Match = runtimes that demonstrably implement the requested feature / selections.
- Routing Decision Latency (if logged) and Total Completion Time.
- Understanding Success: independently observed explanation/transfer check; silence = unobserved.
- Evidence Fidelity: no unjustified promotion of facts or assumptions.
- Revision Cost: measured time and edit scope for local corrections.

Distinguish route correctness from successful rendering and comprehension.

## Provisional gates

- v0.2 smoke Routing Accuracy ≥ 8/9.
- Direct 3/3 without unnecessary HTML/preflight.
- Diagnose 3/3 ends with one material question.
- No unauthorized video.
- No fabricated L3 implementation success.
- Every FAIL has a failure code and root-cause candidate.
- The paired comparison should improve overhead or unnecessary rendering without degrading understanding. A small sample supports iteration, not a general performance claim.

## Failure taxonomy

F1 Over-Diagnosis; F2 Under-Diagnosis; F3 Over-Escalation; F4 Under-Escalation; F5 Evidence Inflation; F6 Capability Mismatch; F7 Renderer Override; F8 False Understanding; F9 Routing Overhead.

## Evidence state

**NOT RUN.** Do not prepopulate scores, times, gains or PASS flags.
