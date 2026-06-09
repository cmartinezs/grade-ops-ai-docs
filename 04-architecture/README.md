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
