# SpecKit School Constitution

## 1. Project Identity

SpecKit School is an educational mini Spec Kit designed to teach Spec-Driven Development through browser-based AI chat.

It is intended for students, teachers, workshop participants, beginner developers, and instructors who need a simple way to practice structured software thinking before implementation.

SpecKit School is inspired by GitHub Spec Kit but is not an official GitHub project, distribution, extension, or replacement.

---

## 2. Constitutional Purpose

The purpose of SpecKit School is to teach learners how to move from vague ideas to structured specifications.

The project must prioritize learning, clarity, traceability, and human judgment.

The project must never encourage students to treat AI-generated output as automatically correct.

---

## 3. Sacred Principles

### 3.1 Educational Clarity Above Complexity

All commands, examples, explanations, and artifacts must be understandable by beginners.

The project must avoid unnecessary jargon.

When technical terms are needed, they must be explained in plain language.

---

### 3.2 No Gap Filling Doctrine

The AI must never fill gaps.

The AI must never infer missing requirements, business rules, user decisions, technical constraints, acceptance criteria, task dependencies, or implementation details.

The AI must never convert assumptions into facts.

The AI must never silently resolve ambiguity.

When information is missing, ambiguous, contradictory, or uncertain, the AI must mark the item with:

```text
[NEEDS HUMAN DECISION]
```

This label means:

- the AI found a gap;
- the AI is not allowed to decide on behalf of the human;
- the point cannot be treated as resolved;
- a human decision is required;
- the decision must be recorded before the item becomes part of the specification.

---

### 3.3 No Suggestions by Default

When the AI finds a gap, it must not suggest solutions by default.

The AI may only provide options if the human explicitly asks for options.

When options are requested, they must be labeled as:

```text
[OPTIONS — NOT DECISIONS]
```

Options are not decisions.

Options must never be treated as accepted until the human explicitly confirms one.

---

### 3.4 Specification Before Implementation

Implementation must not begin before the project has enough specification structure.

At minimum, the following must exist before implementation guidance:

- context
- clarifications
- specification
- tasks
- analysis
- checklist

For deeper learning, rules should also be created before tasks.

If a downstream step requires an omitted upstream artifact, the workflow must
mark the step as `[BLOCKED]` instead of reconstructing the missing artifact
automatically.

---

### 3.5 Browser-First, Upload-Optional

SpecKit School must be usable through browser-based AI chat.

The project must not require:

- local CLI installation
- multiple file uploads
- custom extensions
- advanced setup
- paid tools

The primary usage model is copy and paste from GitHub into AI chat.

Uploads are optional convenience, never a requirement.

---

### 3.6 AI as Assistant, Not Authority

AI may help generate text, questions, analysis, and implementation guidance.

However, the human remains responsible for:

- deciding unclear points;
- approving requirements;
- validating rules;
- accepting tasks;
- approving implementation guidance;
- judging final quality.

---

### 3.7 Traceability Is Mandatory

Every task must be traceable to at least one of the following:

- a requirement;
- a rule;
- a clarification decision;
- an acceptance criterion;
- a learning objective.

If a task cannot be traced, it must be marked:

```text
[NEEDS HUMAN DECISION]
```

Repository-canonical files and chat-generated artifacts must remain distinct.
`IMPLEMENTATION.md` is the repository-level guide, while `implementation.md` is
a generated workflow artifact and must never replace the canonical file.

For workflow continuity, `spec.md`, `tasks.md`, and `checklist.md` must be
treated as persisted artifacts even though they are generated through chat.

---

### 3.8 Small Artifacts, Strong Structure

Artifacts must be short, useful, and structured.

The goal is not heavy documentation.

The goal is useful documentation that guides reasoning, validation, and implementation.

---

### 3.9 Workshop-First Design

SpecKit School must work in short educational sessions.

The project must support:

- live demonstration;
- student practice;
- fast copy/paste usage;
- clear next steps;
- concise outputs.

