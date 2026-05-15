# PRD — SpecKit School

## 1. Product Overview

SpecKit School is an educational mini Spec Kit for learning Spec-Driven Development through browser-based AI chat.

The product helps students transform vague ideas into structured artifacts before implementation.

The project is intentionally reduced to five Markdown files:

```text
README.md
CONSTITUTION.md
PRD.md
COMMANDS.md
IMPLEMENTATION.md
```

---

## 2. Problem Statement

Students using AI tools often move directly from vague prompts to generated code.

This creates problems:

- unclear requirements;
- hidden assumptions;
- weak validation;
- untraceable tasks;
- AI-generated decisions;
- lack of human review;
- confusion between prompting and specifying.

SpecKit School solves this by giving students a lightweight SDD workflow that works directly in browser chat.

---

## 3. Product Vision

SpecKit School should help students develop one professional habit:

> Think in specifications before asking AI to implement.

---

## 4. Product Goals

| Goal | Description |
|---|---|
| Teach SDD | Introduce Spec-Driven Development through practice |
| Reduce ambiguity | Make unclear information visible |
| Prevent AI guessing | Enforce the No Gap Filling Doctrine |
| Support browser chat | Work without local setup or uploads |
| Improve traceability | Connect requirements, decisions, tasks, and implementation |
| Support workshops | Be usable in short classroom or lab sessions |
| Keep the repo small | Reduce the project to five Markdown files |

---

## 5. Target Audience

| Audience | Need |
|---|---|
| Students | Learn how to structure ideas before coding |
| Beginner developers | Use AI more intentionally |
| Teachers | Teach SDD with a simple workflow |
| Workshop participants | Practice SDD quickly in a browser |
| Technical mentors | Guide junior developers with clear artifacts |

---

## 6. Browser-Based Constraint

SpecKit School must be usable through a browser-based AI chat interface.

The core workflow must not require:

- file uploads;
- CLI installation;
- local tooling;
- custom extensions;
- paid platform features;
- complex setup.

The primary workflow is copy and paste.

---

## 7. Core Workflow

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

## 8. Fast Workshop Workflow

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

This fast workflow is a didactic shortcut for workshops.

It must not authorize the AI to reconstruct skipped artifacts automatically.

If a later command requires an artifact that was skipped in the fast path, the
command must mark the work as `[BLOCKED]` and request the missing artifact or
human decision explicitly.

---

## 9. Product Scope

### In Scope

| Item | Description |
|---|---|
| Five Markdown files | Entire project must fit into five core files |
| Browser chat usage | Commands must work by copy/paste |
| Help command | Guides students step by step |
| Context command | Defines problem, audience, scope, and success |
| Clarify command | Identifies ambiguities and required decisions |
| Spec command | Defines what the system should do |
| Rules command | Defines business and behavior rules |
| Tasks command | Breaks the work into actionable tasks |
| Analyze command | Reviews consistency and traceability |
| Check command | Validates readiness |
| Implement command | Guides implementation from approved artifacts |
| No Gap Filling | Prevents AI from inventing missing information |
| Canonical artifact boundaries | Distinguishes repository files from chat-generated artifacts |
| Workflow blocking behavior | Prevents downstream commands from auto-filling skipped prerequisites |

### Out of Scope

| Item | Reason |
|---|---|
| CLI tool | Not required for browser-first learning |
| Multiple template files | Conflicts with five-file simplicity |
| Upload-heavy workflow | Not viable for many students |
| Enterprise governance | Too complex for beginners |
| Multi-agent automation | Not needed for the educational MVP |
| Deployment workflow | Outside this SDD-focused scope |

---

## 10. Functional Requirements

| ID | Requirement | Description |
|---|---|---|
| FR-001 | Five-file structure | The repository must be reduced to five Markdown files |
| FR-002 | Browser-first usage | Users must be able to use the project through browser AI chat |
| FR-003 | Copy/paste commands | Commands must be copyable from `COMMANDS.md` |
| FR-004 | Help command | `/speckit-school.help` must explain the full workflow |
| FR-005 | Context command | `/speckit-school.context` must produce project context |
| FR-006 | Clarify command | `/speckit-school.clarify` must expose ambiguity |
| FR-007 | Spec command | `/speckit-school.spec` must produce functional specification |
| FR-008 | Rules command | `/speckit-school.rules` must define rules and constraints |
| FR-009 | Tasks command | `/speckit-school.tasks` must create traceable tasks |
| FR-010 | Analyze command | `/speckit-school.analyze` must detect gaps and contradictions |
| FR-011 | Check command | `/speckit-school.check` must decide readiness |
| FR-012 | Implement command | `/speckit-school.implement` must guide implementation |
| FR-013 | No Gap Filling | AI must never fill, infer, or silently resolve gaps |
| FR-014 | Canonical labels | Gaps must use `[NEEDS HUMAN DECISION]` |
| FR-015 | No default suggestions | AI must not suggest options unless explicitly asked |
| FR-016 | Human approval | Decisions must be made or approved by a human |
| FR-017 | Workflow dependency integrity | Commands must not reconstruct missing upstream artifacts automatically |
| FR-018 | Blocking behavior | If a required artifact or decision is missing, the command must mark the work as `[BLOCKED]` |
| FR-019 | Repository versus chat artifact boundary | The product must distinguish the five repository files from generated chat artifacts |
| FR-020 | Implementation artifact distinction | `IMPLEMENTATION.md` and `implementation.md` must be treated as different artifacts with different roles |

---

## 11. Non-Functional Requirements

