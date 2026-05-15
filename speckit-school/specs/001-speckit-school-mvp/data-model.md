# Data Model: SpecKit School MVP

## Overview

SpecKit School is a documentation-first product, so its primary data model is
artifact-oriented rather than database-oriented.

## Entities

### CoreFile

| Field | Type | Description |
|---|---|---|
| `name` | enum | One of `README.md`, `CONSTITUTION.md`, `PRD.md`, `COMMANDS.md`, `IMPLEMENTATION.md` |
| `role` | string | Canonical repository responsibility |
| `is_canonical` | boolean | Always `true` for this entity |
| `owner_scope` | string | Repository-level governance or product definition |

**Validation Rules**
- Must be one of the five canonical repository files.
- Must not be replaced by a chat-generated artifact with a similar name.

### ChatArtifact

| Field | Type | Description |
|---|---|---|
| `name` | enum | One of `context.md`, `clarifications.md`, `spec.md`, `rules.md`, `tasks.md`, `analysis.md`, `checklist.md`, `implementation.md` |
| `generated_by` | string | The command responsible for producing the artifact |
| `purpose` | string | The workflow role of the artifact |
| `must_persist` | boolean | Whether the artifact must be saved locally |
| `status` | enum | `transient`, `persisted`, `reviewed`, `approved`, `blocked` |

**Validation Rules**
- `spec.md`, `tasks.md`, and `checklist.md` must have `must_persist = true`.
- All other artifacts may remain transient unless a human chooses to save them.
- A `blocked` artifact must reference a missing prerequisite or unresolved human decision.

### CommandPrompt

| Field | Type | Description |
|---|---|---|
| `name` | string | Slash-command name |
| `input_contract` | string | Required artifact or prompt input |
| `output_artifact` | string | Intended generated artifact |
| `blocking_rule` | string | Condition that requires `[BLOCKED]` instead of progression |

**Validation Rules**
- Must correspond to a documented command in `COMMANDS.md`.
- Must not claim an output artifact that conflicts with canonical repository file boundaries.

### HumanDecisionMarker

| Field | Type | Description |
|---|---|---|
| `label` | enum | Canonical governance label |
| `meaning` | string | What the label communicates in workflow behavior |
| `blocks_progress` | boolean | Whether the label prevents downstream execution |

**Supported Labels**
- `[NEEDS HUMAN DECISION]`
- `[OPTIONS — NOT DECISIONS]`
- `[ASSUMPTION — UNVERIFIED]`
- `[BLOCKED]`
- `[READY FOR REVIEW]`
- `[APPROVED]`

### WorkflowPath

| Field | Type | Description |
|---|---|---|
| `name` | enum | `full` or `fast_workshop` |
| `steps` | ordered list | Command sequence |
| `permits_skips` | boolean | Whether it may omit intermediate steps |
| `skip_policy` | string | Rule governing omitted prerequisites |

**Validation Rules**
- `fast_workshop` may omit steps only as a didactic shortcut.
- Omitted prerequisites must not be reconstructed automatically.

## Relationships

- A `CoreFile` defines governance or product behavior for one or more
  `CommandPrompt` entities.
- A `CommandPrompt` produces zero or one `ChatArtifact`.
- A `ChatArtifact` may contain one or more `HumanDecisionMarker` entries.
- A `WorkflowPath` is composed of ordered `CommandPrompt` steps.
- `ChatArtifact.status` transitions may be constrained by `HumanDecisionMarker`
  values such as `[BLOCKED]` or `[APPROVED]`.

## State Transitions

### ChatArtifact Status

```text
transient -> persisted -> reviewed -> approved
transient -> blocked
persisted -> blocked
reviewed -> blocked
```

**Transition Notes**
- `blocked` occurs when a missing prerequisite or unresolved decision prevents
  valid continuation.
- `approved` requires human review and cannot be inferred automatically.

## Identity and Uniqueness Rules

- Each canonical `CoreFile.name` is unique within the repository root.
- Each `ChatArtifact.name` is unique within a given workflow instance.
- The pair `CommandPrompt.name + output_artifact` must remain stable across the
  documented MVP workflow.
