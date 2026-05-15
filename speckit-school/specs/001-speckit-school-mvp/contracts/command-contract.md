# Command Contract: SpecKit School MVP

## Purpose

Define the public command interface of SpecKit School as a prompt-and-artifact
contract for browser-based AI chat.

## Contract Rules

1. Every command must be copyable from `COMMANDS.md`.
2. Every command must declare its intended output artifact or state that no
   artifact is required.
3. No command may invent missing upstream artifacts.
4. If a required prerequisite is absent, the command must return `[BLOCKED]`.
5. Commands must preserve the distinction between canonical repository files
   and chat-generated artifacts.

## Command Matrix

| Command | Required Input | Output | Blocking Rule |
|---|---|---|---|
| `/speckit-school.help` | None | Guidance text | None |
| `/speckit-school.context` | Project idea | `context.md` | `[BLOCKED]` if no project idea is provided |
| `/speckit-school.clarify` | `context.md` or equivalent context input | `clarifications.md` | `[BLOCKED]` if the upstream context is missing |
| `/speckit-school.spec` | Approved context and clarifications | `spec.md` | `[BLOCKED]` if required context or clarifications are missing |
| `/speckit-school.rules` | Approved spec and clarifications | `rules.md` | `[BLOCKED]` if required spec or clarifications are missing |
| `/speckit-school.tasks` | Approved spec and rules | `tasks.md` | `[BLOCKED]` if required spec or rules are missing |
| `/speckit-school.analyze` | Context, clarifications, spec, rules, tasks | `analysis.md` | `[BLOCKED]` if any required dependency is missing |
| `/speckit-school.check` | Spec, rules, tasks, analysis | `checklist.md` | `[BLOCKED]` if any required dependency is missing |
| `/speckit-school.implement` | Spec, rules, tasks, analysis, checklist | `implementation.md` | `[BLOCKED]` if required artifacts or approval conditions are missing |

## Fast Workshop Constraint

The fast workshop workflow is a didactic shortcut only.

If it omits a required upstream artifact, later commands must return
`[BLOCKED]` rather than reconstructing the missing artifact automatically.

## Persistence Constraint

- `spec.md` must be persisted.
- `tasks.md` must be persisted.
- `checklist.md` must be persisted.
- All other generated artifacts may remain transient unless a human chooses to
  save them.
