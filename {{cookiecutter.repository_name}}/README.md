# {{ cookiecutter.repository_name | replace('-', ' ') | replace('_', ' ') | title }}

Documentation for one technical initiative.

## Objective

Describe the outcome this initiative should achieve.

## Scope

### In Scope

- Define the first in-scope item.

### Out of Scope

- Define the first out-of-scope item.

## Working with This Documentation

- Define or change behavior in a specification.
- Record significant technical choices in an ADR.
- Capture investigations in a research note.
- Track temporary actions in `todos/`.
- Use an external issue tracker for assigned implementation work.
- See [CONVENTIONS.md](CONVENTIONS.md) for detailed rules.

## Proposal

- [Initiative proposal](proposal.md)

## Specifications

- [SPEC-0001: System overview](specs/SPEC-0001-system-overview.md)

## Architecture Decisions

_No current ADRs._

## Research

_No active research notes._

## Active Todos

- [TODO-0001: Initial validation](todos/TODO-0001-initial-validation.md)

## External Work Items

- Tracking issue:
- Milestone or epic:

## Open Questions

- Add the first open question.

## Render a Document

Render only the Markdown document you are working on. No Quarto project configuration is required.

```bash
# PDF
quarto render proposal.md --to pdf
quarto render specs/SPEC-0001-system-overview.md --to pdf

# HTML
quarto render proposal.md --to html
quarto render todos/TODO-0001-initial-validation.md --to html
```

Quarto writes the rendered file next to its source document by default.
