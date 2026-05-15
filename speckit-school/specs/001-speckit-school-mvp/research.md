# Research: SpecKit School MVP

## Decision 1: Implement the MVP as a documentation-first workflow product

- **Decision**: Treat SpecKit School as a repository of canonical Markdown artifacts and workflow contracts rather than as a conventional software application.
- **Rationale**: The PRD, README, and implementation guide all define the MVP in terms of five repository files, browser-chat usage, and educational workflow behavior. A docs-first plan avoids inventing an application stack that the product does not require.
- **Alternatives considered**:
  - Build a standalone web application: rejected because the PRD is browser-first through AI chat, not browser-app-first.
  - Build a CLI tool: rejected because the PRD explicitly places CLI tooling out of scope for the MVP.

## Decision 2: Use Markdown artifacts and command contracts as the public interface

- **Decision**: Represent the product interface as copyable slash-command prompts plus documented artifact expectations in Markdown.
- **Rationale**: The learner-facing interface is `COMMANDS.md`, and the product succeeds when users can copy prompts into browser AI chat and receive structured Markdown outputs. This is the most direct contract surface for the MVP.
- **Alternatives considered**:
  - REST or RPC API contracts: rejected because the product exposes prompts, not network endpoints.
  - UI mock contracts only: rejected because the product contract is behavioral and text-based, not screen-based.

## Decision 3: Enforce partial persistence for workflow continuity

- **Decision**: Require local persistence for `spec.md`, `tasks.md`, and `checklist.md`, while allowing other chat-generated artifacts to remain transient unless explicitly saved by a human.
- **Rationale**: This matches the clarification outcome and balances traceability with low-friction classroom use.
- **Alternatives considered**:
  - Persist every artifact: rejected because it adds friction beyond the MVP constraint.
  - Persist nothing: rejected because review continuity and downstream workflow validation would become fragile.

## Decision 4: Preserve `[BLOCKED]` as the canonical response to missing prerequisites

- **Decision**: Any downstream command that depends on a skipped or missing upstream artifact must mark the work as `[BLOCKED]` instead of reconstructing missing content.
- **Rationale**: This is required by both the PRD and the constitution to prevent hidden gap-filling.
- **Alternatives considered**:
  - Auto-generate simple missing artifacts: rejected because it violates human decision authority.
  - Silently skip missing prerequisites: rejected because it weakens traceability and instructional clarity.

## Decision 5: Keep `CONSTITUTION.md` canonical without requiring a student-facing command

- **Decision**: `CONSTITUTION.md` remains a visible repository governance artifact without introducing a required `/speckit-school.constitution` command in the main learner workflow.
- **Rationale**: The constitution is part of product governance, but the learner workflow does not need an extra mandatory command to preserve that authority.
- **Alternatives considered**:
  - Add a learner-facing constitution command immediately: rejected because it increases workflow length without being required for the MVP.
  - Hide the constitution from learners: rejected because it would weaken governance transparency.

## Decision 6: Keep localization out of scope for the MVP

- **Decision**: Do not introduce multilingual output or localization rules in the MVP.
- **Rationale**: The PRD and clarified spec do not require multilingual support, and adding it now would widen product scope unnecessarily.
- **Alternatives considered**:
  - English plus Portuguese command support: rejected because it is a future enhancement, not a clarified MVP requirement.
  - Automatic language detection: rejected because it would introduce behavior not grounded in the current product scope.
