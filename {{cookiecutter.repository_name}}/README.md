# {{ cookiecutter.project_name | title }}

Status: `Proposed`

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

## How This Repository Works

- Start with `proposal.md`. It defines the problem, objective, scope, constraints, and success criteria.
- Hold a team discussion to review the initiative. The discussion is the control point: it decides what to create or update next.
- Create only the documents you need: a research note to validate assumptions, a specification to define behavior, an ADR to record a decision, a todo for temporary action items.
- Use [CONVENTIONS.md](CONVENTIONS.md) for the full rules on identifiers, linking, lifecycle, and archiving.

### Workflow

1. Write the initial proposal.
2. Review the initiative with the team.
3. Create or update the required research note, specification, ADR, or todo.
4. Update the proposal and `README.md`.
5. Return the document to the team for review.
6. Repeat the cycle until the initiative is completed, abandoned, or superseded.

![Cradle initiative workflow](workflow.png)

For the full documentation and conventions, see the [Cradle README](https://codeberg.org/dominikfalkner/cradle/src/branch/main/README.md).

## Render a Document

No Quarto project configuration is required. Render the Markdown file you are working on:

```bash
quarto render proposal.md --to pdf
quarto render proposal.md --to html
```

Rendered files are written next to their source and are ignored by Git.
