<!--
Sync Impact Report
- Version change: template -> 1.0.0
- Modified principles:
  - Placeholder principle 1 -> I. Human Decision Authority
  - Placeholder principle 2 -> II. Canonical Artifact Boundaries
  - Placeholder principle 3 -> III. Workflow Dependency Integrity
  - Placeholder principle 4 -> IV. Browser-First Educational Simplicity
  - Placeholder principle 5 -> V. Traceability Before Implementation
- Added sections:
  - Sensitive Points and Canonical Constraints
  - Workflow and Review Gates
- Removed sections:
  - None
- Templates requiring updates:
  - ✅ updated: .specify/templates/spec-template.md
  - ✅ updated: .specify/templates/plan-template.md
  - ✅ updated: .specify/templates/tasks-template.md
  - ✅ updated: COMMANDS.md
  - ✅ updated: CONSTITUTION.md
- Follow-up TODOs:
  - Review PRD.md separately if the team wants these canonical constraints reflected in product scope wording.
-->

# SpecKit School Constitution

## Core Principles

### I. Human Decision Authority
SpecKit School MUST never convert missing, ambiguous, contradictory, or
uncertain information into a resolved statement. The canonical unresolved label
is `[NEEDS HUMAN DECISION]`. Temporary defaults, assumptions, or inferred
context MUST be labeled `[ASSUMPTION — UNVERIFIED]` and MUST NOT be treated as
approved facts. The system MUST NOT suggest options unless a human explicitly
asks for them, and any options MUST be labeled `[OPTIONS — NOT DECISIONS]`.

Rationale: the project exists to teach specification discipline, not to reward
plausible guessing.

### II. Canonical Artifact Boundaries
SpecKit School MUST preserve the distinction between repository-canonical files
and chat-generated artifacts. `README.md`, `CONSTITUTION.md`, `PRD.md`,
`COMMANDS.md`, and `IMPLEMENTATION.md` are repository-level canonical files.
Lowercase artifacts such as `context.md`, `clarifications.md`, `spec.md`,
`rules.md`, `tasks.md`, `analysis.md`, `checklist.md`, and `implementation.md`
are workflow outputs that MAY exist only in chat until a human chooses to
persist them. `IMPLEMENTATION.md` MUST be treated as the repository guide for
how implementation guidance works; `implementation.md` MUST be treated as a
generated artifact, never as a replacement for the canonical repository file.

Rationale: beginners must be able to tell what belongs to the product skeleton
and what belongs to the working session.

### III. Workflow Dependency Integrity
No command MAY invent, backfill, or silently synthesize an omitted upstream
artifact. If a downstream step depends on a missing artifact, missing decision,
or omitted workflow stage, the command MUST stop and mark the work as
`[BLOCKED]` plus `[NEEDS HUMAN DECISION]` where appropriate. Abbreviated or
workshop workflows MAY skip stages for teaching purposes, but skipped stages do
not authorize downstream commands to reconstruct missing content automatically.

Rationale: a shorter workflow is only valid when its prerequisites still exist
or when the human explicitly accepts the reduced scope.

### IV. Browser-First Educational Simplicity
The default learning path MUST remain usable through browser-based AI chat with
copy-and-paste interaction. The workflow MUST avoid requiring CLI installation,
custom extensions, paid platform features, or heavy setup for normal student
use. Outputs MUST remain concise, structured, and understandable for beginners.

Rationale: educational accessibility is part of the product contract, not a
nice-to-have.

### V. Traceability Before Implementation
Implementation guidance MUST NOT proceed until the relevant specification chain
is visible and reviewable. At minimum, implementation-facing work MUST be
traceable to approved inputs and blocked whenever unresolved decisions would
change the outcome. Every task MUST trace back to at least one requirement,
rule, clarification decision, acceptance criterion, or learning objective. If
traceability cannot be shown, the item MUST be marked `[BLOCKED]` or
`[NEEDS HUMAN DECISION]`.

Rationale: traceability is the mechanism that keeps learning artifacts honest.

## Sensitive Points and Canonical Constraints

1. The fast workshop workflow is a didactic subset, not a license to bypass
   prerequisites. If a later command requires an omitted artifact, the command
   MUST report `[BLOCKED]` instead of auto-generating the missing artifact.
2. The absence of a student-facing `/speckit-school.constitution` command does
   not authorize AI to improvise governance. Repository governance is canonical
   in `.specify/memory/constitution.md`, and the learner-facing `CONSTITUTION.md`
   MUST remain aligned with it.
3. Any inconsistency between `CONSTITUTION.md` and
   `.specify/memory/constitution.md` MUST be treated as a governance mismatch
   and labeled `[NEEDS HUMAN DECISION]` until resolved. For command behavior,
   `.specify/memory/constitution.md` is the operational source of truth.
4. The distinction between `IMPLEMENTATION.md` and `implementation.md` is
   mandatory. Commands MUST never merge, rename, or treat them as the same
   artifact.
5. Chat-generated artifacts MAY remain transient, but no command may assume a
   prior artifact exists unless it is present in the conversation or explicitly
   provided by the human.

## Workflow and Review Gates

1. Governance Gate: The operational constitution exists and contains no
   unresolved template placeholders.
2. Context Gate: Problem, audience, scope, and success criteria are visible.
3. Clarification Gate: Important ambiguities are resolved or labeled.
4. Specification Gate: Functional requirements and acceptance logic are
   observable, testable, and free of silent gap-filling.
5. Rules Gate: Rules are separated from implementation details when the chosen
   workflow requires them.
6. Task Gate: Tasks are actionable, traceable, and blocked when dependencies or
   decisions are missing.
7. Analysis Gate: Contradictions, gaps, and terminology drift are visible.
8. Checklist Gate: Readiness is explicitly approved, limited, or blocked before
   implementation guidance proceeds.

## Governance

This constitution supersedes prompts, examples, templates, and implementation
guidance inside this repository.

Amendment policy:

- MAJOR: changes a core principle, label meaning, or artifact authority model.
- MINOR: adds a new principle, gate, or mandatory constraint without weakening
  existing rules.
- PATCH: clarifies wording without changing governance meaning.

Compliance policy:

- Any artifact that conflicts with this constitution is invalid until corrected.
- Any template that reintroduces automatic gap-filling or ambiguous artifact
  authority must be updated before use.
- Every review of workflow or command behavior MUST verify compliance with the
  five core principles and the sensitive-point constraints above.

**Version**: 1.0.0 | **Ratified**: 2026-05-15 | **Last Amended**: 2026-05-15
