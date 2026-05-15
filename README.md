# SpecKit School

SpecKit School is a lightweight educational framework for learning
Spec-Driven Development in browser-based AI chat.

It helps students, mentors, and workshop facilitators move from vague ideas to
structured artifacts before implementation, with explicit rules against hidden
assumptions and AI-invented decisions.

## Overview

The project is designed to teach one professional habit:

> Start with specification, not code.

Instead of jumping directly from a prompt to generated implementation,
SpecKit School guides users through a structured workflow that makes ambiguity,
decisions, traceability, and review visible.

## Highlights

- Browser-first workflow with copy-and-paste commands
- No mandatory local setup or file uploads
- Explicit handling of ambiguity through canonical labels
- Educational scope tailored for workshops, classrooms, and beginners
- Strong separation between repository-canonical files and chat-generated artifacts

## Repository Structure

The core product lives in [`speckit-school/`](speckit-school/).

Main files:

- `speckit-school/README.md`
- `speckit-school/CONSTITUTION.md`
- `speckit-school/PRD.md`
- `speckit-school/COMMANDS.md`
- `speckit-school/IMPLEMENTATION.md`

Feature artifacts created during the SpecKit workflow live under:

- `speckit-school/specs/`

## What SpecKit School Teaches

SpecKit School is built to help users:

- clarify what a system should do before implementation
- expose missing decisions instead of guessing
- break work into traceable tasks
- preserve human review authority over AI-generated output
- use AI as an assistant, not as the final decision-maker

## Core Principle

SpecKit School follows the **No Gap Filling Doctrine**.

When information is missing, ambiguous, contradictory, or uncertain, the AI
must not invent an answer. Instead, it should use canonical labels such as:

- `[NEEDS HUMAN DECISION]`
- `[ASSUMPTION — UNVERIFIED]`
- `[BLOCKED]`

## Getting Started

If you want to work with the product itself, start here:

1. Open `speckit-school/README.md`
2. Review `speckit-school/CONSTITUTION.md`
3. Read `speckit-school/PRD.md`
4. Use the prompts in `speckit-school/COMMANDS.md`

## Intended Use

SpecKit School is especially useful for:

- educational workshops
- software design classes
- mentoring sessions
- beginner developers learning structured AI-assisted workflows

## Status

This repository currently contains the consolidated SpecKit School product and
its generated planning artifacts.
