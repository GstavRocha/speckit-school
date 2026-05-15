# Tasks: SpecKit School MVP

**Input**: Design documents from `/specs/001-speckit-school-mvp/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: Tests are not explicitly requested in the feature specification. Validation is performed through workflow walkthroughs, artifact review, and checklist verification.

**Organization**: Tasks are grouped by user story to enable independent implementation and validation of each educational workflow increment.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- Canonical repository files live at the repository root
- Feature-planning artifacts live under `specs/001-speckit-school-mvp/`
- Validation artifacts are referenced from the feature directory and repository root

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Establish the feature workspace and shared planning artifacts

- [x] T001 Review `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/spec.md`, `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/plan.md`, and `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/research.md` to confirm the implementation scope
- [x] T002 [P] Confirm canonical governance constraints in `/home/gustavo/SPECKITSCHOOL/speckit-school/.specify/memory/constitution.md` before editing repository-facing artifacts
- [x] T003 [P] Review `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/contracts/command-contract.md` and `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/data-model.md` as the interface and artifact reference baseline

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Align the canonical repository files with the constitution before user-story-specific improvements

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

- [x] T004 Update `/home/gustavo/SPECKITSCHOOL/speckit-school/CONSTITUTION.md` so the learner-facing constitution remains aligned with `/home/gustavo/SPECKITSCHOOL/speckit-school/.specify/memory/constitution.md`
- [x] T005 Update `/home/gustavo/SPECKITSCHOOL/speckit-school/PRD.md` so workflow blocking, artifact boundaries, and persistence rules remain canonical
- [x] T006 Update `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md` so every command honors `[BLOCKED]`, artifact boundaries, and no-gap-filling behavior
- [x] T007 Update `/home/gustavo/SPECKITSCHOOL/speckit-school/IMPLEMENTATION.md` so implementation guidance remains consistent with persisted artifacts, governance, and blocking rules

**Checkpoint**: Canonical governance and command rules are aligned across the repository

---

## Phase 3: User Story 1 - Turn an idea into structured artifacts (Priority: P1) 🎯 MVP

**Goal**: Ensure a student can move from a vague idea to structured SDD artifacts through browser chat without hidden assumptions

**Independent Test**: A student can follow the documented workflow from `README.md` and `COMMANDS.md`, produce the required artifacts, and see unresolved items marked instead of auto-resolved

### Implementation for User Story 1

- [x] T008 [US1] Update `/home/gustavo/SPECKITSCHOOL/speckit-school/README.md` so the student workflow, five canonical files, and browser-first usage are clearly explained
- [x] T009 [US1] Refine `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md` so `/speckit-school.help`, `/speckit-school.context`, `/speckit-school.clarify`, and `/speckit-school.spec` form a coherent learner path
- [x] T010 [US1] Update `/home/gustavo/SPECKITSCHOOL/speckit-school/PRD.md` so product requirements and command behavior remain traceable to the student workflow
- [x] T011 [US1] Validate the artifact authority model against `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/contracts/command-contract.md` and record any required command wording adjustments in `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md`
- [x] T012 [US1] Run the documented student flow using `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/quickstart.md` and confirm that `spec.md`, `tasks.md`, and `checklist.md` are treated as required persisted artifacts

**Checkpoint**: User Story 1 delivers a complete and reviewable student-facing MVP path

---

## Phase 4: User Story 2 - Run a short classroom or workshop session (Priority: P2)

**Goal**: Ensure instructors can use an abbreviated workshop flow without allowing skipped prerequisites to be silently reconstructed

**Independent Test**: An instructor can run the fast workshop workflow and confirm that omitted prerequisites lead to `[BLOCKED]` instead of automatic recovery

### Implementation for User Story 2

- [x] T013 [P] [US2] Update `/home/gustavo/SPECKITSCHOOL/speckit-school/README.md` to explain the difference between the full workflow and the fast workshop workflow
- [x] T014 [US2] Refine `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md` so the fast workshop flow explicitly communicates when later commands depend on skipped artifacts
- [x] T015 [US2] Update `/home/gustavo/SPECKITSCHOOL/speckit-school/PRD.md` to preserve the didactic-only nature of the fast workshop path
- [x] T016 [US2] Validate `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md` and `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/contracts/command-contract.md` so `/speckit-school.rules` remains an explicit prerequisite for downstream workflow steps
- [x] T017 [US2] Validate `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/quickstart.md` against the fast workshop flow and confirm that downstream blocking behavior is clearly testable

**Checkpoint**: User Story 2 supports classroom use without violating workflow dependency integrity

---

## Phase 5: User Story 3 - Review AI output with human control and traceability (Priority: P3)

**Goal**: Ensure mentors and beginner developers can review outputs, understand artifact authority, and maintain human approval over implementation readiness

**Independent Test**: A reviewer can inspect the repository documents and generated artifacts, identify where approval is required, and confirm that no canonical file can be replaced by a chat artifact

### Implementation for User Story 3

- [x] T018 [P] [US3] Update `/home/gustavo/SPECKITSCHOOL/speckit-school/CONSTITUTION.md` and `/home/gustavo/SPECKITSCHOOL/speckit-school/IMPLEMENTATION.md` so review checkpoints and approval rules are explicit for mentors
- [x] T019 [US3] Refine `/home/gustavo/SPECKITSCHOOL/speckit-school/analysis.md` so the review narrative stays aligned with current PRD and constitution decisions
- [x] T020 [US3] Review `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/data-model.md` and `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/contracts/command-contract.md` against repository wording to confirm canonical terms are used consistently
- [x] T021 [US3] Validate `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md` and `/home/gustavo/SPECKITSCHOOL/speckit-school/IMPLEMENTATION.md` so `[NEEDS HUMAN DECISION]`, `[ASSUMPTION — UNVERIFIED]`, and `[BLOCKED]` are applied consistently in review-facing guidance

**Checkpoint**: User Story 3 makes governance, approval, and review traceability explicit

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Final cross-artifact cleanup and validation across all user stories

- [x] T022 [P] Reconcile `/home/gustavo/SPECKITSCHOOL/speckit-school/README.md`, `/home/gustavo/SPECKITSCHOOL/speckit-school/PRD.md`, `/home/gustavo/SPECKITSCHOOL/speckit-school/COMMANDS.md`, `/home/gustavo/SPECKITSCHOOL/speckit-school/CONSTITUTION.md`, and `/home/gustavo/SPECKITSCHOOL/speckit-school/IMPLEMENTATION.md` for terminology consistency
- [x] T023 Re-run the validation path described in `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/quickstart.md` and update `/home/gustavo/SPECKITSCHOOL/speckit-school/analysis.md` if any new mismatches are found
- [x] T024 Confirm that `/home/gustavo/SPECKITSCHOOL/speckit-school/specs/001-speckit-school-mvp/checklists/requirements.md` still reflects the implemented repository behavior

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Story 1 (Phase 3)**: Depends on Foundational completion
- **User Story 2 (Phase 4)**: Depends on Foundational completion and benefits from User Story 1 wording alignment
- **User Story 3 (Phase 5)**: Depends on Foundational completion and benefits from User Stories 1 and 2 being stable
- **Polish (Phase 6)**: Depends on all targeted user story work being complete

### User Story Dependencies

- **User Story 1 (P1)**: First MVP increment and baseline for student-facing flow
- **User Story 2 (P2)**: Depends on the core learner path already being coherent
- **User Story 3 (P3)**: Depends on student and workshop flows being stable enough to review and govern

### Within Each User Story

- Repository-facing explanation changes should be made before cross-artifact validation
- Contract and model validation should occur after the corresponding command or governance wording is updated
- Story validation should happen before moving to the next priority

### Parallel Opportunities

- `T002` and `T003` can run in parallel
- `T013` and `T018` can run in parallel once foundational tasks are complete
- `T022` can run in parallel with final validation preparation after story-level edits are done

---

## Parallel Example: User Story 2

```text
Task: "Update /home/gustavo/SPECKITSCHOOL/speckit-school/README.md to explain the difference between the full workflow and the fast workshop workflow"
Task: "Update /home/gustavo/SPECKITSCHOOL/speckit-school/CONSTITUTION.md and /home/gustavo/SPECKITSCHOOL/speckit-school/IMPLEMENTATION.md so review checkpoints and approval rules are explicit for mentors"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational
3. Complete Phase 3: User Story 1
4. **STOP and VALIDATE**: Confirm the student-facing workflow works end to end

### Incremental Delivery

1. Complete Setup + Foundational
2. Deliver User Story 1 as the baseline student flow
3. Add User Story 2 for workshop-safe abbreviated usage
4. Add User Story 3 for governance and reviewer clarity
5. Finish with cross-artifact validation and terminology cleanup

### Parallel Team Strategy

With multiple contributors:

1. One contributor aligns governance and canonical files
2. One contributor focuses on student/workshop wording
3. One contributor focuses on review and traceability validation

---

## Notes

- `[P]` tasks are parallelizable and should avoid editing the same file at the same time
- `[US1]`, `[US2]`, and `[US3]` labels map directly to the clarified user stories in `spec.md`
- `spec.md`, `tasks.md`, and `checklist.md` remain required persisted artifacts throughout implementation
- Any missing prerequisite discovered during execution must be surfaced as `[BLOCKED]` rather than inferred or auto-filled
