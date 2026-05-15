# Inconsistency Labels: SpecKit School MVP

## Purpose

This file proposes canonical labels for the inconsistency points found during
`/speckit.analyze`.

## Proposed Labels

| ID | Location | Inconsistency | Proposed Label | Why This Label |
|---|---|---|---|---|
| IL-001 | `spec.md`, `command-contract.md`, `quickstart.md` | Resolved. The fast workshop workflow now distinguishes guaranteed specification-stage outputs from later steps that must return `[BLOCKED]` when skipped upstream artifacts are still required. | `[RESOLVED]` | The spec now aligns with the command contract and quickstart behavior. |
| IL-002 | `tasks.md` | Tasks `T008`, `T013`, and `T021` target `/home/gustavo/SPECKITSCHOOL/README.md`, while the planned repository root for the product is `speckit-school/` and other canonical files live under `/home/gustavo/SPECKITSCHOOL/speckit-school/`. | `[BLOCKED]` | Execution should stop until the target file path is corrected, otherwise work may be applied outside the intended product root. |
| IL-003 | `tasks.md`, `command-contract.md`, `quickstart.md` | The workflow requires `rules.md` for downstream steps, but `tasks.md` does not include a dedicated validation task to confirm the `/speckit-school.rules` contract and its role in the learner workflow. | `[NEEDS HUMAN DECISION]` | The implementation scope needs an explicit decision on whether `rules.md` validation is a required MVP task or intentionally covered only indirectly. |

## Label Usage Notes

- Use `[NEEDS HUMAN DECISION]` when the inconsistency changes the intended
  product behavior or workflow contract.
- Use `[BLOCKED]` when task execution should not continue until the issue is
  corrected.
- Use `[RESOLVED]` when the inconsistency has already been corrected in the
  governing feature artifacts and no further action is required.
- Do not replace these labels with implicit assumptions during implementation or
  review.
