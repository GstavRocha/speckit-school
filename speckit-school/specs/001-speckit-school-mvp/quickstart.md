# Quickstart: SpecKit School MVP

## Goal

Validate the SpecKit School MVP as a browser-first educational workflow using
the canonical repository files and persisted workflow artifacts.

## Prerequisites

- Access to the repository files:
  - `README.md`
  - `CONSTITUTION.md`
  - `PRD.md`
  - `COMMANDS.md`
  - `IMPLEMENTATION.md`
- Access to a browser-based AI chat
- A simple project idea for testing

## Recommended Test Idea

```text
Create a To-Do List application where a user can add, complete, and delete tasks.
```

## Full Workflow Validation

1. Open `COMMANDS.md`.
2. Copy `/speckit-school.help` into the AI chat.
3. Continue through:
   - `/speckit-school.context`
   - `/speckit-school.clarify`
   - `/speckit-school.spec`
   - `/speckit-school.rules`
   - `/speckit-school.tasks`
   - `/speckit-school.analyze`
   - `/speckit-school.check`
4. Persist these generated artifacts locally:
   - `spec.md`
   - `tasks.md`
   - `checklist.md`
5. Confirm that unresolved issues are labeled with `[NEEDS HUMAN DECISION]`.
6. Confirm that missing prerequisites are labeled `[BLOCKED]` rather than
   reconstructed automatically.

## Fast Workshop Validation

1. Use the fast workflow:
   - `/speckit-school.help`
   - `/speckit-school.context`
   - `/speckit-school.clarify`
   - `/speckit-school.spec`
   - `/speckit-school.tasks`
   - `/speckit-school.analyze`
   - `/speckit-school.check`
2. If a downstream command requires an artifact skipped by the fast path,
   confirm that the command returns `[BLOCKED]`.
3. Confirm that the workflow still produces concise, beginner-friendly output
   suitable for classroom review.

## Expected Outcomes

- The workflow remains usable without CLI setup or mandatory uploads.
- The AI does not invent missing rules, requirements, or decisions.
- `spec.md`, `tasks.md`, and `checklist.md` are available for review continuity.
- Repository-canonical files remain distinct from chat-generated artifacts.

## Failure Conditions

- A command silently fills a missing prerequisite.
- A chat-generated artifact is treated as a replacement for a canonical
  repository file.
- The workflow requires localization or additional application tooling not
  defined in the MVP.
