# Documentation Conventions

## Core Principle

One documentation structure represents one technical initiative. Every document must support the same problem statement, scope, and intended outcome.

This structure is documentation-only. It may be used as a standalone repository, inside an implementation repository, or within a monorepo.

For the initiative workflow, lifecycle, and team review process, see the [Cradle README](https://codeberg.org/dominikfalkner/cradle/src/branch/main/README.md).

## Document Responsibilities

| Document | Purpose |
|---|---|
| `README.md` | Current overview, navigation, and living index |
| `proposal.md` | Motivation, objective, scope, constraints, and success criteria |
| Specification | Required behavior, interfaces, constraints, and acceptance criteria |
| ADR | Significant technical decision and its rationale |
| Research note | Investigation, evidence, findings, and limitations |
| Todo | Temporary action items, not authoritative for requirements or architecture |
| External issue | Assigned implementation and delivery work |

## Creating Documents

To add a document, copy the matching blank from `templates/`, assign the next four-digit identifier, fill it in, and link it back to the proposal and related documents with relative Markdown links.

Do not use YAML front matter by default. Filenames provide identifiers, Git provides history, and Markdown links describe relationships.

## Identifiers

```text
SPEC-<NNNN>-<description>.md
ADR-<NNNN>-<decision>.md
RES-<NNNN>-<description>.md
TODO-<NNNN>-<description>.md
```

Identifiers are permanent and must never be reused. Moving a document into the archive does not change its identifier or filename.

## Initiative Lifecycle

An initiative has one of these statuses: `Proposed`, `Active`, `Paused`, `Completed`, `Abandoned`, or `Superseded`.

The status must be visible in both `proposal.md` and `README.md`. Active and paused initiatives must have an owner and a next review date. `Paused` must include a reason. `Paused` is not a final status.

Final statuses are `Completed`, `Abandoned`, and `Superseded`.

## Lifecycle and Archive

A document's location defines whether it is current:

| Location | Meaning |
|---|---|
| `specs/` | Current specification |
| `adrs/` | Current architecture decision |
| `research/` | Active or currently relevant research |
| `todos/` | Active working item |
| `archive/<subfolder>/` | Superseded, abandoned, or completed document |

Anything outside `archive/` is current or active by default.

Completed or cancelled todos may be deleted because Git preserves their history. Archive a todo only when it is referenced or historically valuable.

When archiving a document: keep its identifier and filename unchanged, update links, link to its replacement where applicable, remove it from active sections of the `README.md`, and check for broken relative links.

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
