# Changelog

All notable changes to `understand-first` are recorded here.

## [0.1.0] — 2026-10-09

### Added

- Initial standalone release of `understand-first`.
- Canonical preflight for assumptions, missing information, common failure mode, and one critical question.
- Understanding goal: Pattern → Root Cause → Verification → Transfer.
- Four-rung Representation Ladder.
- Evidence Gate.
- Capability candidate lifecycle: Candidate → Trial → Evidence → Review → Adopt / Revise / Reject.
- English and Simplified Chinese documentation.

### Boundary

This release is an independent synthesis of cited public ideas.

The combined protocol, Evidence Gate, and capability-transfer lifecycle are project design choices and should not be attributed to the cited authors as a single framework.

## v0.2.0 — Candidate (not released / not validated)

- Introduced a lightweight, single-pass Fast Gate: Direct / Diagnose / Represent.
- Routed directly to L1–L4 without sequential generation, preserving lowest-effective-representation behavior.
- Added optional `answer-me-with-html` runtime guidance and capability checks; HTML is not automatically L3.
- Added fallback and feedback re-routing; separated render success, comprehension, and evidence validity.
- Required explicit user request/approval for video creation.
- Added two test cases and A/B/C evaluation protocol. **All trial results remain NOT RUN.**
- Preserved Canonical Preflight and existing Evidence Gate / capability extraction.
