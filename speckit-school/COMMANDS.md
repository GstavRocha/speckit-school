# SpecKit School Commands

This file contains all SpecKit School commands.

Copy one command at a time and paste it into a browser-based AI chat.

Do not upload files unless you explicitly want to. The default workflow is copy and paste.

---

## Global Command Rules

Every command must follow these rules:

1. Do not fill gaps.
2. Do not infer missing decisions.
3. Do not silently resolve ambiguity.
4. Do not suggest options unless the human explicitly asks.
5. Mark missing, ambiguous, contradictory, or uncertain information as:

```text
[NEEDS HUMAN DECISION]
```

6. If the human asks for options, label them as:

```text
[OPTIONS — NOT DECISIONS]
```

7. Keep outputs concise, structured, and beginner-friendly.
8. Produce Markdown that can be copied into a file.
9. If a command depends on an upstream artifact that is missing or was skipped, mark the work as `[BLOCKED]` and do not invent the missing artifact.
10. Treat `IMPLEMENTATION.md` as the repository guide and `implementation.md` as a generated chat artifact. They are not interchangeable.
11. Treat `spec.md`, `tasks.md`, and `checklist.md` as required persisted artifacts for workflow continuity.

---

## Required Persisted Artifacts

The following generated artifacts must be saved locally when produced:

- `spec.md`
- `tasks.md`
- `checklist.md`

Other generated artifacts may remain chat-only unless a human chooses to save
them.

---

# 1. /speckit-school.help

```text
/speckit-school.help

You are helping me use SpecKit School, an educational mini Spec Kit for learning Spec-Driven Development through browser-based AI chat.

Explain the workflow step by step.

Show:
1. What SpecKit School is.
2. The full workflow.
3. The fast workshop workflow.
4. What each command does.
5. What artifact each command generates.
6. Common mistakes.
7. The next recommended command.

Follow the No Gap Filling Doctrine:
- Do not infer missing information.
- Do not invent decisions.
- Do not suggest options unless I explicitly ask.
- Mark missing or unclear points as [NEEDS HUMAN DECISION].

Output in Markdown.
```

---

# 2. /speckit-school.context

```text
/speckit-school.context

Create a project context artifact for a Spec-Driven Development learning project.

The project idea is:

[PASTE PROJECT IDEA HERE]

Generate a Markdown artifact named context.md with these sections:

# Project Context

## Problem
## Target Audience
## Learning Objective
## Product Objective
## Scope
## Out of Scope
## Assumptions
## Constraints
## Success Criteria
## Open Questions

Rules:
- Do not fill gaps.
- Do not infer missing decisions.
- Do not suggest options unless I explicitly ask.
- Mark missing, ambiguous, contradictory, or uncertain information as [NEEDS HUMAN DECISION].
- Keep the artifact concise and useful for students.
```

---

# 3. /speckit-school.clarify

```text
/speckit-school.clarify

Review the project context below and identify ambiguity before specification.

Context:

[PASTE context.md HERE]

Generate a Markdown artifact named clarifications.md with these sections:

# Clarifications

## Summary
## Key Questions
## Required Human Decisions
## Confirmed Decisions
## Assumptions Marked as Unverified
## Remaining Ambiguities
## Impact on Specification

Rules:
- Do not answer the questions yourself.
- Do not infer missing decisions.
- Do not suggest options unless I explicitly ask.
- Mark each unresolved item as [NEEDS HUMAN DECISION].
- If I ask for options, label them as [OPTIONS — NOT DECISIONS].
- Keep the clarification list short and high-impact.
```

---

# 4. /speckit-school.spec

```text
/speckit-school.spec

Create a functional specification based only on the approved context and clarifications.

Context:

[PASTE context.md HERE]

Clarifications:

[PASTE clarifications.md HERE]

Generate a Markdown artifact named spec.md with these sections:

# Specification

## Overview
## Goals
## User Stories
## Functional Requirements
## User Flows
## Data Requirements
## States
## Edge Cases
## Acceptance Criteria
## Open Specification Gaps

Rules:
- Use only information explicitly present in the provided artifacts.
- Do not fill gaps.
- Do not infer missing requirements.
- Do not create acceptance criteria without a source.
- Mark missing, ambiguous, contradictory, or uncertain points as [NEEDS HUMAN DECISION].
- Do not suggest options unless I explicitly ask.
```

---

# 5. /speckit-school.rules

