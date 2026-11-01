# Optional Representation Runtime Adapter (v0.2 Candidate)

The runtime is an **optional executor**, not the owner of routing. `understand-first` chooses the initial level; the executor verifies feasibility and renders. Renderer recommendations never override the choice automatically.

## Levels and execution

| Need | Level | Possible executor | Boundary |
|---|---|---|---|
| Clear information | L1 | Native answer | Do not render for decoration |
| Static relationships | L2 | Native diagram, `answer-me-with-html` flow/tree/sequence/timeline/er | HTML output remains L2 if static |
| Genuine manipulation | L3 | A runtime with real state-dependent controls | `answer-me-with-html` ask/comment/reply is feedback, **not proof of a parameter simulation engine** |
| Temporal/dynamic | L4 | Video/animation-capable runtime | Video only after explicit user request/approval |

## `answer-me-with-html`: observed documentation boundary

Upstream: https://github.com/QingYunA/answer-me-with-html

Upstream Skill: https://github.com/QingYunA/answer-me-with-html/blob/main/skills/answer-me-with-html/SKILL.md

- Writes extended Markdown and a small structural DSL, then runs its bundled `am` CLI.
- Supports flow/tree/sequence/timeline/er/chart components and renders one-page HTML.
- Supports reader feedback using ask/comment/reply and source-linked excerpts; distinguish feedback widgets from arbitrary state-driven simulations.
- Advertises explainer-video functionality via `am video`, but its own instructions require an explicit video request.
- The documented CLI requires Node.js 20+ and a valid local installation. Never assume availability merely because a repository exists online.
- Its Skill favors proactive page generation and offers an always-on mode. Do **not** inherit this recommendation: stay with the lowest effective representation.
- Do not claim a native capability-check API or automatic cross-Skill invocation. The status values below belong to *this integration specification*.

## Minimal adapter contract (proposed, not an existing API)

Input:
```yaml
route:
  mode: represent
  level: L2
  need: structural_relationships
  preferred_runtime: answer-me-with-html
  fallback: native_diagram
```

Internal result:
```yaml
capability: SUPPORTED # SUPPORTED | DEGRADED | UNSUPPORTED
render_status: success # success | failed | not_run
warnings: []
```

Check: installation, actual feature suitability, input/dependencies, usable output, source fidelity.

- **SUPPORTED**: render and verify a usable output where tools permit.
- **DEGRADED**: disclose limitations and use an explicitly acceptable fallback.
- **UNSUPPORTED**: do not misrepresent a static form as a dynamic simulation; select another available runtime or explain the blocker.
- **NOT INSTALLED**: use a native representation; do not install or modify settings without authorization.
- **RENDER FAILED**: diagnose the technical error rather than assuming a higher level is required.

## Feedback

Treat `render_success`, `understanding_success`, and `evidence_validity` as independent outcomes. Silence is `unobserved`, not PASS.

If understanding is not resolved, diagnose the remaining blocker and re-run the Fast Gate. No automatic L2→L3→L4 escalation.

## Security and governance

Do not run third-party install scripts, change global always-on settings, or expose private source files as a side effect of explanation. Keep facts and uncertainty intact in every representation. Review source excerpts before sharing an HTML page.
