# 03 AI Agents

This folder defines the operational contracts for GradeOps AI agents.

It answers:

> What does each agent do, what does it receive, what does it return, what must it never do, and how is it audited?

## Essence

`03-ai-agents` prevents the system from becoming a collection of loose prompts.

Each agent should be treated as an operational component with:

- a clear responsibility;
- structured input;
- structured output;
- uncertainty flags;
- handoff rules;
- human review checkpoints;
- logging requirements;
- acceptance criteria.

## How To Use This Folder

Start with:

1. `agents-overview.md` — overall agent architecture, common envelope, logs, model routing, and control principles.

Then use the individual contracts:

- `assessment-agent.md`;
- `rubric-agent.md`;
- `grading-agent.md`;
- `feedback-agent.md`;
- `learning-gap-agent.md`;
- `recovery-agent.md`;
- `teacher-report-agent.md`;
- `ops-agent.md`.

## What Belongs Here

- Agent responsibilities.
- Input/output contracts.
- JSON-compatible output structures.
- Agent-specific limits.
- Quality checks.
- Handoff rules.
- Logging and uncertainty rules.
- Human approval boundaries.

## What Does Not Belong Here

- Full backend architecture.
- Frontend UX copy.
- Pricing.
- Customer discovery.
- Legal policy beyond agent-relevant constraints.

## Control Principle

Agents operate the repetitive workflow. Teachers retain judgment, standards, and final approval.

No agent should silently create final grades, final feedback, or student-facing outputs without teacher review.
