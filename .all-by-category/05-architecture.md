# 04 Architecture Consolidated

> Generated for NotebookLM from `04-architecture`. This is a full-content consolidation, not a summary.

## Source Files

- `04-architecture/README.md`
- `04-architecture/api-design.md`
- `04-architecture/data-model.md`
- `04-architecture/deployment.md`
- `04-architecture/security.md`
- `04-architecture/system-architecture.md`

## Consolidated Content


---

## Source: `04-architecture/README.md`

# 04 Architecture

This folder defines how the product can be built and deployed.

It answers:

> What system structure, data model, API, security posture, and deployment approach support the MVP?

## Essence

`04-architecture` translates product and agent contracts into technical design.

The architecture should support:

- teacher-reviewed workflows;
- agent orchestration;
- structured persistence;
- usage and cost evidence;
- Google Cloud / Gemini compliance;
- secure handling of assessment and submission data.

## How To Use This Folder

Use these files when designing or implementing the system:

1. `system-architecture.md` — logical components and architecture stance.
2. `data-model.md` — core entities and modeling priorities.
3. `api-design.md` — backend/API expectations.
4. `security.md` — privacy, access control, and risk posture.
5. `deployment.md` — deployment assumptions and Google Cloud direction.

## What Belongs Here

- System diagrams.
- Logical components.
- Data entities and relationships.
- API boundaries.
- Security and privacy decisions.
- Deployment topology.
- Cloud service assumptions.
- Observability and logging architecture.

## What Does Not Belong Here

- Business pricing.
- Sales scripts.
- User interview notes.
- Product backlog details.
- Full application code.

## Architecture Principle

The system should make every meaningful AI operation traceable: input, model, output, cost estimate, status, teacher approval state, and final action.

## Diagram Rule

Architecture diagrams must use Mermaid by default. Use PlantUML only when Mermaid cannot express the diagram clearly. Use ASCII only as a last fallback.


---

## Source: `04-architecture/api-design.md`

# API Design

## API goals
- Support the assessment workflow end to end
- Keep agent operations observable
- Make evidence extraction straightforward

## Representative resources
- `/assessments`
- `/rubrics`
- `/submissions`
- `/grades`
- `/feedback`
- `/learning-gaps`
- `/recovery-activities`
- `/teacher-reports`
- `/agent-logs`
- `/evidence`

## Design principle
Prefer simple, auditable APIs over broad automation surface area in the MVP.


---

## Source: `04-architecture/data-model.md`

# Data Model

## Core entities
- Teacher
- Organization
- Cohort
- Assessment
- Rubric
- Submission
- Grade record
- Feedback record
- Learning gap
- Recovery activity
- Teacher report
- Agent log
- Evidence record

## Modeling priorities
- Trace each output back to its inputs
- Store approval state for human review steps
- Separate learner artifacts from operational evidence


---

## Source: `04-architecture/deployment.md`

# Deployment

## MVP deployment assumptions
- Fast to demonstrate and iterate
- Reliable enough for small pilots
- Simple operational footprint

## Practical requirements
- Separate environments for demo and pilot use
- Persistent storage for submissions, reports, and logs
- Monitoring for agent run failures and workflow bottlenecks

This repository documents deployment assumptions only. It does not include infrastructure code.


---

## Source: `04-architecture/security.md`

# Security

## Priorities
- Protect student submissions and grading data
- Restrict access by organization and role
- Keep audit logs for grading and feedback actions
- Preserve human approval points for sensitive outputs

## MVP security baseline
- Authenticated teacher access
- Role-based permissions
- Secure storage for submissions and reports
- Logged agent actions and approval events


---

## Source: `04-architecture/system-architecture.md`

# System Architecture

## Logical components
- Teacher workspace
- Workflow orchestration layer
- Specialized assessment agents
- Submission and artifact storage
- Reporting and evidence store

## Architectural stance
The architecture should support a teacher-reviewed workflow, not full autonomy. Every major output should be attributable to an agent step and reviewable by a human operator.

