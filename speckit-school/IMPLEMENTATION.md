# SpecKit School Implementation Guide

## 1. Implementation Goal

This document explains how to implement and maintain the SpecKit School repository using only five Markdown files.

The project must remain simple, browser-first, and educational.

---

## 2. Final Repository Structure

```text
speckit-school/
├── README.md
├── CONSTITUTION.md
├── PRD.md
├── COMMANDS.md
└── IMPLEMENTATION.md
```

No additional files are required for the MVP.

---

## 3. Implementation Principles

| Principle | Rule |
|---|---|
| Five-file simplicity | Do not split commands into multiple files for the MVP |
| Browser-first | Commands must work by copy/paste into AI chat |
| Upload-optional | No workflow may require file upload |
| Constitution-first | All commands must obey `CONSTITUTION.md` |
| No Gap Filling | AI must never infer missing decisions |
| Student-centered | Outputs must be clear for beginners |
| Implementation after validation | `/speckit-school.implement` must not bypass analysis or checklist |

---

## 4. Implementation Steps

### Step 1 — Create Repository

Create a public GitHub repository named:

```text
speckit-school
```

Description:

```text
An educational mini Spec Kit for learning Spec-Driven Development through browser-based AI chat.
```

---

### Step 2 — Add the Five Files

Create:

```text
README.md
CONSTITUTION.md
PRD.md
COMMANDS.md
IMPLEMENTATION.md
```

---

### Step 3 — Add the Constitution First

The constitution must be added before the commands are finalized.

The No Gap Filling Doctrine must be present before any command template is accepted.

---

### Step 4 — Add Commands

All commands must live inside `COMMANDS.md`.

Each command must include:

- command name;
- purpose;
- input placeholders;
- expected artifact;
- output structure;
- No Gap Filling rules.

---

### Step 5 — Validate Command Consistency

Each command must obey this checklist:

| Check | Required |
|---|---|
| Uses browser-chat language | Yes |
| Produces copyable Markdown | Yes |
| Avoids file upload dependency | Yes |
| Does not fill gaps | Yes |
| Uses `[NEEDS HUMAN DECISION]` | Yes |
| Does not suggest options by default | Yes |
| Supports beginner learning | Yes |

---

### Step 6 — Test With a To-Do List Example

Use this simple idea:

```text
Create a To-Do List application where a user can add, complete, and delete tasks.
```

Run the fast workflow:

```text
/speckit-school.help
/speckit-school.context
/speckit-school.clarify
/speckit-school.spec
/speckit-school.tasks
/speckit-school.analyze
/speckit-school.check
```

Expected result:

- the AI should ask for missing decisions;
- the AI should not invent authentication, storage, design, or technology choices;
- unresolved points must be marked `[NEEDS HUMAN DECISION]`.
- if a skipped upstream artifact is still required later, the later step must
  return `[BLOCKED]`.

---

## 5. Implementation Command Behavior

The `/speckit-school.implement` command must be strict.

It may only guide implementation when:

1. `spec.md` exists;
2. `rules.md` exists whenever the downstream implementation step depends on it;
3. `tasks.md` exists;
4. `analysis.md` exists;
5. `checklist.md` exists;
6. no blocking `[NEEDS HUMAN DECISION]` item affects the implementation task.

The implementation workflow must also preserve the required persisted artifacts:

- `spec.md`
- `tasks.md`
- `checklist.md`

If unresolved decisions exist, the implementation guide must show:

```text
[BLOCKED]
```

Example:

```text
Task T-004: Implement task persistence
Status: [BLOCKED]
Reason: Storage method is marked as [NEEDS HUMAN DECISION].
```

---

## 6. Human Review Points

Human review is mandatory at these points:

| Point | Human Must Confirm |
|---|---|
| After context | Problem, audience, scope |
| After clarify | Decisions and unresolved gaps |
| After spec | Functional requirements |
| After rules | Rules and constraints |
| After tasks | Task traceability |
| After analyze | Gaps and contradictions |
| After check | Readiness |
| Before implement | Approved task execution |

---

## 7. Maintaining the Five-File Rule

New content should be added inside the existing five files.

| New Need | Where It Goes |
|---|---|
| New command | `COMMANDS.md` |
| New principle | `CONSTITUTION.md` |
| New requirement | `PRD.md` |
| New usage instruction | `README.md` |
| New maintenance rule | `IMPLEMENTATION.md` |

Do not add folders or extra template files in the MVP.

---

## 8. Future Expansion Rules

The project may expand beyond five files only after the MVP is validated in a real workshop.

Expansion requires a human decision and must be recorded as:

```text
[APPROVED]
```

Possible future files:

```text
examples/todo-list.md
docs/instructor-guide.md
docs/student-guide.md
docs/glossary.md
```

Until then, the five-file structure is canonical.

---

## 9. Definition of Done

The MVP implementation is complete when:

| Item | Done When |
|---|---|
| Repository exists | GitHub repo is public |
| README exists | User understands purpose and usage |
| Constitution exists | No Gap Filling Doctrine is explicit |
| PRD exists | Product scope is clear |
| Commands exist | All commands are copyable |
| Implementation exists | Maintenance rules are clear |
| Required artifacts persist | `spec.md`, `tasks.md`, and `checklist.md` are preserved for review continuity |
| Browser flow works | A student can use it without uploads |
| To-Do List test passes | AI does not fill gaps during the test |

---

## 10. Final Implementation Rule

SpecKit School is not successful because it generates code quickly.

SpecKit School is successful when it teaches students to protect the specification from ambiguity, false certainty, and AI-invented decisions.
