# Feature Specification: SpecKit School MVP

**Feature Branch**: `001-speckit-school-mvp`  
**Created**: 2026-05-15  
**Status**: Draft  
**Input**: User description: "Execute `speckit-specify` using `PRD.md` as the source artifact"

## Clarifications

### Session 2026-05-15

- Q: How should the fast workshop workflow behave when a downstream command depends on an artifact skipped earlier in the abbreviated flow? → A: It must mark the work as `[BLOCKED]` instead of reconstructing the missing artifact automatically.
- Q: Must chat-generated artifacts be persisted locally for the workflow to remain valid? → A: Only `spec.md`, `tasks.md`, and `checklist.md` must be persisted.
- Q: Should `CONSTITUTION.md` require its own student-facing command in the main workflow? → A: `CONSTITUTION.md` remains a canonical governance file without requiring a dedicated student-facing command in the main workflow.
- Q: Is localization a requirement for the MVP? → A: no localization requirement.

## User Scenarios & Testing

### User Story 1 - Turn an idea into structured artifacts (Priority: P1)

A student uses browser-based AI chat to transform a vague project idea into structured learning artifacts before implementation.

**Why this priority**: This is the primary educational value of SpecKit School and the core behavior described in the PRD.

**Independent Test**: Can be fully tested by giving the system a vague idea, following the documented workflow, and confirming that the chat produces the expected artifacts without requiring local setup or uploads.

**Acceptance Scenarios**:

1. **Given** a student has a vague project idea, **When** they use `/speckit-school.help` followed by the core workflow commands, **Then** they receive structured Markdown artifacts that progressively clarify scope, requirements, tasks, and readiness.
2. **Given** the student has not made a required decision, **When** a command encounters ambiguity, **Then** the output marks the gap explicitly instead of silently resolving it.
3. **Given** the student is working only in browser chat, **When** they follow the workflow, **Then** they can continue without CLI setup, custom extensions, or file uploads.

---

### User Story 2 - Run a short classroom or workshop session (Priority: P2)

A teacher or workshop facilitator uses the reduced workflow to teach Spec-Driven Development in a short session.

**Why this priority**: The PRD positions workshop usability as a key product goal, but it depends on the core student flow already existing.

**Independent Test**: Can be tested by following the fast workshop workflow and confirming that a facilitator can move a group from idea to reviewable specification-stage artifacts in one guided session, while any later dependency-bound step is surfaced as `[BLOCKED]` instead of being auto-completed.

**Acceptance Scenarios**:

1. **Given** a facilitator is running a short session, **When** they use the fast workshop workflow, **Then** the participants can reach specification outputs and continue only where required upstream artifacts are present, with later blocked steps marked explicitly when prerequisites are missing.
2. **Given** participants are beginners, **When** they read command outputs, **Then** the outputs remain concise, structured, and understandable enough to support guided learning.
3. **Given** the fast workshop workflow skipped a required upstream artifact, **When** a later command needs that artifact, **Then** the command marks the work as `[BLOCKED]` instead of reconstructing the missing content automatically.

---

### User Story 3 - Review AI output with human control and traceability (Priority: P3)

A mentor or beginner developer reviews generated artifacts to confirm that AI assistance does not replace human judgment.

**Why this priority**: Traceability and human approval are central safeguards in the PRD, but they are valuable after the core workflow exists.

**Independent Test**: Can be tested by reviewing generated artifacts and verifying that unclear points are marked, tasks remain traceable, and implementation guidance is not treated as automatically approved.

**Acceptance Scenarios**:

1. **Given** an artifact contains missing or uncertain information, **When** a reviewer inspects it, **Then** unresolved points are visibly marked for human decision.
2. **Given** a task list has been generated, **When** a reviewer checks it, **Then** each task can be traced back to a requirement, rule, decision, acceptance criterion, or learning objective.

## Edge Cases

- A user provides an incomplete or vague project idea that is not sufficient to produce a clear artifact.
- A command is asked to proceed even though required upstream artifacts or human decisions are still missing.
- A user asks the AI to suggest or decide unresolved points without explicitly requesting options.
- A user attempts to use the workflow as if implementation can start before specification and validation artifacts exist.
- A workshop user reaches a downstream command after skipping an upstream artifact in the abbreviated flow.
- A generated artifact grows beyond a concise workshop-friendly format and becomes hard for beginners to use.

## Requirements

### Functional Requirements