| ID | Requirement | Description |
|---|---|---|
| NFR-001 | Simplicity | The project must remain small and easy to understand |
| NFR-002 | Readability | All content must be readable Markdown |
| NFR-003 | Learnability | A beginner must understand the workflow quickly |
| NFR-004 | Low friction | No upload or local setup should be required |
| NFR-005 | Traceability | Tasks must connect to requirements, rules, or decisions |
| NFR-006 | Human control | AI must never replace human judgment |
| NFR-007 | Consistency | Commands must follow consistent output patterns |
| NFR-008 | Workshop usability | The workflow must fit short learning sessions |
| NFR-009 | Artifact clarity | A beginner must be able to distinguish repository-canonical files from chat-generated artifacts |
| NFR-010 | Dependency transparency | Missing prerequisites must be visible instead of silently bypassed |

---

## 12. Artifact Authority Model

SpecKit School uses two artifact layers:

### Repository-Canonical Files

These files define the product itself and are part of the repository contract:

```text
README.md
CONSTITUTION.md
PRD.md
COMMANDS.md
IMPLEMENTATION.md
```

### Chat-Generated Artifacts

These artifacts are workflow outputs created in browser chat.

They may remain only in chat until a human chooses to persist them.

For MVP workflow continuity, `spec.md`, `tasks.md`, and `checklist.md` are the
required persisted chat-generated artifacts.

`IMPLEMENTATION.md` must never be treated as the same artifact as
`implementation.md`.

---

## 13. Artifacts Generated in Chat

Although the repository has only five files, the student may generate these learning artifacts in the chat:

| Artifact | Generated By | Purpose |
|---|---|---|
| `context.md` | `/speckit-school.context` | Defines problem and scope |
| `clarifications.md` | `/speckit-school.clarify` | Captures questions and decisions |
| `spec.md` | `/speckit-school.spec` | Defines expected behavior |
| `rules.md` | `/speckit-school.rules` | Defines rules and constraints |
| `tasks.md` | `/speckit-school.tasks` | Defines actionable tasks |
| `analysis.md` | `/speckit-school.analyze` | Reviews consistency |
| `checklist.md` | `/speckit-school.check` | Validates readiness |
| `implementation.md` | `/speckit-school.implement` | Guides implementation |

These artifacts do not need to exist as repository templates in the MVP. They are produced by the commands in browser chat.

---

## 14. MVP Definition

The MVP is complete when:

| Item | Acceptance |
|---|---|
| `README.md` | Explains project usage |
| `CONSTITUTION.md` | Defines sacred rules |
| `PRD.md` | Defines product requirements |
| `COMMANDS.md` | Contains all commands |
| `IMPLEMENTATION.md` | Explains how to implement and maintain the project |
| Browser workflow | Works through copy/paste |
| No Gap Filling | Enforced in every command |
| Help command | Shows students what to do next |

---

## 15. MVP Acceptance Criteria

| ID | Criterion |
|---|---|
| MVP-AC-001 | A student can use the project without uploading files |
| MVP-AC-002 | A student can copy commands from `COMMANDS.md` into browser chat |
| MVP-AC-003 | The AI marks gaps with `[NEEDS HUMAN DECISION]` |
| MVP-AC-004 | The AI does not suggest options unless asked |
| MVP-AC-005 | The help command explains the next step |
| MVP-AC-006 | The workflow supports a short workshop |
| MVP-AC-007 | The project is clearly educational |
| MVP-AC-008 | The project does not present itself as official GitHub Spec Kit |
| MVP-AC-009 | The implementation command uses only approved artifacts |
| MVP-AC-010 | No command allows AI to invent decisions |
| MVP-AC-011 | If a required upstream artifact is missing, the command marks the work as `[BLOCKED]` instead of inventing it |
| MVP-AC-012 | Students can distinguish repository files from chat-generated artifacts |
| MVP-AC-013 | `IMPLEMENTATION.md` and `implementation.md` are treated as different artifacts |

---

## 16. Success Metrics

| Metric | Expected Result |
|---|---|
| Student comprehension | Students explain prompt vs specification |
| Artifact quality | Students produce clear context, spec, and tasks |
| Ambiguity control | Students identify missing decisions |
| AI discipline | Students reject AI-invented requirements |
| Workshop viability | The flow can run in a browser during class |
| Repository simplicity | The project remains understandable with five files |

---

## 17. Risks and Mitigations

| Risk | Mitigation |
|---|---|
| Students skip specification | Use `/speckit-school.help` and `/speckit-school.check` |
| AI invents missing details | Enforce No Gap Filling Doctrine |
| Students depend on uploads | Make copy/paste the default |
| Workflow feels too long | Provide fast workshop workflow |
| Repository grows too much | Keep the five-file rule |
| Users confuse it with official Spec Kit | Add clear disclaimer |
| Users confuse repo files with chat artifacts | Make artifact authority explicit in the PRD and commands |
| Fast workflow skips required inputs | Block downstream commands instead of allowing auto-filled recovery |
| `IMPLEMENTATION.md` is confused with `implementation.md` | Keep both roles explicitly distinct in product rules |

---

## 18. Final Product Summary

SpecKit School is a five-file educational SDD framework for browser-based AI chat.

It teaches students to move from idea to specification before implementation.

Its strongest rules are that AI must never fill gaps, must never reconstruct
missing prerequisites automatically, and must preserve the distinction between
repository-canonical files and chat-generated artifacts.

The product succeeds when students stop thinking only in prompts and start thinking in specifications, decisions, traceability, and validation.
