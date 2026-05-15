# SpecKit School

SpecKit School is an educational mini Spec Kit for learning Spec-Driven
Development through browser-based AI chat.

It helps students move from a vague idea to structured artifacts such as
`context.md`, `clarifications.md`, `spec.md`, `rules.md`, `tasks.md`,
`analysis.md`, `checklist.md`, and `implementation.md` without jumping
directly to code.

SpecKit School is inspired by GitHub Spec Kit and Spec-Driven Development, but
it is not an official GitHub project, distribution, or replacement.

---

## Purpose

SpecKit School exists to teach one core habit:

> Do not start with code. Start with specification.

Students should learn how to transform an initial idea into structured reasoning
before asking AI to implement anything.

---

## Browser-First Usage

The primary workflow is:

1. Open this repository.
2. Open `COMMANDS.md`.
3. Copy the command you need.
4. Paste it into a browser-based AI chat.
5. Review the generated Markdown.
6. Save required artifacts when the workflow says they must persist.
7. Continue to the next command.

File uploads are optional. They must never be required for the core workflow.

---

## Full Workflow

```text
/speckit-school.help
↓
/speckit-school.context
↓
/speckit-school.clarify
↓
/speckit-school.spec
↓
/speckit-school.rules
↓
/speckit-school.tasks
↓
/speckit-school.analyze
↓
/speckit-school.check
↓
/speckit-school.implement
```

---

## Fast Workshop Workflow

For short workshops, use:

```text
/speckit-school.help
↓
/speckit-school.context
↓
/speckit-school.clarify
↓
/speckit-school.spec
↓
/speckit-school.tasks
↓
/speckit-school.analyze
↓
/speckit-school.check
```

This is a didactic shortcut, not a full replacement for the core workflow.

If a later command still depends on an artifact skipped by the fast path, the
correct behavior is:

```text
[BLOCKED]
```

The AI must not reconstruct the missing artifact automatically.

---

## The Five Canonical Repository Files

| File | Purpose |
|---|---|
| `README.md` | Explains the project and how to use it |
| `CONSTITUTION.md` | Defines the sacred rules of the project |
| `PRD.md` | Defines the product requirements |
| `COMMANDS.md` | Contains all browser-chat commands |
| `IMPLEMENTATION.md` | Explains how to build and maintain the project |

These files define the product itself.

---

## Chat-Generated Artifacts

The workflow may generate:

- `context.md`
- `clarifications.md`
- `spec.md`
- `rules.md`
- `tasks.md`
- `analysis.md`
- `checklist.md`
- `implementation.md`

These artifacts are workflow outputs, not replacements for repository-canonical
files.

`IMPLEMENTATION.md` and `implementation.md` are different artifacts and must
never be treated as interchangeable.

---

## Required Persisted Artifacts

These workflow artifacts must be saved locally for continuity:

- `spec.md`
- `tasks.md`
- `checklist.md`

Other generated artifacts may remain transient in chat unless a human chooses
to save them.

---

## Canonical Rule

SpecKit School follows the No Gap Filling Doctrine.

The AI must never fill missing information, infer decisions, or silently
resolve ambiguity.

Whenever information is missing, ambiguous, contradictory, or uncertain, the AI
must mark it with:

```text
[NEEDS HUMAN DECISION]
```

If a required upstream artifact is missing, the AI must mark the work as:

```text
[BLOCKED]
```

The AI must not suggest options unless the human explicitly asks for options.

When options are requested, they must be labeled as:

```text
[OPTIONS — NOT DECISIONS]
```

---

## Human Review

Human review is required before implementation guidance is treated as approved.

At minimum, a human should review:

- context and clarifications
- specification and rules
- task traceability
- analysis output
- readiness checklist

---

## Positioning

SpecKit School is an educational project.

It is designed for classrooms, workshops, computer labs, and beginner
developers working in browser-based AI chat without local setup friction.
