# Solution

GradeOps AI is an AI-operated assessment workflow for programming education.

It helps educators move from a learning goal to reviewed feedback and teacher reports through a controlled agent workflow.

## Core Approach

- One workflow from assessment setup to reporting.
- Specialized agents for repetitive assessment operations.
- Teacher approval on important outputs.
- Structured evidence capture from day one.
- Auditable logs for AI actions, cost, usage, and decisions.
- A narrow MVP focused on practical programming assessments.

## MVP Workflow

1. Teacher defines what they want to evaluate.
2. Assessment Agent generates the activity.
3. Rubric Agent creates and validates criteria.
4. Students submit answers or code.
5. Grading Agent analyzes submissions against the rubric.
6. Feedback Agent drafts personalized feedback.
7. Learning Gap Agent identifies recurring issues.
8. Recovery Agent suggests reinforcement activities.
9. Teacher reviews and approves.
10. Teacher Report Agent prepares the final report.
11. Ops Evidence Agent records usage, costs, outcomes, and agent logs.

## Agent Responsibilities

| Agent | Responsibility | Output |
| --- | --- | --- |
| Assessment Agent | Generate assessment activities from a learning goal. | Activity brief, instructions, expected evidence. |
| Rubric Agent | Create and validate grading criteria. | Rubric, criteria weights, consistency notes. |
| Grading Agent | Analyze submissions against the rubric. | Suggested score, rubric evidence, uncertainty flags. |
| Feedback Agent | Draft student-facing feedback. | Personalized feedback and improvement advice. |
| Learning Gap Agent | Detect repeated misconceptions. | Gap summary and affected students/cohorts. |
| Recovery Agent | Suggest reinforcement work. | Recovery activities tied to specific gaps. |
| Teacher Report Agent | Summarize the assessment run. | Teacher-facing report and next-step recommendations. |
| Ops Evidence Agent | Capture operational proof. | Logs, cost estimates, usage events, time-saved evidence. |

## Human Control Model

The product should be explicit about authority:

- agents suggest;
- teachers review;
- teachers approve;
- approved outputs can be delivered to students;
- rejected or edited outputs remain part of the audit trail.

This avoids the most dangerous misinterpretation: that GradeOps AI replaces teacher judgment.

## Evidence Model

Each agent execution should record:

- timestamp;
- teacher or account;
- assessment;
- agent name;
- model used;
- input summary;
- structured output summary;
- status;
- teacher approval state;
- estimated cost;
- estimated time saved;
- final action taken.

This evidence is not only observability. It is part of the business narrative for the hackathon.

## Cost Evidence Model

Each assessment run should also calculate:

- input tokens by agent;
- output tokens by agent;
- model used by agent;
- estimated cost per agent execution;
- retries and failed calls;
- cost per assessment;
- cost per graded submission;
- cost per active teacher;
- revenue attached to the customer or pilot;
- whether the revenue is arms-length or related-party.

This prevents a weak interpretation of the product as a demo. GradeOps AI should prove it understands its unit economics.

## Technical Direction

The MVP should use a simple, defensible architecture:

- frontend for teacher workflow and dashboard;
- backend API for orchestration and persistence;
- Gemini API for at least one deployed LLM call;
- at least one Google Cloud product in production;
- structured storage for assessments, submissions, rubrics, feedback, and logs;
- operational dashboard for usage, agent runs, cost, and evidence.

Google Cloud Run, Firebase, Firestore, Cloud SQL, Cloud Storage, and Cloud Logging are valid candidates depending on implementation speed and team preference.

Personal AI subscriptions can be used for development acceleration, but not as the production grading runtime. The deployed product must use traceable API/cloud billing and save agent execution evidence.

## Model Routing Direction

Use model routing to control cost:

| Workload | Model Policy |
| --- | --- |
| Assessment generation | Gemini Flash-class model. |
| Rubric generation and validation | Gemini Flash-class model. |
| Bulk grading | Gemini Flash-Lite-class model by default. |
| Individual feedback | Flash-Lite by default, Flash fallback for difficult cases. |
| Teacher reports | Gemini Flash-class model. |
| Premium review | Stronger fallback model only when needed. |

## Value Proposition

### For Teachers

- Reduce grading and feedback workload.
- Improve feedback consistency.
- Detect learning gaps earlier.
- Keep control over evaluation decisions.
- Prepare reports faster.

### For Students

- Receive faster feedback.
- Understand mistakes more clearly.
- Get targeted recovery activities.
- Benefit from more consistent assessment criteria.

### For Small Education Providers

- Operate like a larger academic team without hiring more staff.
- Standardize assessment quality across cohorts.
- Produce clearer evidence of learning outcomes.
- Reduce operational bottlenecks.
- Create a repeatable assessment workflow.

## Strategic Differentiator

GradeOps AI is not a generic quiz generator.

It is an AI-native assessment operations platform where agents run meaningful workflow steps and teachers retain final pedagogical authority.

## Hackathon Relevance

GradeOps AI is designed to produce the evidence needed for a credible AI venture:

- real users;
- real assessment runs;
- usage events;
- agent logs;
- teacher approvals;
- time saved;
- customer feedback;
- payment evidence;
- cost tracking;
- demo-ready operational dashboard.

## Core Principle

AI operates the repetitive workflow. Teachers retain judgment, standards, and final approval.