An abbreviated workshop flow may skip steps for teaching purposes, but skipped
steps do not authorize AI to infer or silently generate prerequisites for later
commands.

---

## 4. Canonical Labels

| Label | Meaning |
|---|---|
| `[NEEDS HUMAN DECISION]` | A human must resolve this before it becomes part of the spec |
| `[OPTIONS — NOT DECISIONS]` | Possible alternatives requested by the user, not accepted decisions |
| `[ASSUMPTION — UNVERIFIED]` | A temporary assumption that must not be treated as fact |
| `[BLOCKED]` | Work cannot continue because a required decision is missing |
| `[READY FOR REVIEW]` | The artifact can be reviewed by a human |
| `[APPROVED]` | A human has explicitly approved the item |

---

## 5. Required AI Behavior

| Situation | Required Behavior |
|---|---|
| Missing information | Mark as `[NEEDS HUMAN DECISION]` |
| Ambiguous requirement | Mark as `[NEEDS HUMAN DECISION]` |
| Contradictory rule | Mark as `[NEEDS HUMAN DECISION]` |
| Undefined user role | Mark as `[NEEDS HUMAN DECISION]` |
| Missing acceptance criterion | Mark as `[NEEDS HUMAN DECISION]` |
| Unknown validation rule | Mark as `[NEEDS HUMAN DECISION]` |
| Unclear task dependency | Mark as `[NEEDS HUMAN DECISION]` |
| Missing upstream artifact | Mark as `[BLOCKED]` |
| Repo/chat artifact confusion | Mark as `[NEEDS HUMAN DECISION]` |
| Required persisted artifact absent | Mark as `[BLOCKED]` |
| User asks for options | Provide options labeled `[OPTIONS — NOT DECISIONS]` |

---

## 6. Prohibited AI Behavior

| Prohibited Behavior | Reason |
|---|---|
| Filling missing requirements | Creates false certainty |
| Guessing business rules | Corrupts the specification |
| Assuming user intent | Hides ambiguity |
| Creating acceptance criteria without source | Weakens validation |
| Resolving contradictions silently | Breaks traceability |
| Treating assumptions as decisions | Removes human accountability |
| Inventing implementation details | Bypasses approved artifacts |
| Suggesting options by default | Influences decisions before clarification |

---

## 7. Quality Gates

Before implementation guidance, the project must pass these gates:

| Gate | Requirement |
|---|---|
| Context Gate | The problem, audience, scope, and success criteria are clear |
| Clarification Gate | Important ambiguities are resolved or labeled |
| Specification Gate | Functional requirements are observable and testable |
| Rules Gate | Rules are separated from implementation details |
| Task Gate | Tasks are actionable and traceable |
| Analysis Gate | Gaps, contradictions, and weak traceability are visible |
| Checklist Gate | Readiness is explicitly approved or blocked |

---

## 8. Non-Goals

SpecKit School is not:

- a replacement for GitHub Spec Kit;
- an official GitHub project;
- an enterprise methodology;
- a complex architecture framework;
- a CLI-first tool;
- a deployment framework;
- a documentation-heavy process;
- a tool that lets AI decide for the human.

---

## 9. Governance

Any change to SpecKit School must preserve:

1. the No Gap Filling Doctrine;
2. browser-first usability;
3. beginner accessibility;
4. traceability;
5. human decision authority.

No future command, template, example, or implementation guide may override this constitution.

If any artifact violates this constitution, the artifact is invalid until corrected.

---

## 10. Versioning Rules

SpecKit School uses semantic versioning:

```text
MAJOR.MINOR.PATCH
```

- MAJOR: changes the workflow or constitutional rules;
- MINOR: adds commands, examples, or templates without breaking the workflow;
- PATCH: fixes wording, examples, typos, or minor inconsistencies.

Any change to the No Gap Filling Doctrine requires a MAJOR version change.
