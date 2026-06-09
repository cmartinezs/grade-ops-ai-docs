# 99 Decisions Consolidated

> Generated for NotebookLM from `99-decisions`. This is a full-content consolidation, not a summary.

## Source Files

- `99-decisions/README.md`
- `99-decisions/adr-template.md`

## Consolidated Content


---

## Source: `99-decisions/README.md`

# 99 Decisions

This folder records important decisions that should remain visible over time.

It answers:

> What did we decide, why did we decide it, and what tradeoffs does that create?

## Essence

`99-decisions` is for durable decisions, not notes.

Use this folder when a choice affects multiple documents, implementation direction, business strategy, architecture, scope, or future contributors.

## How To Use This Folder

Use `adr-template.md` to create new decision records.

Recommended naming:

```text
YYYY-MM-DD-short-decision-title.md
```

Examples:

- `2026-06-08-use-gradeops-ai-name.md`;
- `2026-06-08-price-by-graded-submissions.md`;
- `2026-06-08-mermaid-diagram-standard.md`.

## What Belongs Here

- Architecture decisions.
- Business model decisions.
- Product scope decisions.
- Naming decisions.
- Pricing model decisions.
- Compliance or hackathon interpretation decisions.
- Documentation conventions that affect the whole repo.

## What Does Not Belong Here

- Meeting notes.
- Raw brainstorming.
- Temporary todos.
- Implementation details that are not decision-worthy.

## Decision Quality Bar

A decision record should explain:

- context;
- decision;
- rationale;
- consequences;
- owner;
- status;
- date.

## Current Template

Use:

- `adr-template.md`


---

## Source: `99-decisions/adr-template.md`

# ADR Template

- Status:
- Date:
- Decision owner:

## Context
What problem or decision is being addressed?

## Decision
What was decided?

## Rationale
Why is this the best choice now?

## Consequences
What becomes easier, harder, or riskier because of this decision?

