# Documentation Conventions

## Core Principle

One documentation structure represents one technical initiative. Every document must support the same problem statement, scope, and intended outcome.

This structure is documentation-only. It may be used as a standalone repository, inside a normal implementation repository, or within a monorepo.

## Document Responsibilities

| Document | Purpose |
|---|---|
| `README.md` | Current overview, navigation, and brief usage instructions |
| `proposal.md` | Motivation, objective, scope, constraints, and success criteria |
| Specification | Required behavior, interfaces, constraints, and acceptance criteria |
| ADR | Significant technical decision and its rationale |
| Research note | Investigation, evidence, findings, and limitations |
| Todo | Temporary working actions and checklists |
| External issue | Assigned implementation and delivery work |

## Add or Change a Feature

1. Update `proposal.md` when the initiative scope or objective changes.
2. Create or update a specification.
3. Add research when assumptions require validation.
4. Create an ADR for significant technical decisions.
5. Add temporary actions to `todos/`.
6. Create external implementation issues where needed.
7. Link related documents using relative Markdown links.
8. Update the root README.

## Conduct Research

1. Copy `templates/research-note.md`.
2. Assign the next `RES` identifier.
3. State the research question.
4. Document the method, evidence, findings, and limitations.
5. Link affected specs, ADRs, and todos.
6. Create an ADR when the research results in a decision.

Research records what was learned. An ADR records what was decided.

## Create or Change a Specification

1. Copy `templates/specification.md`.
2. Assign the next `SPEC` identifier.
3. Define behavior, interfaces, constraints, edge cases, and acceptance criteria.
4. Link related research and ADRs.
5. Add unresolved work to `todos/`.
6. Submit the change through the normal Git review process.
7. Link implementation issues where applicable.

A specification answers: **What must the system do?**

A specification in `specs/` represents current expected behavior.

## Record a Decision

1. Copy `templates/adr.md`.
2. Assign the next `ADR` identifier.
3. Record the context, considered options, decision, and consequences.
4. Link related specifications and research.
5. Submit the ADR through the normal Git review process.
6. Add it to the root README.

An ADR answers: **Why was this technical choice made?**

An ADR in `adrs/` represents a current architectural decision.

## Manage Todos

1. Copy `templates/todo-list.md`.
2. Assign the next `TODO` identifier.
3. Define a clear completion condition.
4. Link related documents and external issues.
5. Add active todos to the root README.
6. Remove finished todos from the active README list.

Todos are not authoritative for requirements or architecture.

## Identifiers

All formal document identifiers use four digits:

```text
SPEC-<four-digit-number>-<description>.md
ADR-<four-digit-number>-<decision>.md
RES-<four-digit-number>-<description>.md
TODO-<four-digit-number>-<description>.md
```

Identifiers are permanent and must not be reused. Moving a document into the archive does not change its identifier or filename.

## Lifecycle and Archive

A document's location defines whether it is current:

| Location | Meaning |
|---|---|
| `specs/` | Current specification |
| `adrs/` | Current architecture decision |
| `research/` | Active or currently relevant research |
| `todos/` | Active working item |
| `archive/specs/` | Superseded or abandoned specification |
| `archive/adrs/` | Superseded or abandoned decision |
| `archive/research/` | Completed, abandoned, or no longer relevant research |
| `archive/todos/` | Completed or cancelled todo |

Anything outside `archive/` is current or active by default.

Completed or cancelled todos may be deleted because Git preserves their history. Archive a todo only when it is referenced or historically valuable.

When archiving a document:

1. Keep its identifier and filename unchanged.
2. Update links that should continue pointing to it.
3. Link to its replacement where applicable.
4. Remove it from active sections of the root README.
5. Check for broken relative links.

## Linking Rules

Use relative Markdown links in document bodies. Do not use YAML front matter by default; filenames provide identifiers, Git provides history, and Markdown links describe relationships.

## Source of Truth

| Document | Source of truth for |
|---|---|
| `proposal.md` | Motivation, objective, and initiative boundaries |
| Specification | Required behavior and technical requirements |
| ADR | Significant technical decisions and trade-offs |
| Research note | Evidence, findings, and limitations |
| Todo | Temporary working actions |
| External issue | Assignment and implementation progress |
| `README.md` | Current summary and navigation |
| `CONVENTIONS.md` | Documentation workflow and repository rules |
| Git history | Authorship, dates, reviews, and previous versions |

Merged documents must not knowingly contradict one another. Todos and research notes do not override the proposal, specifications, or ADRs.

## Repository Boundary

Create another initiative structure when work has a different problem statement, independent objective, separate success criteria, separate lifecycle, or mostly unrelated specifications and decisions.