- **FR-001**: The system MUST define a browser-first Spec-Driven Development workflow for students using AI chat.
- **FR-002**: The system MUST keep the repository constrained to five core Markdown files: `README.md`, `CONSTITUTION.md`, `PRD.md`, `COMMANDS.md`, and `IMPLEMENTATION.md`.
- **FR-003**: The system MUST provide copyable command prompts in `COMMANDS.md` for the learning workflow.
- **FR-004**: The system MUST provide a help command that explains the full workflow, generated artifacts, common mistakes, and the next recommended step.
- **FR-005**: The system MUST provide a context command that structures a project idea into problem, audience, scope, assumptions, constraints, success criteria, and open questions.
- **FR-006**: The system MUST provide a clarify command that exposes ambiguity, unresolved decisions, and unverified assumptions before specification.
- **FR-007**: The system MUST provide a spec command that creates a functional specification using only approved context and clarifications.
- **FR-008**: The system MUST provide a rules command that defines behavior and constraints using only approved specification and clarifications.
- **FR-009**: The system MUST provide a tasks command that creates actionable tasks traceable to approved artifacts.
- **FR-010**: The system MUST provide an analyze command that checks consistency, gaps, and traceability across artifacts.
- **FR-011**: The system MUST provide a check command that evaluates whether the project is ready for implementation guidance.
- **FR-012**: The system MUST provide an implement command that generates implementation guidance only after the required specification structure exists.
- **FR-013**: The system MUST explicitly mark missing, ambiguous, contradictory, or uncertain information instead of silently resolving it.
- **FR-014**: The system MUST use `[NEEDS HUMAN DECISION]` as the canonical unresolved-decision marker in generated outputs.
- **FR-015**: The system MUST avoid suggesting options by default when a gap is found.
- **FR-016**: The system MUST allow options only when explicitly requested and MUST label them as `[OPTIONS — NOT DECISIONS]`.
- **FR-017**: The system MUST support both the full workflow and the reduced workshop workflow defined in the PRD.
- **FR-018**: The system MUST mark downstream work as `[BLOCKED]` when the reduced workshop workflow skipped an upstream artifact that is still required.
- **FR-019**: The system MUST allow learning artifacts to be generated in chat without requiring them to exist as repository templates in the MVP.
- **FR-020**: The system MUST keep generated outputs concise, structured, and beginner-friendly.
- **FR-021**: The system MUST preserve human approval as the authority for decisions, validation, and implementation readiness.
- **FR-022**: The system MUST treat `CONSTITUTION.md` as a canonical governance artifact without requiring a dedicated student-facing command in the main workflow.
- **FR-023**: The MVP MUST treat localization as out of scope unless a future human decision adds it explicitly.

### Key Entities

- **Core File**: One of the five Markdown files that define the repository-level product structure and learning workflow.
- **Command Prompt**: A copyable browser-chat instruction that tells the AI which artifact to produce and which rules to follow.
- **Chat Artifact**: A generated Markdown output such as `context.md`, `clarifications.md`, `spec.md`, `rules.md`, `tasks.md`, `analysis.md`, `checklist.md`, or `implementation.md`.
- **Required Persisted Artifact**: A chat-generated artifact that must be saved locally for the workflow to remain valid: `spec.md`, `tasks.md`, and `checklist.md`.
- **Human Decision Marker**: A canonical label used to identify unresolved items that require explicit human input before they can be treated as approved.
- **Workflow Path**: Either the full command sequence or the reduced workshop sequence used to guide learning sessions.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A learner can start from a vague idea and produce, in a single browser-chat session, at least the `context`, `clarifications`, `spec`, `tasks`, `analysis`, and `checklist` artifacts without requiring CLI setup or file uploads.
- **SC-002**: The repository remains limited to exactly five core Markdown files while still supporting all workflow guidance through copyable prompts and chat-generated artifacts.
- **SC-003**: Every generated task in the learning flow can be traced to at least one requirement, rule, clarification decision, acceptance criterion, or learning objective during review.
- **SC-004**: Every command output that encounters unresolved information marks that gap explicitly rather than silently converting it into a decision.
- **SC-005**: A facilitator can complete the reduced workshop workflow with participants in one guided session, obtaining reviewable `context`, `clarifications`, and `spec` outputs, while any later step that still depends on skipped upstream artifacts returns an explicit `[BLOCKED]` signal.
- **SC-006**: The workflow preserves `spec.md`, `tasks.md`, and `checklist.md` as local artifacts for review continuity, while allowing other chat-generated artifacts to remain transient when not explicitly saved.

## Assumptions

- **[ASSUMPTION — UNVERIFIED]** Learners and facilitators have access to a browser-based AI chat interface that accepts multi-line Markdown prompts.
- **[ASSUMPTION — UNVERIFIED]** The educational MVP is evaluated primarily in workshop and classroom contexts rather than enterprise delivery contexts.
- **[ASSUMPTION — UNVERIFIED]** Generated learning artifacts other than `spec.md`, `tasks.md`, and `checklist.md` may remain chat-only unless a human chooses to save them.
- **[ASSUMPTION — UNVERIFIED]** Human reviewers are available to approve unresolved decisions before implementation guidance is treated as actionable.