```text
/speckit-school.rules

Create project rules based only on the approved specification and clarifications.

Specification:

[PASTE spec.md HERE]

Clarifications:

[PASTE clarifications.md HERE]

Generate a Markdown artifact named rules.md with these sections:

# Rules

## Business Rules
## Validation Rules
## Permission Rules
## State Rules
## Error Rules
## Constraints
## Examples
## Open Rule Gaps

Rules:
- Do not invent business rules.
- Do not infer user permissions.
- Do not infer validation behavior.
- Mark missing or unclear rules as [NEEDS HUMAN DECISION].
- Do not suggest options unless I explicitly ask.
```

---

# 6. /speckit-school.tasks

```text
/speckit-school.tasks

Create actionable implementation tasks based only on the approved specification and rules.

Specification:

[PASTE spec.md HERE]

Rules:

[PASTE rules.md HERE]

Generate a Markdown artifact named tasks.md with these sections:

# Tasks

## Task Overview
## Setup Tasks
## Core Implementation Tasks
## Validation Tasks
## Review Tasks
## Task Traceability
## Blocked Tasks

Each task must include:
- Task ID
- Description
- Source requirement or rule
- Expected outcome
- Validation step

Rules:
- Do not create tasks without a source requirement or rule.
- Do not invent implementation details.
- If a task depends on a missing decision, mark it as [NEEDS HUMAN DECISION].
- Do not suggest options unless I explicitly ask.
```

---

# 7. /speckit-school.analyze

```text
/speckit-school.analyze

Analyze the consistency and traceability of the artifacts below.

Context:

[PASTE context.md HERE]

Clarifications:

[PASTE clarifications.md HERE]

Specification:

[PASTE spec.md HERE]

Rules:

[PASTE rules.md HERE]

Tasks:

[PASTE tasks.md HERE]

Generate a Markdown artifact named analysis.md with these sections:

# Analysis

## Summary
## Artifact Coverage
## Consistency Review
## Traceability Review
## Gaps
## Contradictions
## Risks
## Recommendations
## Readiness Signal

Use this readiness signal:
- Ready
- Almost Ready
- Not Ready

Rules:
- Do not fix the artifacts.
- Do not fill gaps.
- Do not infer decisions.
- Do not suggest solutions unless I explicitly ask.
- Mark missing, ambiguous, contradictory, or uncertain points as [NEEDS HUMAN DECISION].
```

---

# 8. /speckit-school.check

```text
/speckit-school.check

Create a readiness checklist based on the artifacts below.

Specification:

[PASTE spec.md HERE]

Rules:

[PASTE rules.md HERE]

Tasks:

[PASTE tasks.md HERE]

Analysis:

[PASTE analysis.md HERE]

Generate a Markdown artifact named checklist.md with these sections:

# Checklist

## Context Check
## Clarification Check
## Specification Check
## Rules Check
## Tasks Check
## Analysis Check
## Traceability Check
## Ambiguity Check
## Readiness Decision

Rules:
- Do not approve implementation if unresolved [NEEDS HUMAN DECISION] items exist.
- Do not fill gaps.
- Do not infer missing decisions.
- Do not suggest options unless I explicitly ask.
- The readiness decision must be one of:
  - Ready
  - Almost Ready
  - Not Ready
```

---

# 9. /speckit-school.implement

```text
/speckit-school.implement

Create implementation guidance based only on approved artifacts.

Specification:

[PASTE spec.md HERE]

Rules:

[PASTE rules.md HERE]

Tasks:

[PASTE tasks.md HERE]

Analysis:

[PASTE analysis.md HERE]

Checklist:

[PASTE checklist.md HERE]

Generate a Markdown artifact named implementation.md with these sections:

# Implementation Guide

## Implementation Summary
## Required Approved Artifacts
## Task Execution Order
## Human Review Points
## Validation Steps
## Blocked Items
## Completion Criteria

Rules:
- Do not implement or guide implementation for unresolved [NEEDS HUMAN DECISION] items.
- Do not invent requirements.
- Do not invent rules.
- Do not invent implementation details.
- Do not bypass the checklist.
- If the checklist is Not Ready, mark implementation as [BLOCKED].
- If the checklist is Almost Ready, only guide the approved parts.
- If the checklist is Ready, guide implementation task by task.
```

---

## Command-to-Artifact Table

| Command | Artifact |
|---|---|
| `/speckit-school.help` | no required artifact |
| `/speckit-school.context` | `context.md` |
| `/speckit-school.clarify` | `clarifications.md` |
| `/speckit-school.spec` | `spec.md` |
| `/speckit-school.rules` | `rules.md` |
| `/speckit-school.tasks` | `tasks.md` |
| `/speckit-school.analyze` | `analysis.md` |
| `/speckit-school.check` | `checklist.md` |
| `/speckit-school.implement` | `implementation.md` |
