# 02 Product Consolidated

> Generated for NotebookLM from `02-product`. This is a full-content consolidation, not a summary.

## Source Files

- `02-product/README.md`
- `02-product/assessment-modes.md`
- `02-product/curriculum-structure.md`
- `02-product/metrics.md`
- `02-product/mvp-scope.md`
- `02-product/personas.md`
- `02-product/response-intake.md`
- `02-product/student-access.md`
- `02-product/user-stories.md`
- `02-product/workflows.md`

## Consolidated Content


---

## Source: `02-product/README.md`

# 02 Product

This folder defines what the MVP must do for users.

It answers:

> What does the product experience need to include to prove the business and support a credible demo?

## Essence

`02-product` turns the project and business strategy into product behavior:

- MVP scope (two assessment modes: open and closed);
- personas;
- user stories;
- workflows;
- assessment modes and their specific flows;
- student access model;
- response intake channels;
- curriculum and subject structure;
- product metrics.

The folder is intentionally product-focused. It describes user experience, states, flows, priorities, and acceptance criteria without becoming backend architecture.

## How To Use This Folder

Use these files to drive product planning and implementation:

1. `mvp-scope.md` — what is in scope, out of scope, and required for the demo; scope matrix with priorities.
2. `personas.md` — users, buyers, operators, reviewers, and anti-personas.
3. `user-stories.md` — backlog by epic, priority, and acceptance criteria (Epics 1–13).
4. `workflows.md` — end-to-end workflows for open and closed assessment, approval states, failure flows, and evidence flow.
5. `assessment-modes.md` — open vs. closed assessment comparison, shared lifecycle, AI role per mode, question bank states, and snapshot rule.
6. `student-access.md` — student (LearnerRef) model, secure link types, invitation flow, what students can see, and security rules.
7. `response-intake.md` — digital (P0) and physical paper (P1) intake channels, OCR vs OMR, conflict resolution, and normalization to AssessmentAttempt.
8. `curriculum-structure.md` — subject/topic/learning-outcome taxonomy; P0 string tagging; P1 structured model with CurriculumNode and LearningObjective; AI-generated curriculum; Chile pack reference.
9. `metrics.md` — product, business, AI-native operations, trust, and hackathon evidence metrics.

## What Belongs Here

- User needs.
- Product flows.
- Acceptance criteria.
- MVP boundaries.
- Product lifecycle states.
- Product and activation metrics.
- Mermaid diagrams for product workflows.

## What Does Not Belong Here

- Detailed API endpoints.
- Prompt templates.
- Infrastructure choices.
- Sales scripts.
- Financial ledgers.
- Raw technical exploration.

## Diagram Rule

Product diagrams must use Mermaid by default. Use PlantUML only when Mermaid cannot express the diagram clearly. Use ASCII only as a last fallback.


---

## Source: `02-product/assessment-modes.md`

# Assessment Modes

GradeOps AI supports two assessment modes that share the same operational infrastructure but differ in question type, grading mechanism, and AI role.

The choice of mode is made by the teacher when creating an assessment. Both modes produce a `GradeResult` associated with a student, an assessment, and a subject.

## Modes

| Dimension | Open Assessment | Closed Assessment |
| --- | --- | --- |
| Response type | Code, text, development, file, extended answer | Selection of alternatives (TF, single choice, multiple choice) |
| Assessment generation | AI generates context, case, instructions, deliverables, and rubric | AI generates questions, alternatives, answer key, difficulty, and learning outcomes |
| Grading mechanism | AI suggests score against approved rubric; teacher approves | Deterministic engine compares against frozen answer key; teacher reviews exceptions |
| AI role in grading | Interpretive, uncertain, subject to approval | Structural: generate and validate; deterministic at scoring time |
| Main control checkpoint | Rubric approval + grading suggestion approval | Question curation approval + answer key approval |
| Primary risk | Subjectivity, rubric ambiguity, inconsistency | Bad answer key, ambiguous distractors, mismatch between question and snapshot |
| Best use | Practical programming tasks, code review, open-ended problems | Conceptual checks, quick knowledge verification, theory assessment |
| Teacher workload | High: review grading suggestion per student | Low: review exceptions only; review analytics after |

## Common Assessment Lifecycle

Both modes share this base lifecycle:

```mermaid
stateDiagram-v2
  [*] --> draft
  draft --> pending_teacher_review : AI output ready
  pending_teacher_review --> approved : Teacher approves
  pending_teacher_review --> draft : Teacher regenerates
  approved --> published : Teacher publishes
  published --> accepting_responses : Teacher opens
  accepting_responses --> responses_received : Responses arrive
  responses_received --> grading_in_progress : Grading starts
  grading_in_progress --> pending_teacher_review : Grading suggestions/results ready
  pending_teacher_review --> graded : Teacher confirms
  graded --> results_published : Teacher publishes results
  results_published --> archived
```

## Open Assessment Specifics

```mermaid
flowchart TD
  A[Teacher defines learning goal]
  B[Assessment Agent drafts context and instructions]
  C[Rubric Agent drafts and validates rubric]
  D[Teacher reviews and approves rubric]
  E[Students receive link or submit via teacher]
  F[Grading Agent analyzes each submission]
  G[Feedback Agent drafts feedback]
  H[Learning Gap Agent summarizes cohort gaps]
  I[Teacher reviews and approves all outputs]
  J[Results and feedback published]

  A --> B --> C --> D --> E --> F --> G --> H --> I --> J
```

### AI Role in Open Assessments

The AI generates, interprets, and suggests. The teacher validates every output that reaches a student.

| Step | AI Action | Teacher Action |
| --- | --- | --- |
| Assessment creation | Generates draft | Approves or edits |
| Rubric | Generates criteria and weights | Approves before grading |
| Grading | Suggests score per criterion with evidence | Approves, edits, or rejects |
| Feedback | Drafts student-facing text | Approves before delivery |
| Learning gaps | Summarizes cohort patterns | Confirms instructional relevance |
| Recovery | Suggests reinforcement activity | Approves before use |

## Closed Assessment Specifics

```mermaid
flowchart TD
  A[Teacher defines evaluative intent]
  B[Question Generation Agent produces question batch]
  C[Distractor Quality Agent reviews alternatives]
  D[Ambiguity Review Agent checks questions]
  E[Teacher reviews and approves questions]
  F[Approved questions enter the Question Bank]
  G[Teacher or Assessment Assembly Agent composes evaluation]
  H[Teacher approves composition and scoring policy]
  I[System creates snapshot and publishes]
  J[Students receive access link]
  K[Students respond]
  L[Deterministic grading engine scores against answer key]
  M[Teacher reviews exceptions and analytics]
  N[Teacher publishes results]
  O[Item Analytics Agent analyzes post-assessment performance]

  A --> B --> C --> D --> E --> F --> G --> H --> I --> J --> K --> L --> M --> N --> O
```

### AI Role in Closed Assessments

The AI generates and validates structure. Grading is deterministic. The teacher curates, not just approves.

| Step | AI Action | Teacher Action |
| --- | --- | --- |
| Question generation | Generates questions, alternatives, key, difficulty, outcomes | Approves/edits/rejects each question |
| Distractor quality | Flags weak distractors, bias, imbalance | Reviews flags; may accept or request regeneration |
| Ambiguity check | Flags multiple valid interpretations, missing context | Resolves before approving |
| Assessment composition | Proposes question selection, balance, punchcard, scoring | Approves final composition |
| Grading | No AI involvement; deterministic engine | Reviews exceptions (duplicates, blanks, ambiguous marks) |
| Results narrative | Item Analytics Agent interprets difficulty and gaps | Reviews before sharing |
| Recovery suggestion | Suggests reinforcement based on item analytics | Approves before use |

### Deterministic Grading Rule

For closed assessments, grading must follow this formula and never involve probabilistic AI judgment:

```text
GradeResult =
  student answer(s)
  + snapshot of frozen answer key
  + scoring policy (full credit / partial credit / penalty)
  + grade scale
  = calculated score
```

This is immutable once the assessment snapshot is published.

## Question Bank

The closed assessment mode requires a question bank. The bank is AI-native: questions are generated by agents, curated by the teacher, and versioned by the system.

```mermaid
stateDiagram-v2
  [*] --> ai_generated
  ai_generated --> pending_review
  pending_review --> approved
  pending_review --> rejected
  approved --> active
  active --> needs_revision
  needs_revision --> pending_review
  active --> retired
  active --> versioned : New version created
```

| State | Meaning | Usable in assessment |
| --- | --- | --- |
| `ai_generated` | Created by AI, not yet reviewed | No |
| `pending_review` | Awaiting teacher curation | No |
| `approved` | Teacher validated content, alternatives, and key | Yes |
| `active` | In bank and available | Yes |
| `needs_revision` | Has warnings or was flagged as ambiguous | No (unless confirmed) |
| `retired` | Blocked from future use; historical only | No |
| `rejected` | Discarded | No |
| `versioned` | Has a newer version; this version is historical | No as current |

## Snapshot Rule

When a closed assessment is published, the system must freeze:

- all questions;
- all alternatives with their order and labels;
- the answer key;
- the scoring policy;
- the grade scale.

This snapshot cannot be changed after the assessment starts. Changes require a new assessment version and a new assessment run. Any recalculation after the fact must be audited and logged.

## Mode Selection

When a teacher creates an assessment, they select the mode:

```text
Create assessment
  -> Open (practical / code)
  -> Closed (objectives / alternatives)
```

The selection determines:
- which agents run;
- which intake flow is used;
- how grading works;
- which reports are generated.

Mixed mode (open + closed in one assessment) is deferred to a future version.

## Result Model

Both modes produce the same result structure for the student:

| Field | Type | Notes |
| --- | --- | --- |
| `assessment_id` | UUID | Parent assessment |
| `learner_ref_id` | UUID | Student reference |
| `raw_score` | numeric | Points obtained |
| `weighted_score` | numeric | Applied to subject weighting |
| `final_grade` | numeric | Converted using grade scale |
| `grading_status` | enum | `calculated`, `teacher_approved`, `published_to_student` |
| `teacher_approved_by` | UUID | Nullable |
| `published_at` | timestamp | When student can see result |


---

## Source: `02-product/curriculum-structure.md`

# Curriculum Structure

GradeOps AI needs a curriculum taxonomy to anchor questions, assessments, and rubrics to subjects, topics, and learning objectives. This taxonomy enables AI to generate contextually relevant questions, helps teachers compose coherent assessments, and makes analytics and reports pedagogically meaningful.

## Why Curriculum Structure Matters

Without curriculum anchors, the Question Generation Agent has no reliable scope boundary. It may generate questions that are off-level, off-topic, or misaligned with declared learning objectives. Similarly, the Assessment Assembly Agent cannot guarantee coverage if it does not know which learning objectives a question addresses.

Curriculum structure enables:

- AI question generation with a defined scope.
- Question bank filtering by subject, topic, and learning objective.
- Closed assessment composition that guarantees curriculum coverage.
- Post-assessment reporting by topic and learning objective.
- Detection of over- or under-assessed curriculum areas.

## MVP Model (P0): Subject > Topic Tagging

For the MVP, curriculum anchoring is implemented as **string-based tagging** on questions and assessments. No complex relational curriculum model is required at P0.

```text
Subject (string)
  └── Topic (string)
      └── Learning Outcome (string)
```

Example:
```text
Subject: "Object-Oriented Programming"
Topic: "Inheritance"
Learning Outcome: "Design reusable class hierarchies using inheritance"
```

These fields are free-text at P0, populated by the teacher or suggested by the Question Generation Agent. Questions store them as `subject_area`, `topic_tags_json`, and `learning_outcome`. Assessments store them as `topic` and `learning_goal`.

This is sufficient for the hackathon MVP.

## Full Model (P1): Layered Curriculum Taxonomy

For scale — institutional use, Chile national curriculum, and multi-country expansion — GradeOps AI needs a structured, versionable curriculum taxonomy. This model is P1 and does not need to be built for the hackathon demo.

### Taxonomy Hierarchy

```text
CurriculumProvider
  └── CurriculumFramework
      └── CurriculumVersion
          └── EducationLevel
              └── Subject
                  └── CurriculumNode (axis, unit, module, topic, subtopic)
                      └── LearningObjective
                          └── Skill / Competency
```

### Simple vs. Full View

| Context | Recommended model |
| --- | --- |
| Independent teachers, bootcamps, corporate training | Simple: Subject > Topic > Learning Outcome (P0 string-based) |
| K-12 schools, institutional programs | Full: Provider > Framework > Level > Subject > Node > LO |
| International products | Multi-country: one CurriculumProvider per country/ministry |

### Curriculum Creation Sources

| Source | Description | When to use |
| --- | --- | --- |
| Manual | Teacher defines subject, units, and topics | Independent teachers, custom programs |
| AI-generated | AI proposes curriculum structure from a course description | Fast setup for new courses |
| Official | Imported from a national or institutional curriculum document | K-12 schools aligned to a national standard |

### AI-Generated Curriculum

When a teacher describes a course, GradeOps AI can generate a proposed curriculum structure.

Example input:
```text
Course: Object-Oriented Programming for first-year computer science students.
Duration: 12 weeks.
Topics: classes, objects, encapsulation, inheritance, polymorphism, interfaces, exceptions.
```

Example output:
```text
Subject: Object-Oriented Programming
Units:
  1. Foundations: Classes and Objects
  2. Encapsulation and Access Control
  3. Relationships: Inheritance
  4. Polymorphism and Abstract Design
  5. Exception Handling

Learning Outcomes:
  - Model entities using classes and objects.
  - Apply encapsulation in simple designs.
  - Implement inheritance for code reuse.
  - Use polymorphism to extend behavior.
  - Handle exceptions robustly.
```

AI-generated curriculum structures must be approved by the teacher before they can be used to constrain question generation or assessment composition.

## Linking Questions to Curriculum

Every question in the bank must carry curriculum metadata.

| Field | MVP (P0) | Full model (P1) |
| --- | --- | --- |
| Subject | `subject_area: string` | `subject_id: UUID` references `Subject` entity |
| Topic | `topic_tags_json: json` | `curriculum_node_ids: UUID[]` references `CurriculumNode` |
| Learning outcome | `learning_outcome: string` | `learning_objective_ids: UUID[]` references `LearningObjective` |
| Difficulty | `difficulty: enum` | unchanged |
| Level | `level` on assessment or question | `education_level_id: UUID` references `EducationLevel` |

### Rules

- A question must have at least one subject and one learning outcome to be `active` in the bank.
- A question with no curriculum metadata may be saved as `draft` but cannot be used in assessments.
- AI-generated questions include suggested subject, topic, and learning outcome; these are confirmed when the teacher approves the question.

## Linking Assessments to Curriculum

### Closed Assessments

A closed assessment must declare its curriculum scope before composition. This scope defines which questions from the bank are eligible.

```text
Assessment blueprint:
  subject: "Object-Oriented Programming"
  topics: ["Inheritance", "Polymorphism"]
  learning_outcomes: ["LO-04", "LO-05"]
  question_count: 15
  difficulty_distribution: { easy: 30%, medium: 50%, hard: 20% }
```

The Assessment Assembly Agent selects only questions that match the declared subject, topics, and learning outcomes. Questions from other subjects cannot be included unless the teacher explicitly overrides with a confirmation.

### Open Assessments

Open assessments are linked to curriculum less rigidly: the teacher declares the subject and intended learning outcomes, and these inform the assessment context, case, and rubric criteria.

```text
Assessment:
  subject: "Object-Oriented Programming"
  topic: "Inheritance"
  learning_outcomes: ["Design reusable class hierarchies using inheritance"]
  rubric: criteria mapped to each declared learning outcome
```

This enables post-assessment reporting by learning outcome even for open assessments.

## Curriculum Validators

Before composing or publishing a closed assessment, the system should validate curriculum coherence.

| Validator | Check | Behavior |
| --- | --- | --- |
| Subject consistency | All selected questions belong to the declared subject | Block or alert |
| Coverage completeness | All declared learning outcomes have at least one question | Alert with option to generate more |
| Level consistency | Questions match the declared student level | Alert on mismatch |
| Cross-subject contamination | A question from a different subject is included | Block or require confirmation |
| Insufficient bank | Bank has fewer approved questions than requested for the declared scope | Alert; suggest generating more or reducing count |

## Reports Enabled by Curriculum Structure

Curriculum metadata unlocks pedagogically meaningful analytics after an assessment runs.

| Report | Requires |
| --- | --- |
| Performance by subject | `subject_area` on question |
| Performance by topic | `topic_tags_json` on question |
| Performance by learning outcome | `learning_outcome` on question |
| Questions with lowest correct rate per outcome | Question + item analytics |
| Outcomes with low coverage in the assessment | Assessment blueprint + bank |
| Reinforcement suggestions by topic | Item analytics + curriculum anchors |

Example interpretation:
```text
In "Object-Oriented Programming / Inheritance":
  - cohort average: 54%
  - question with most errors: item 9 (correct rate: 21%)
  - most-chosen wrong option: B (chosen by 58% of students)
  - recommendation: reinforce use of super() and constructor chaining
```

## Chile Curriculum Pack (P1 Reference)

As a concrete P1 example, GradeOps AI could incorporate the Chilean national curriculum as an official `CurriculumProvider`.

```text
CurriculumProvider
  name: Ministerio de Educación de Chile
  country_code: CL
  provider_type: official

CurriculumFramework
  name: Currículum Nacional

EducationLevel
  name: 1° Básico

Subject
  name: Matemática

CurriculumNode (axis)
  name: Números y Operaciones

LearningObjective
  external_code: MA01 OA 09
  description: Demostrar que comprenden la adición y la sustracción de números del 0 al 20...
```

The architecture must support multiple countries, each as its own `CurriculumProvider`, without hardcoding Chilean structures into the core model.

## Scope

### P0

- String-based `subject_area`, `topic_tags_json`, and `learning_outcome` fields on questions and assessments.
- AI suggests subject/topic/outcome when generating questions; teacher confirms at curation.
- Question bank filterable by subject, topic, and learning outcome strings.
- Assessment assembly uses declared subject and outcome scope to filter eligible bank questions.
- Basic curriculum consistency warning (subject mismatch alert).

### P1

- Structured `Subject`, `CurriculumNode`, and `LearningObjective` entities in the data model.
- AI-generated curriculum structure from course description, with teacher approval.
- Closed assessment blueprint entity with coverage validation.
- Insufficient bank alert with option to generate more questions.
- Reports by learning objective with item analytics.
- Chile national curriculum pack as the first official `CurriculumProvider`.
- Multi-country framework architecture.

### P2

- Curriculum pack marketplace.
- Version-controlled official curriculum updates.
- Longitudinal reporting across curriculum versions.
- Institutional curriculum customization on top of official packs.
- Comparison between aligned and non-aligned questions.


---

## Source: `02-product/metrics.md`

# Metrics

GradeOps AI metrics must prove product value, business viability, AI-native operations, and hackathon evidence.

Metrics are not only analytics. They are part of the product and submission strategy.

## North Star Metric

> Approved feedback outputs generated for real programming submissions.

Why:

- it reflects assessment volume;
- it requires AI operation;
- it requires teacher approval;
- it creates student value;
- it connects directly to workload reduction;
- it can support pricing by graded submissions.

## Metric Groups

| Group | Purpose |
| --- | --- |
| Product usage | Prove teachers use the workflow |
| Workflow completion | Prove the product can run end to end |
| Teacher trust | Prove teachers accept or correct AI outputs |
| Student value | Prove feedback and recovery outputs are generated |
| AI-native operations | Prove agents execute meaningful work |
| Unit economics | Prove cost and pricing discipline |
| Business validation | Prove real demand and revenue |
| Hackathon evidence | Prove submission readiness |

## Product Usage Metrics

| Metric | Definition | Target For Hackathon |
| --- | --- | ---: |
| Teachers registered | Accounts created by educators | 30+ stretch / 10+ minimum |
| Active teachers | Teachers who create or process an assessment | 5+ |
| Assessments created | Assessment records created | 10+ |
| Assessments processed | Assessments with submissions analyzed | 5+ |
| Submissions received | Student submissions stored | 100+ |
| Submissions analyzed | Submissions processed by Grading Agent | 100+ |
| Feedback drafts generated | Feedback outputs created | 300+ stretch / 100+ minimum |
| Reports generated | Teacher reports produced | 5+ |

## Workflow Completion Metrics

| Metric | Definition | Why It Matters |
| --- | --- | --- |
| Assessment creation completion rate | Created assessments that reach rubric generation | Shows intake clarity |
| Rubric approval rate | Rubrics approved by teachers | Shows trust and usability |
| Submission processing completion rate | Submissions that reach analysis result | Shows operational reliability |
| Teacher review completion rate | Suggestions reviewed by teacher | Shows human-in-the-loop works |
| Report generation rate | Assessments that produce final report | Shows full workflow completion |
| Time to first assessment | Time from account creation to first assessment draft | Activation metric |
| Time to first approved feedback | Time from assessment creation to first approved feedback | Value realization metric |

## Teacher Trust Metrics

| Metric | Definition | Interpretation |
| --- | --- | --- |
| AI grading approval rate | Suggestions accepted without score edits | High may indicate trust, but must be checked for blind approval |
| AI grading edit rate | Suggestions edited by teacher | Healthy signal if edits improve quality |
| AI grading rejection rate | Suggestions rejected | High means quality/rubric mismatch |
| Feedback approval rate | Feedback drafts approved | Indicates usefulness |
| Feedback edit rate | Drafts edited before approval | Helps improve prompts/product |
| Uncertainty flag rate | Outputs flagged as uncertain | Shows responsible operation |
| Teacher override count | Number of edits/rejections | Evidence of human authority |

Do not optimize for 100% blind approval. The product should encourage meaningful teacher review.

## AI-Native Operations Metrics

| Metric | Definition | Target |
| --- | --- | ---: |
| Agent runs logged | Every agent execution event | 500+ |
| Agent run success rate | Successful runs / total runs | 90%+ for demo |
| Retry rate | Retried runs / total runs | Track and reduce |
| Failed run rate | Failed runs / total runs | Low and visible |
| Model usage by agent | Which model each agent used | Required for cost/evidence |
| Token usage by agent | Input/output tokens or estimates | Required for unit economics |
| Cost per agent run | Estimated cost per run | Required |
| Cost per assessment | AI/cloud cost per assessment | Required |
| Cost per graded submission | Cost per submission analyzed | Required |
| Premium fallback rate | Premium model runs / total runs | Keep low and explicit |

## Student Value Metrics

| Metric | Definition |
| --- | --- |
| Feedback outputs approved | Teacher-approved feedback items |
| Average feedback turnaround time | Time from submission to approved feedback |
| Learning gaps detected | Unique gap groups identified |
| Recovery activities generated | Activities suggested for gaps |
| Recovery activities approved | Teacher-approved recovery actions |
| Students affected by gap | Count of submissions tied to each gap |

For MVP, student accounts are not required. Student value can be measured from teacher-approved outputs.

## Business Metrics

| Metric | Definition | Target |
| --- | --- | ---: |
| Discovery interviews | Completed educator interviews | 10+ |
| Demo calls | Product demos with target users | 5+ |
| Pilot candidates | Strong candidates with upcoming assessment | 5+ |
| Paid pilots | Paid Pilot Packs | 1-3 minimum / 3+ target |
| Payment commitments | Signed or explicit commitments | 3+ |
| Arms-length revenue | Revenue from unrelated customers | Track separately |
| Related-party revenue | Revenue from known/related contacts | Track separately |
| Revenue by month | Revenue grouped by month | Required |
| Marketing spend | Paid acquisition costs | Report even if zero |
| Customer acquisition cost | Spend / customers | Can be zero for founder-led |
| Testimonials collected | Approved quotes or feedback | 1+ |

## Unit Economics Metrics

| Metric | Definition |
| --- | --- |
| AI runtime cost | Gemini/Vertex model usage cost |
| Cloud runtime cost | Cloud Run/DB/storage/logging estimate |
| Payment fees | Stripe/processor fees |
| Support time | Manual onboarding/review time |
| Cost per customer | Product cost attributed to customer |
| Revenue per customer | Revenue by account |
| Gross margin per offer | Revenue minus attributable cost |
| Free-tier/credits used | Cost covered by credits |
| Cash cost paid | Actual cash spend |
| Allocated tooling cost | Development tooling if reported separately |

## Hackathon Evidence Metrics

| Evidence Metric | Required Artifact |
| --- | --- |
| Users | Customer/pilot list |
| Revenue | Payment evidence or commitments |
| Revenue by month | Revenue ledger |
| Related-party revenue | Related-party flag |
| Costs | Cost ledger/billing evidence |
| Marketing spend | Marketing ledger or US$0 declaration |
| Agent logs | Product dashboard/export |
| API usage | Google/Gemini dashboard screenshots/export |
| Product demo | 3-minute video |
| Customer proof | Testimonials/interview notes |
| Impact | Time saved, feedback speed, gaps detected |

## Activation Funnel

```mermaid
flowchart TD
  A[Visitor / outreach target]
  B[Discovery conversation]
  C[Demo]
  D[Pilot candidate]
  E[Paid pilot or commitment]
  F[Assessment created]
  G[Rubric approved]
  H[Submissions processed]
  I[Feedback approved]
  J[Report generated]
  K[Testimonial / repeat use]

  A --> B --> C --> D --> E --> F --> G --> H --> I --> J --> K
```

## Product Funnel Metrics

| Stage | Metric |
| --- | --- |
| Assessment started | Assessment draft created |
| Assessment ready | Rubric approved |
| Assessment active | First submission received |
| AI operation | First grading suggestion generated |
| Human control | First teacher approval/edit/rejection |
| Student value | First feedback approved |
| Reporting | Teacher report generated |
| Business evidence | Time saved/cost/revenue linked |

## Quality Thresholds

| Area | Minimum Threshold |
| --- | --- |
| Agent log coverage | 100% of agent runs logged |
| Teacher approval coverage | 100% of student-facing outputs approved or marked pending |
| Cost tracking coverage | 90%+ of agent runs have model/cost estimate |
| Submission processing | 90%+ of valid submissions processed successfully |
| Report generation | 80%+ of processed assessments generate report |
| Evidence completeness | 100% of paid pilots have revenue/customer evidence record |

## Time-Saved Estimation

Time saved should be estimated transparently.

Suggested simple formula:

```text
Estimated time saved =
teacher baseline estimate
- actual teacher review/edit time
- onboarding/setup time if included
```

If baseline is unknown, collect teacher estimate:

- time usually spent creating assessment;
- time usually spent grading;
- time usually spent writing feedback;
- time usually spent preparing report.

Label all values as estimates unless directly measured.

## Event Instrumentation

Minimum events:

| Event | Trigger |
| --- | --- |
| `teacher_signed_in` | Teacher logs in |
| `assessment_created` | Assessment brief saved |
| `agent_run_started` | Agent begins |
| `agent_run_completed` | Agent succeeds |
| `agent_run_failed` | Agent fails |
| `rubric_generated` | Rubric draft created |
| `rubric_approved` | Teacher approves rubric |
| `submission_received` | Submission stored |
| `submission_analyzed` | Grading suggestion created |
| `grading_suggestion_approved` | Teacher approves score |
| `grading_suggestion_edited` | Teacher edits score |
| `grading_suggestion_rejected` | Teacher rejects score |
| `feedback_generated` | Feedback draft created |
| `feedback_approved` | Teacher approves feedback |
| `learning_gap_generated` | Gap summary created |
| `recovery_activity_generated` | Recovery suggestion created |
| `teacher_report_generated` | Report created |
| `evidence_dashboard_viewed` | Operator/teacher views evidence |
| `payment_recorded` | Revenue event added |
| `testimonial_recorded` | Customer quote/evidence added |

## Dashboard Views

### Teacher Dashboard

- assessments;
- pending approvals;
- submissions processed;
- feedback ready;
- report ready;
- common gaps.

### Operator/Hackathon Dashboard

- users;
- customers/pilots;
- assessments processed;
- submissions processed;
- agent runs;
- model usage;
- estimated costs;
- revenue evidence;
- related-party revenue;
- testimonials;
- time saved.

## Metrics Anti-Patterns

Avoid:

- vanity user counts without real assessment runs;
- counting AI drafts as student value before teacher approval;
- hiding failed agent runs;
- mixing related-party and arms-length revenue;
- reporting credits as if costs do not exist;
- claiming time saved without baseline;
- optimizing for AI approval rate without quality review.

## Metrics Conclusion

GradeOps AI should measure what it claims to be:

> a real AI-operated assessment workflow for programming educators with teacher control, evidence, cost awareness, and business validation.


---

## Source: `02-product/mvp-scope.md`

# MVP Scope

GradeOps AI MVP is a focused product workflow for programming educators.

It must prove one thing clearly:

> A teacher can run assessments — practical programming exercises and objective knowledge checks — with AI agents, keep final control, generate useful feedback/reporting, and produce auditable evidence of usage, cost, and AI-native operations.

The MVP is not a full LMS, not a generic quiz generator, not a student chatbot, and not an OCR-first grading platform.

The MVP supports two assessment modes:

- **Open assessments** — practical programming tasks; rubric-based grading; AI generates, teacher approves.
- **Closed assessments** — objective questions with alternatives (TF, single choice, multiple choice); AI-native question bank; deterministic grading against a frozen answer key.

## Alignment With Canonical Strategy

| Canonical Decision | Product Scope Implication |
| --- | --- |
| Initial wedge: programming assessments | Open assessments remain the primary wedge; closed assessments expand scope within the same target user |
| Core promise: run the next assessment with AI agents | Prioritize end-to-end assessment workflow over feature breadth; both modes must have a viable demo path |
| Teacher authority | Every high-impact output requires teacher review/approval in both modes |
| AI-native operations | Agent executions must be visible, logged, and structured; closed mode adds question generation and curation agents |
| Pricing by assessments/submissions | Product must track assessment count and graded-submission count across both modes |
| Hackathon evidence | Usage, cost, revenue, customer, and agent evidence must be captured from day one |
| Closed assessment mode | Add question bank, deterministic grading engine, and student access via secure link |

## Teacher-Led, Student-Centered MVP

The MVP user interface is teacher-led, but the product is not limited to assessment generation.

### Open Assessment Flow

```text
Teacher creates assessment
  -> teacher approves rubric
  -> students receive access link or teacher loads submissions
  -> agents analyze each student submission
  -> agents draft grading suggestions and feedback
  -> teacher approves or edits outputs
  -> report summarizes the assessment run
```

### Closed Assessment Flow

```text
Teacher defines evaluative intent
  -> AI generates question batch
  -> teacher reviews and approves questions into bank
  -> teacher or AI composes assessment from bank
  -> teacher approves composition and answer key
  -> system publishes assessment and sends student access links
  -> students respond via secure link
  -> deterministic engine grades responses
  -> teacher reviews exceptions and analytics
  -> results published to students
```

Students are represented as `LearnerRef` records with an email. Access to the assessment and results is delivered via secure, signed links — no student account required.

The commercial usage limit in plans refers to **graded student submissions**, not registered students.

## MVP Product Objective

Enable a programming educator to:

1. create an open or closed assessment from a learning goal;
2. generate a rubric (open) or question bank (closed) with AI assistance;
3. invite students via secure links or load submissions directly;
4. grade: AI suggestions against rubric (open) or deterministic scoring against answer key (closed);
5. draft personalized feedback (open) or generate item analytics (closed);
6. detect cohort-level learning gaps;
7. approve or edit AI outputs;
8. generate a teacher report;
9. publish results accessible to students via link;
10. see the agent logs, model usage, cost estimates, and evidence dashboard.

## Target User For MVP

Primary MVP user:

> A programming instructor, tutor, or bootcamp teacher who runs recurring practical assessments and wants to reduce grading/feedback workload without losing pedagogical control.

Secondary user:

> A small academy or bootcamp operator who needs visibility into cohort outcomes and assessment consistency.

## MVP Experience

The first usable product should feel like an assessment operations console, not a general admin system.

A teacher should be able to complete this loop:

```text
Learning goal
  -> assessment draft
  -> rubric draft
  -> teacher approval
  -> submissions
  -> grading suggestions
  -> feedback drafts
  -> learning gaps
  -> teacher approval
  -> report
  -> evidence dashboard
```

## MVP Scope Matrix

| Area | Must Build | Should Build | Could Build Later | Do Not Build Now |
| --- | --- | --- | --- | --- |
| Authentication | Simple teacher login | Account profile | Organization admin | Complex SSO |
| Open assessment creation | Learning-goal intake and constraints | Templates for intro programming | Rich curriculum mapping | Full LMS authoring |
| Rubrics | AI-generated rubric draft | Rubric validation notes | Rubric library | Institutional rubric governance |
| Closed assessment mode | Question generation, bank curation, answer key, deterministic grading | AI-assembled question composition | Bank sharing across teachers | Marketplace of question banks |
| Question bank | AI generation + teacher curation queue, approve/reject | Versioning UI, clone, retire | Full analytics history per item | Institutional shared banks |
| Subject and curriculum structure | String-based subject/topic/learning-outcome tagging on questions and assessments | Structured Subject + CurriculumNode + LearningObjective entities; AI-generated curriculum | National curriculum packs (e.g., Chile) | Multi-country curriculum marketplace |
| Student submissions (open) | Text/code paste and simple file upload | CSV/bulk import | GitHub Classroom integration | OCR/photo-first intake |
| Student response (closed) | Secure link delivery, web response portal | CSV response import | Paper/OMR ingestion | Complex proctoring |
| Student access | LearnerRef + signed links, no account required | Result portal via link | Magic link resend | Full student account and portal |
| Grading assistance (open) | Rubric-based score suggestion | Uncertainty flags | Code execution sandbox | Fully autonomous grading |
| Grading (closed) | Deterministic engine against answer key | Exception review queue | Partial credit configuration | AI-based objective grading |
| Feedback | Individual feedback draft | Tone/style controls | Feedback templates | Student chatbot |
| Learning gaps | Cohort summary | Gap-to-recovery mapping | Longitudinal analytics | Predictive student profiling |
| Recovery | Suggested remedial activity | Short exercise draft | Personalized recovery plan | Full adaptive learning system |
| Item analytics | Post-assessment difficulty and correct-rate per item | Reinforcement suggestions from analytics | Longitudinal item performance | BI suite for items |
| Teacher review | Approve/edit/reject states | Bulk approve with warnings | Review delegation | Silent AI delivery |
| Reports | Teacher report (both modes) | Export PDF/CSV | Cohort comparison | BI suite |
| Evidence | Agent logs, usage, cost estimate | Business dashboard | Public evidence export | Hidden logs |
| Payments | Manual/Stripe evidence outside product acceptable | Basic plan flag | Self-serve billing | Complex metering marketplace |

## In Scope

### 1. Teacher Workspace

The teacher can see:

- assessments;
- current status;
- submission count;
- pending approvals;
- report availability;
- evidence dashboard link.

### 2. Assessment Intake

Teacher inputs:

- learning goal;
- programming topic;
- target level;
- language or pseudocode;
- expected duration;
- number of students;
- constraints;
- optional existing instructions.

Example:

> Evaluate conditionals, loops, and functions in Java for first-semester students. Duration: 90 minutes. Difficulty: basic.

### 3. Assessment Draft Generation

Assessment Agent produces:

- title;
- context;
- instructions;
- learning objectives;
- expected deliverables;
- allowed resources;
- evaluation criteria summary;
- student-facing statement.

### 4. Rubric Generation And Validation

Rubric Agent produces:

- criteria;
- weights;
- performance levels;
- scoring notes;
- common mistakes;
- validation warnings;
- ambiguity flags.

### 5. Teacher Approval For Assessment And Rubric

Teacher can:

- approve;
- edit;
- reject/regenerate;
- add notes;
- lock rubric for grading.

No grading should start until the rubric is approved or explicitly marked as draft/demo.

### 6. Student Submission Intake

#### Open Assessments

Supported input types:

- pasted student code/text;
- uploaded `.txt`, `.java`, `.py`, `.js`, `.ts`, `.html`, `.css`, `.md`;
- manual `student_identifier` (teacher-controlled, no login);
- optional `student_display_name` if the teacher needs it;
- bulk paste/import if simple.

Each loaded answer becomes a `StudentSubmission`. A graded submission is consumed when that `StudentSubmission` is analyzed for grading/feedback.

#### Closed Assessments

Students respond through a secure access link sent to their email. The teacher creates a `LearnerRef` per student (email required; display name and external identifier optional). No student account is required.

Each `AssessmentAttempt` records the student's response. The graded submission usage counter increments when the attempt is analyzed.

#### Student Identity Model

The MVP uses a minimal identity approach:

- Open assessments: `StudentSubmission` with `student_identifier` (teacher-loaded).
- Closed assessments: `LearnerRef` + `AssessmentInvitation` + `AssessmentAttempt` (link-based).
- No student login or account in either mode.

### 7. Grading Assistance

Grading Agent produces:

- suggested score;
- score per rubric criterion;
- evidence found in submission;
- missing requirements;
- uncertainty flags;
- teacher review recommendation.

The product must communicate clearly:

> Suggested score is not final until teacher approval.

### 8. Feedback Drafts

Feedback Agent produces:

- concise feedback;
- strengths;
- improvement areas;
- next step;
- rubric criterion references;
- tone suitable for students.

### 9. Learning Gap Summary

Learning Gap Agent produces:

- repeated errors;
- affected students count;
- affected rubric criteria;
- severity;
- suggested class-level reinforcement.

### 10. Recovery Activity

Recovery Agent produces:

- short remedial exercise;
- focus topic;
- instructions;
- expected output;
- optional hints;
- relationship to detected gaps.

### 11. Teacher Report

Teacher Report Agent produces:

- assessment summary;
- distribution of suggested/approved results;
- common errors;
- learning gaps;
- suggested next class action;
- time-saved estimate;
- evidence summary.

### 12. Agent Log And Evidence Capture

Each agent execution must record:

- timestamp;
- teacher/account;
- assessment;
- submission if applicable;
- agent name;
- action type;
- model used;
- input summary;
- output summary;
- status;
- token estimate;
- cost estimate;
- uncertainty flags;
- approval state;
- final action taken.

## Out Of Scope

Do not build in the MVP:

- full LMS;
- student social features, student account with password;
- chat tutor;
- institution-wide administration;
- complex roles/permissions;
- SSO;
- mobile app;
- OCR/OMR for physical paper (P1 for closed assessments, not P0);
- plagiarism detection as a core claim;
- code execution sandbox unless trivial and safe;
- advanced curriculum mapping;
- marketplace of assessments or shared question banks;
- broad multi-subject support;
- fully autonomous grading (open assessments);
- AI-based scoring for closed assessments (must be deterministic).

## MVP User Roles

| Role | MVP Permissions |
| --- | --- |
| Teacher | Create assessment (open/closed), approve rubric/question bank, manage learner list, upload submissions, review grading/exceptions, approve feedback, view report/logs |
| Operator/Admin | View evidence dashboard, cost/revenue summary, customer/pilot status |
| Student (LearnerRef) | Access assessment via secure link, submit response, view published result via link; no login or account |

## Required Product States

### Assessment States

| State | Meaning |
| --- | --- |
| `draft` | Created but not yet approved |
| `rubric_pending_review` | Rubric generated and waiting for teacher |
| `ready_for_submissions` | Teacher approved assessment/rubric |
| `submissions_received` | At least one submission is present |
| `grading_in_progress` | Agent grading is running |
| `pending_teacher_review` | Suggestions are ready for review |
| `approved` | Teacher approved student-facing outputs |
| `reported` | Teacher report was generated |
| `archived` | Workflow closed |

### Submission States

| State | Meaning |
| --- | --- |
| `received` | Submission stored |
| `analysis_pending` | Waiting for agent processing |
| `analyzed` | Grading suggestion exists |
| `needs_review` | Teacher must inspect |
| `approved` | Teacher approved result/feedback |
| `edited_by_teacher` | Teacher changed AI output |
| `rejected` | Teacher rejected AI output |
| `excluded` | Submission removed from final report |

### Agent Run States

| State | Meaning |
| --- | --- |
| `queued` | Waiting to run |
| `running` | Agent processing |
| `succeeded` | Output generated |
| `failed` | Agent failed |
| `retried` | Re-run after failure |
| `requires_human_review` | Output has risk/uncertainty |
| `approved` | Output accepted |
| `edited` | Output changed |
| `rejected` | Output rejected |

## Non-Functional MVP Requirements

| Requirement | MVP Expectation |
| --- | --- |
| Traceability | Every agent output must map to an assessment/submission and model used |
| Cost visibility | Every agent run should have an estimated cost |
| Human control | High-impact outputs require teacher approval |
| Reliability | Failure states must not lose submissions or teacher edits |
| Privacy | Store minimal student data and avoid unnecessary sensitive information |
| Demo readiness | Core flow must be demonstrable in under 3 minutes |
| Exportability | Reports/evidence should be exportable or screenshot-ready |
| English readiness | Public/demo content should be available in English for submission |

## MVP Acceptance Criteria

The MVP is acceptable when:

1. a teacher can create one programming assessment from a learning goal;
2. AI generates an assessment and rubric as structured data;
3. the teacher can approve or edit the rubric;
4. at least 30 student submissions can be ingested in a controlled demo/pilot;
5. grading suggestions are generated against the rubric;
6. feedback drafts are produced per submission;
7. learning gaps and recovery suggestions are produced;
8. the teacher can approve/edit/reject outputs;
9. a report is generated;
10. agent logs and cost estimates are visible;
11. the workflow can be shown in a 3-minute demo;
12. the same flow can support at least one real or semi-real pilot.

## MVP Cut Line

When time is short, protect these features first:

1. assessment creation;
2. rubric generation;
3. submission intake;
4. grading suggestions;
5. teacher approval;
6. feedback drafts;
7. report;
8. agent logs/evidence.

Everything else is secondary.

## Product Conclusion

The MVP should be narrow enough to build quickly and strong enough to prove the business.

The winning product story is not:

> We built many education features.

It is:

> We ran real programming assessments with AI agents, teachers stayed in control, students got feedback faster, and the business captured usage, cost, revenue, and operational evidence.


---

## Source: `02-product/personas.md`

# Personas

GradeOps AI personas describe product users, buyers, evaluators, and anti-personas for the MVP.

The product is focused on programming assessment operations, so every persona must connect to a real assessment workflow.

## Persona Summary

| Persona | Role In Product | Role In Business | Priority |
| --- | --- | --- | --- |
| Lead Programming Instructor | Main daily user | Buyer or strong influencer | P0 |
| Independent Tutor | Daily user and buyer | Direct buyer | P0 |
| Bootcamp Instructor | Daily user | Influencer or buyer | P0 |
| Academy Operator | Dashboard/report consumer | Buyer | P1 |
| Program Manager | Evidence/report consumer | Buyer or approver | P1 |
| Student | Responds via secure link; receives results | Impact beneficiary | P1 |
| Reviewer/Assistant | Supports teacher review | Internal/secondary user | P2 |
| Institution Admin | Procurement/security | Later buyer | Out of MVP |

## P0 Persona: Lead Programming Instructor

### Profile

A teacher who runs recurring programming assessments for a class, cohort, or section.

They may teach:

- introductory programming;
- algorithms;
- Java;
- Python;
- JavaScript;
- web development;
- mobile development;
- backend basics;
- software engineering foundations.

### Goals

- Create assessments faster.
- Grade practical submissions consistently.
- Give students useful feedback.
- Detect repeated mistakes before the next class.
- Keep pedagogical control.
- Avoid being buried in repetitive correction work.

### Pain Points

- Rewrites similar assessments every term.
- Grading takes too long.
- Feedback quality decreases when workload is high.
- Rubrics are hard to apply consistently.
- Reports require manual consolidation.
- Students repeat mistakes because gaps are detected late.

### Trust Requirements

- Must approve rubrics before grading.
- Must approve final scores/feedback.
- Needs to see why AI suggested a score.
- Needs uncertainty flags.
- Needs edit/reject options.
- Needs audit trail for sensitive decisions.

### Success Moment

> I reviewed a full batch of programming submissions faster than usual, edited the AI where needed, and got a useful summary for my next class.

### Product Messaging

> Run your next programming assessment with AI agents while keeping final control.

## P0 Persona: Independent Tutor

### Profile

A tutor who teaches programming to individuals or small groups and wants to look professional while scaling their feedback.

### Goals

- Give high-quality individual feedback.
- Save preparation and correction time.
- Show students clear progress.
- Package tutoring as a more professional service.
- Reuse assessment workflows across students.

### Pain Points

- Custom feedback takes time.
- Student progress tracking is informal.
- Rubrics are often implicit.
- Hard to justify premium tutoring prices without evidence.
- Admin work steals time from teaching.

### Trust Requirements

- Wants editable feedback tone.
- Wants simple workflow and low setup.
- Does not want institutional complexity.
- Needs affordable pricing.
- Needs to avoid exposing private student data.

### Success Moment

> I gave each student clear feedback and a recovery exercise without spending my whole evening writing it manually.

### Product Messaging

> Give better feedback to every programming student without turning tutoring into admin work.

## P0 Persona: Bootcamp Instructor

### Profile

An instructor responsible for a cohort of students moving quickly through modules and practical assignments.

### Goals

- Process many submissions quickly.
- Identify students at risk.
- Keep feedback turnaround fast.
- Maintain grading consistency.
- Prepare cohort-level insights for the next session.

### Pain Points

- High volume of assignments.
- Fast teaching cycle leaves little correction time.
- Feedback delays reduce student momentum.
- Hard to identify common misconceptions early.
- Multiple reviewers may apply criteria inconsistently.

### Trust Requirements

- Needs rubric-based grading.
- Needs batch processing.
- Needs learning-gap summary.
- Needs evidence for instructor/manager discussion.
- Needs clear teacher approval workflow.

### Success Moment

> I saw the cohort’s common mistakes before the next module and had feedback drafts ready for review.

### Product Messaging

> Keep feedback cycles fast in high-volume programming cohorts.

## P1 Persona: Academy Operator

### Profile

A founder, coordinator, or operations lead running a small academy, training program, or bootcamp.

### Goals

- Improve throughput without hiring more academic operations staff.
- Standardize assessment quality.
- Produce reports for students, clients, or internal decisions.
- Increase perceived quality of the academy.
- Reduce bottlenecks around instructor workload.

### Pain Points

- Instructor capacity limits growth.
- Grading quality varies by instructor.
- Reporting is manual.
- Student risk appears too late.
- Scaling feedback requires more staff.

### Trust Requirements

- Needs evidence dashboards.
- Needs cost visibility.
- Needs privacy and data boundaries.
- Needs confidence that teachers retain final authority.
- Needs repeatable workflow, not one-off AI prompts.

### Success Moment

> My instructors can process assessments more consistently and I can see cohort outcomes without adding another coordinator.

### Product Messaging

> Give your small academy the assessment operations capacity of a larger academic team.

## P1 Persona: Program Manager

### Profile

A manager responsible for learning quality, cohort outcomes, or technical training delivery.

### Goals

- See learning gaps across cohorts.
- Ensure assessment consistency.
- Support instructors with operational tools.
- Demonstrate learner progress.
- Make decisions from evidence.

### Pain Points

- Outcomes are hard to compare.
- Assessment evidence is scattered.
- Feedback quality varies.
- Reporting arrives late.
- Instructor workload affects delivery quality.

### Trust Requirements

- Needs reports and exports.
- Needs consistent rubric structure.
- Needs evidence of teacher review.
- Needs data that can be summarized safely.
- Needs visibility into usage and outcomes.

### Success Moment

> I can see which skills are weak across the cohort and what instructors are doing next.

### Product Messaging

> Turn assessment activity into evidence for better program decisions.

## P1 Persona: Student

### Profile

A learner who responds to an assessment and receives results through a secure link. Students access GradeOps AI without creating an account.

For open assessments, the teacher may load submissions on the student's behalf. For closed assessments, the student receives a link and responds directly.

Students are not the primary MVP user, but a real assessment operation requires real student participation.

### Goals

- Receive and submit the assessment without friction.
- Receive feedback quickly.
- Understand what they did wrong.
- Know what to practice next.
- Trust that evaluation is fair.
- See clear criteria.

### Pain Points

- Feedback arrives too late.
- Feedback is too generic.
- Mistakes are not connected to criteria.
- Students do not know what to fix next.
- Access is complicated or requires creating yet another account.

### Trust Requirements

- Should know teacher has final authority.
- Should receive understandable feedback.
- Should not receive raw AI uncertainty or internal logs.
- Should not have personal data exposed unnecessarily.
- Access link should work on any device without installation.

### Access Model

- Students receive a unique link in their email.
- No password, no registration.
- One link per assessment.
- Result link sent after teacher publishes results.

### Success Moment

> I received the assessment, submitted my answers, and later saw my result with clear feedback — all without creating an account.

### Product Messaging

Student-facing messaging is secondary for MVP. If needed:

> Receive and submit your assessment, and see your results — no account required.

## P2 Persona: Reviewer Or Assistant

### Profile

A teaching assistant, reviewer, or collaborator who helps review submissions.

### Goals

- Apply rubric consistently.
- Reduce repetitive review effort.
- Escalate uncertain submissions.
- Coordinate with lead instructor.

### Pain Points

- Manual review is repetitive.
- Rubric interpretation varies.
- Lead instructor still needs final confidence.
- Multiple reviewers create inconsistency.

### Trust Requirements

- Needs role boundaries.
- Needs comments/notes.
- Needs escalation to teacher.
- Needs audit trail.

### MVP Note

This persona is not required for MVP unless a pilot explicitly involves multiple reviewers. Do not build complex role management yet.

## Anti-Personas

### Enterprise Institution Buyer

Large institutions have procurement, compliance, SSO, legal, and integration needs. They may be valuable later, but they are too slow for the hackathon MVP.

### Teacher Looking For A Full LMS

GradeOps AI is not designed to manage all course content, attendance, forums, calendars, and institutional records.

### Student Seeking AI Tutoring

The MVP is not a student chatbot or tutor. Student support appears through teacher-approved feedback and recovery activities.

### Fully Autonomous Grading Buyer

A buyer who wants AI to grade and deliver final results without human oversight is not aligned with the trust model.

### Broad Non-Programming Educator

Other subjects may be future expansion, but they dilute MVP clarity.

## Persona Priority For Build Decisions

When a product decision is unclear, optimize in this order:

1. Lead Programming Instructor;
2. Independent Tutor / Bootcamp Instructor;
3. Academy Operator;
4. Program Manager;
5. Student (submission and result access via link);
6. Reviewer/assistant;
7. future institution admin.

## Persona-Based Acceptance Tests

| Persona | Product Must Enable |
| --- | --- |
| Lead Instructor | Create assessment, approve rubric, review grading suggestions, approve feedback, see report |
| Independent Tutor | Run small assessment quickly and produce polished feedback |
| Bootcamp Instructor | Process batch submissions and detect cohort gaps |
| Academy Operator | See evidence of usage, time saved, and outcome reporting |
| Program Manager | Understand learning gaps and assessment consistency |
| Student | Receive and submit assessment via link without account; receive result and feedback via link |
| Reviewer | Support review without replacing teacher authority |

## Persona Conclusion

GradeOps AI should not try to satisfy every education stakeholder in the MVP.

The first product must delight the educator who feels the pain directly:

> The person who has to turn 30 programming submissions into fair scores, useful feedback, and a clear next teaching action.


---

## Source: `02-product/response-intake.md`

# Response Intake

GradeOps AI accepts student responses through two channels. Both channels produce a normalized `AssessmentAttempt`, which feeds the same grading and results pipeline.

## Intake Principle

```text
Every response, regardless of intake channel, must produce a normalized AssessmentAttempt.
```

The intake channel determines how the response enters the system. Once the response is normalized, grading, exception review, and result publication are identical regardless of channel.

## Channels

| Channel | Assessment type | Priority | Mechanism |
| --- | --- | --- | --- |
| Digital — secure link | Open + Closed | P0 | Student responds via web portal using a signed access token |
| Physical — scanned answer sheet | Closed only | P1 | Teacher scans or photographs paper answer sheets; system extracts responses via OMR/QR |

Mixed-channel intake (same student responds both digitally and physically) is an exception case covered in the conflict resolution section.

## Digital Intake (P0)

Students receive an email with a unique, signed `assessment_access_link`. They open the link, respond, and submit without creating an account. See [Student Access](#student-access) for the full student experience and token security rules.

### Digital Flow

```mermaid
flowchart TD
  A[Teacher publishes assessment]
  B[System generates unique token per LearnerRef]
  C[System sends email with access link]
  D[Student opens link]
  E[System validates token: not expired, not revoked, assessment accepting responses]
  F[Student sees assessment]
  G[Student submits response]
  H[System records AssessmentAttempt + ClosedResponse or OpenSubmission]
  I[Token marked as used]

  A --> B --> C --> D --> E --> F --> G --> H --> I
```

### Applies To

- Closed assessments: student selects alternatives in web interface.
- Open assessments: student submits text, code, or file attachment.

## Physical Intake (P1)

Physical intake is designed for closed assessments applied with printed answer sheets. It is the recommended intake path when students do not have access to devices or when the evaluation context requires paper-based delivery.

### OCR vs OMR

| Technique | Best use in GradeOps AI |
| --- | --- |
| OMR (Optical Mark Recognition) | Detecting selected alternatives in bubble or checkbox format on structured answer sheets |
| OCR (Optical Character Recognition) | Reading identifiers, names, or codes written on the sheet; open-ended text if added as P2 |
| QR / unique code | Linking a physical sheet to a specific `AssessmentInvitation`, evaluation, and student without manual association |
| Computer Vision | Detecting sheet orientation, crop boundaries, shadows, and zone alignment before OMR |

For closed assessments, the primary technique is **OMR + QR**. OCR is used only for reading printed or handwritten identifiers when QR is unavailable.

### Physical Flow

```mermaid
flowchart TD
  A[Teacher generates answer sheets]
  B[Each sheet includes ID/QR linked to AssessmentInvitation]
  C[Teacher prints and distributes]
  D[Students respond on paper]
  E[Teacher collects and scans or photographs sheets]
  F[Teacher opens intake module and uploads image or batch]
  G[System validates image quality: sharpness, orientation, completeness, QR readability]
  H{Quality OK?}
  I[System reads QR to identify assessment, student, version]
  J[System detects marked alternatives via OMR]
  K[System calculates confidence per response]
  L[System presents pre-intake to teacher: responses + confidence + alerts]
  M[Teacher reviews and confirms or corrects]
  N[System creates normalized AssessmentAttempt]

  A --> B --> C --> D --> E --> F --> G --> H
  H -- No --> G
  H -- Yes --> I --> J --> K --> L --> M --> N
```

### Physical Answer Sheet Requirements

Every printed answer sheet must include:

- Unique ID or QR linked to `AssessmentInvitation` (student + assessment + version).
- Student display name or identifier (for visual confirmation).
- Assessment title and version label.
- Alignment marks for orientation detection.
- Clear, separated response zones per question.
- Instructions for marking.
- Space for teacher validation if manual association is needed.

### Capture States

| State | Meaning |
| --- | --- |
| `uploaded` | Image received by system |
| `quality_check` | System evaluating image quality |
| `accepted_for_processing` | Image passes quality check |
| `rejected_quality` | Image rejected; teacher must recapture |
| `processing` | OMR and QR extraction running |
| `extraction_completed` | Responses detected; ready for teacher review |
| `needs_human_review` | Low confidence or ambiguity requires teacher action |
| `confirmed` | Teacher confirmed extracted responses |
| `failed` | Processing failed; logged for retry |

### Response Confidence States

| State | Meaning |
| --- | --- |
| `high_confidence` | Mark is clear and unambiguous |
| `low_confidence` | Detection is uncertain; teacher should review |
| `ambiguous` | Multiple marks detected or mark position is unclear |
| `blank` | No mark detected for this question |
| `manually_corrected` | Teacher overrode the detected value |

## Intake Edge Cases

### Physical Intake Exceptions

| Case | Recommended handling |
| --- | --- |
| QR code unreadable | Teacher selects student and assessment manually; action is audited |
| Sheet has no QR but has printed student identifier | System prompts OCR check; teacher confirms association manually |
| Two alternatives marked in single-choice question | Flag as ambiguous; teacher resolves before grading |
| Weak or erased mark | Show low confidence; teacher confirms |
| Sheet image blurry or incomplete | Reject and request recapture |
| Duplicate sheet for same student | Alert teacher; teacher decides which to use; both preserved in log |
| Sheet belongs to a different assessment or version | Block intake; prevent cross-assessment contamination |

### Digital Intake Exceptions

See [Student Access — MVP Pending Decisions](#student-access) and [Workflows — Workflow 4d](#workflows) for token validation edge cases (expired links, already-submitted attempts, etc.).

## Conflict Resolution: Dual-Channel Attempts

A student should not have two valid normalized attempts for the same assessment unless explicitly allowed by the teacher.

| Scenario | Default behavior |
| --- | --- |
| Student submitted digitally; teacher also uploads paper sheet for same student | Block paper intake; teacher must decide which attempt to keep |
| Paper sheet processed twice for same student | Detect duplicate; alert teacher |
| Digital link used after paper sheet was already confirmed | Block if confirmed paper attempt exists; prompt teacher |
| Teacher allows multiple attempts (configured) | Register attempt N; policy determines which counts for grading |
| Student was absent; no response received | Teacher marks as `excluded`; no `GradeResult` is generated |

## Normalization to AssessmentAttempt

After intake, the system creates a normalized attempt regardless of channel.

```mermaid
flowchart LR
  A[Digital ClosedResponse] --> C[AssessmentAttempt]
  B[Confirmed ExtractedAnswer from PaperCapture] --> C
  C --> D[Deterministic grading engine]
  D --> E[GradeResult]
```

For open assessments:
```mermaid
flowchart LR
  A[Digital OpenSubmission] --> C[AssessmentAttempt]
  C --> D[Grading Agent analysis]
  D --> E["GradeSuggestion → Teacher approval → GradeResult"]
```

## Relationship to Data Model

The intake channel is recorded on `AssessmentAttempt.channel`:

| Value | Meaning |
| --- | --- |
| `online` | Student responded via digital link |
| `paper_scan` | Teacher uploaded scanned/photographed sheet; confirmed by teacher |

Physical intake entities (`PaperAnswerSheet`, `PaperCapture`, `ExtractedAnswer`) are defined as P1 entities in the [data model](../04-architecture/data-model.md).

## Scope

### P0

- Digital link delivery and web response portal for closed assessments.
- Digital file or text submission for open assessments.
- Normalized `AssessmentAttempt` creation for all digital responses.
- Duplicate detection and conflict resolution for digital channel.

### P1

- Printable answer sheet generation with QR per student.
- Image upload and quality validation.
- OMR-based alternative detection.
- Confidence scoring and teacher review queue for physical captures.
- Conflict resolution for dual-channel attempts.
- Batch upload of multiple physical sheets.

### P2

- OCR for open answer text on paper.
- Automatic perspective and rotation correction.
- Mobile app for in-classroom capture.
- Offline recognition.
- Mixed open + closed answer sheets.


---

## Source: `02-product/student-access.md`

# Student Access

GradeOps AI gives students a minimal, secure access surface for responding to assessments and reviewing published results. Students do not need a registered account.

Access is granted through **unique, signed tokens delivered to the student's email by the teacher**.

## Core Principle

```text
Students access their evaluation using a secure link sent to their email.
They can respond to an assessment and see published results.
They cannot list other students' assessments, see internal logs, or access any other account data.
```

This avoids building a student LMS portal while still enabling the operation to include real student responses and result delivery.

## Actor Definition

The student in GradeOps AI is a `LearnerRef`: a lightweight reference record created by the teacher for one course section or assessment run.

| Field | Type | Notes |
| --- | --- | --- |
| `id` | UUID | Primary key |
| `organization_id` | UUID | Tenant boundary |
| `email` | string | Used for link delivery |
| `display_name` | string | Optional; teacher-provided |
| `external_identifier` | string | Optional roster code, LMS ID, or alias |

A `LearnerRef` is not a login account. It exists only to enable link delivery and result association.

## Link Types

| Link | Purpose | Expiry |
| --- | --- | --- |
| `assessment_access_link` | Lets the student respond to or submit an open assessment | Configurable; default: after submission |
| `result_access_link` | Lets the student view published results and feedback | Configurable; default: until archived |
| `magic_reauth_link` | Regenerates access when original link expired or lost | One-time use |

Links are sent by the teacher or system when the assessment is published. The teacher can revoke any link.

## Student Lifecycle

```mermaid
stateDiagram-v2
  [*] --> invited
  invited --> link_sent
  link_sent --> access_validated : Token valid
  access_validated --> started : Student opens assessment
  started --> submitted : Student confirms submission
  submitted --> graded : System processes
  graded --> result_available : Teacher publishes result
  result_available --> viewed_result
```

## Invitation Flow

```mermaid
flowchart TD
  A[Teacher publishes assessment]
  B[Teacher creates or imports learner list]
  C[System generates unique token per learner per assessment]
  D[System sends email with access link]
  E[Student opens link]
  F[System validates token: not expired, not revoked, correct status]
  G[Student accesses their assessment or result]

  A --> B --> C --> D --> E --> F --> G
```

## What Students Can See

| Information | Open Assessment | Closed Assessment |
| --- | --- | --- |
| Assessment instructions and context | Yes | Yes |
| Their submitted answer | Yes | Yes |
| Their final grade | Yes, after publication | Yes, after publication |
| Their total score | Yes | Yes |
| Teacher-approved feedback | Yes | Configurable |
| Rubric or criteria | Configurable by teacher | Not applicable / summary only |
| Correct answers | No, unless teacher enables it | Configurable by teacher |
| Questions they answered incorrectly | Not applicable | Configurable |
| Recovery suggestions | Yes, if teacher publishes | Yes, if teacher publishes |
| Internal agent logs | No | No |
| AI confidence scores or model info | No | No |
| Cost estimates or internal metadata | No | No |
| Other students' data | Never | Never |

## Result Portal

The student result portal is a stateless, link-authenticated view. It is not a dashboard or an account.

Access flow:

```text
Student opens result_access_link from email
  -> System validates token
  -> Student sees: assessment name, their grade, feedback if published
  -> Student can download or copy feedback if teacher enabled it
  -> Student cannot navigate to other assessments without a new link
```

If the student does not have the result link, they can request a resend:

```text
Student enters email in "resend my link" form
  -> System sends new magic link if a result is published and learner exists
  -> System does not confirm or deny whether the email exists (rate-limited)
```

## Security Rules

| Rule | Rationale |
| --- | --- |
| Token stored as hash, never as plain text | Prevents link theft from database breach |
| Token is high-entropy random value | Resistant to brute force |
| Token is scoped to one `learner_ref_id` + one `assessment_id` | No cross-student access possible |
| Expiry is configurable | Teacher controls access window |
| Revocation is immediate | Teacher can close access anytime |
| System validates assessment status before token use | Cannot access a result not yet published |
| Rate limiting on all student-facing endpoints | Prevents enumeration and abuse |
| Student email not confirmed or denied in public API | No exposure of roster |
| Access events logged | Full audit trail per student per assessment |
| No shared links | Each student gets their own token |

## MVP Pending Decisions

| Decision | Recommendation |
| --- | --- |
| Can the student reopen the assessment before submitting? | Yes; allow reopen until first submission |
| Can the student save progress before submitting? | P1; in MVP, single submission with pre-submit review |
| Can the student see correct answers for closed assessments? | Configurable by teacher |
| Can the student appeal or request review? | P2; MVP shows result only |
| Can the student submit late? | Flag as late; teacher decides |
| Can the student have multiple attempts? | Configurable; P0 default is one attempt |
| Is the grade scale shown to the student? | Yes, after teacher publishes result |

## Student Privacy Rules

- Store minimal student data: email, display name, external identifier.
- Do not expose full names in URLs or public surfaces.
- Do not include student submission content in public screenshots.
- Token hashes must not appear in logs; log only `learner_ref_id` and event type.
- Delete or anonymize student data at the end of a pilot if requested.
- Do not cross-share student data across organizations.


---

## Source: `02-product/user-stories.md`

# User Stories

This document defines product user stories for the GradeOps AI MVP.

The stories are organized by epic and priority.

Priority definitions:

| Priority | Meaning |
| --- | --- |
| P0 | Required for MVP and hackathon demo |
| P1 | Important for pilot quality |
| P2 | Useful later, not required for first MVP |
| Out | Explicitly outside MVP |

## Epic 1: Teacher Onboarding And Workspace

### US-001: Teacher Login

**Priority:** P0

As a programming educator, I want to access my teacher workspace so I can manage my assessments securely.

Acceptance criteria:

- Teacher can sign in.
- Teacher can see their assessments.
- Teacher can create a new assessment.
- Teacher cannot see another teacher's private assessment data.

### US-002: Assessment Dashboard

**Priority:** P0

As a teacher, I want a dashboard of assessments and statuses so I can know what needs action.

Acceptance criteria:

- Dashboard lists assessments.
- Each assessment shows status.
- Each assessment shows submission count.
- Each assessment shows pending approvals.
- Each assessment links to report/logs if available.

### US-003: Pilot Account Flag

**Priority:** P1

As an operator, I want to mark an account as a pilot customer so business evidence can be tracked.

Acceptance criteria:

- Account can be flagged as pilot/free/paid.
- Related-party flag can be stored.
- Offer/plan can be associated.
- Evidence can be linked.

## Epic 2: Assessment Creation

### US-010: Assessment Brief Intake

**Priority:** P0

As a programming instructor, I want to describe the learning goal, topic, level, and constraints so AI can generate an assessment draft.

Acceptance criteria:

- Teacher can enter learning goal.
- Teacher can select or type programming topic.
- Teacher can set level/difficulty.
- Teacher can set expected duration.
- Teacher can specify programming language or pseudocode.
- Input is saved before agent execution.

### US-011: Assessment Draft Generation

**Priority:** P0

As a teacher, I want an assessment draft generated from my brief so I can start faster.

Acceptance criteria:

- Assessment Agent generates structured output.
- Output includes title, context, instructions, objectives, expected deliverables, and constraints.
- Output is editable.
- Agent execution is logged.
- Model and cost estimate are stored.

### US-012: Assessment Draft Regeneration

**Priority:** P1

As a teacher, I want to regenerate the draft with additional instructions so I can improve quality without starting over.

Acceptance criteria:

- Teacher can request regeneration.
- Teacher can provide adjustment notes.
- Previous version remains traceable.
- New agent run is logged.

## Epic 3: Rubric Generation And Approval

### US-020: Rubric Draft Generation

**Priority:** P0

As a teacher, I want a rubric draft from the assessment so I can evaluate submissions consistently.

Acceptance criteria:

- Rubric Agent generates criteria.
- Each criterion has weight.
- Each criterion has performance levels.
- Total weight is visible.
- Rubric is structured and editable.
- Agent execution is logged.

### US-021: Rubric Validation

**Priority:** P0

As a teacher, I want the rubric checked for ambiguity, missing criteria, and inconsistent weights so I can trust it before grading.

Acceptance criteria:

- Rubric Agent or validator identifies issues.
- Validation notes are visible.
- Teacher can edit before approval.
- Ambiguity/warning flags are stored.

### US-022: Rubric Approval

**Priority:** P0

As a teacher, I want to approve the rubric before grading starts so AI suggestions are based on my final criteria.

Acceptance criteria:

- Teacher can approve rubric.
- Approved rubric is locked for grading.
- Changes after approval create a new version or explicit update event.
- Approval state is logged.

### US-023: Rubric Version History

**Priority:** P1

As a teacher, I want rubric version history so I can understand what changed before grading.

Acceptance criteria:

- Each major rubric change has a version.
- Versions show timestamp and author/agent.
- Approved version is clearly marked.

## Epic 4: Student Submission Intake

### US-030: Manual Student Submission Creation

**Priority:** P0

As a teacher, I want to add a student answer/submission manually so I can process real assessment responses.

Acceptance criteria:

- Teacher can create submission record.
- StudentSubmission has a `student_identifier`.
- Teacher can paste code/text.
- StudentSubmission is associated with an assessment.

### US-031: File Upload Student Submission

**Priority:** P0

As a teacher, I want to upload simple code/text files as student submissions so I can process student work without retyping.

Acceptance criteria:

- Teacher can upload supported file types.
- File content is stored or extracted.
- File is linked to submission.
- Unsupported files show a clear error.

### US-032: Bulk Submission Intake

**Priority:** P1

As a teacher, I want to import several submissions at once so I can process a cohort faster.

Acceptance criteria:

- Teacher can upload or paste a batch.
- System creates multiple submission records.
- Import errors are shown.
- Submissions can be reviewed before processing.

### US-033: Submission Status

**Priority:** P0

As a teacher, I want to see submission processing status, so I know what is pending.

Acceptance criteria:

- Submission state is visible.
- States include received, pending, analyzed, needs review, approved, rejected/excluded.
- Errors are visible and recoverable.

### US-034: Graded Submission Usage Count

**Priority:** P0

As an operator, I want every analyzed student submission to count against plan usage so pricing and cost controls reflect real AI workload.

Acceptance criteria:

- A `StudentSubmission` is created when the teacher loads a student answer.
- Usage is consumed when grading/feedback analysis is executed, not when a student account is created.
- One analyzed attempt counts as one graded submission.
- Re-analysis can be tracked separately if it creates additional AI cost.
- Usage totals are visible by assessment and organization.

## Epic 5: Grading Assistance

### US-040: Rubric-Based Grading Suggestion

**Priority:** P0

As a teacher, I want to grade suggestions tied to rubric criteria so I can review rather than score from scratch.

Acceptance criteria:

- Grading Agent analyzes submission against approved rubric.
- Suggested score is produced per criterion.
- Evidence snippets or summaries are linked to each criterion.
- Overall suggested score is visible.
- Output is marked as suggestion, not final.
- Agent run is logged.

### US-041: Uncertainty Flags

**Priority:** P0

As a teacher, I want uncertainty flags, so I know where to review carefully.

Acceptance criteria:

- Agent can flag uncertain, incomplete, ambiguous, or risky outputs.
- Flag is visible in teacher review.
- Flag appears in agent log.
- High-uncertainty outputs cannot be bulk-approved silently.

### US-042: Teacher Edit Of Score

**Priority:** P0

As a teacher, I want to edit AI-suggested scores so final grading reflects my judgment.

Acceptance criteria:

- Teacher can modify score per criterion.
- Teacher can add note explaining edit.
- Original suggestion remains traceable.
- Final approved score is clearly separated from AI suggestion.

### US-043: Reject AI Suggestion

**Priority:** P0

As a teacher, I want to reject an AI grading suggestion so poor outputs do not affect students.

Acceptance criteria:

- Teacher can reject suggestion.
- Rejection reason can be recorded.
- Submission status changes accordingly.
- Rejection is logged as evidence.

## Epic 6: Feedback Generation And Approval

### US-050: Individual Feedback Draft

**Priority:** P0

As a teacher, I want feedback drafts for each learner so I can personalize them quickly.

Acceptance criteria:

- Feedback Agent generates feedback based on rubric and grading suggestion.
- Feedback includes strengths, improvement areas, and next step.
- Feedback is student-readable.
- Feedback is editable.
- Agent execution is logged.

### US-051: Feedback Approval

**Priority:** P0

As a teacher, I want to approve feedback before delivery so students only receive reviewed outputs.

Acceptance criteria:

- Feedback has pending/approved/edited/rejected states.
- Teacher can approve edited feedback.
- Approved feedback is marked final.
- Approval event is logged.

### US-052: Tone Adjustment

**Priority:** P1

As a teacher, I want to adjust feedback tone so it matches my teaching style.

Acceptance criteria:

- Teacher can select concise/supportive/direct tone.
- Tone instruction affects generated draft.
- Final feedback remains editable.

## Epic 7: Learning Gaps And Recovery

### US-060: Learning Gap Summary

**Priority:** P0

As a teacher, I want a cohort learning-gap summary so I can decide what to reinforce next.

Acceptance criteria:

- Learning Gap Agent summarizes common mistakes.
- Summary links gaps to rubric criteria.
- Summary shows affected submission count.
- Severity or priority is indicated.
- Agent execution is logged.

### US-061: Recovery Activity Suggestion

**Priority:** P0

As a teacher, I want recovery activity suggestions so students can close specific gaps.

Acceptance criteria:

- Recovery Agent suggests at least one activity.
- Activity is linked to detected gaps.
- Activity includes instructions and expected output.
- Teacher can edit or reject activity.

### US-062: Student-Specific Recovery Notes

**Priority:** P1

As a teacher, I want optional student-specific next steps so feedback can be more actionable.

Acceptance criteria:

- Next step can be generated per student.
- Teacher can approve/edit.
- Output is not delivered automatically.

## Epic 8: Teacher Report

### US-070: Assessment Report

**Priority:** P0

As a teacher, I want a report for each assessment so I can understand outcomes and communicate next steps.

Acceptance criteria:

- Report includes assessment summary.
- Report includes submission count.
- Report includes score distribution or simple stats.
- Report includes learning gaps.
- Report includes recommended next teaching action.
- Report includes time-saved estimate.
- Report is generated by Teacher Report Agent and logged.

### US-071: Export Report

**Priority:** P1

As a teacher, I want to export the report so I can share or archive it.

Acceptance criteria:

- Report can be copied or downloaded.
- Export does not expose internal agent prompts unnecessarily.
- Export includes teacher-approved outputs.

## Epic 9: Evidence And Metrics

### US-080: Agent Execution Log

**Priority:** P0

As an operator, I want every agent execution logged so we can prove AI-native operations and debug the workflow.

Acceptance criteria:

- Every agent run has timestamp, agent, model, input summary, output summary, status, cost estimate, and approval state.
- Logs are associated with assessment/customer.
- Logs are visible in internal dashboard.
- Failed/retried runs are captured.

### US-081: Cost Estimate Per Run

**Priority:** P0

As an operator, I want token and cost estimates per agent run so unit economics can be tracked.

Acceptance criteria:

- Agent log stores model used.
- Input/output token estimate is stored if available.
- Cost estimate is calculated or stored.
- Cost can be aggregated by assessment/customer.

### US-082: Business Evidence Dashboard

**Priority:** P0

As an operator, I want a dashboard of usage, cost, revenue evidence, and agent activity so the hackathon submission is credible.

Acceptance criteria:

- Dashboard shows assessments processed.
- Dashboard shows submissions processed.
- Dashboard shows feedback outputs.
- Dashboard shows agent runs.
- Dashboard shows estimated AI cost.
- Dashboard shows pilot/customer status or links to business ledger.

### US-083: Time Saved Estimate

**Priority:** P1

As a teacher/operator, I want a time-saved estimate so value can be communicated.

Acceptance criteria:

- Teacher can enter baseline time or use default estimate.
- Product estimates time saved per assessment.
- Estimate appears in report/evidence dashboard.
- Estimate is clearly labeled as estimated.

## Epic 10: Billing And Plan Limits

### US-090: Usage Limits

**Priority:** P0

As an operator, I want to track assessment and submission usage so plans remain bounded.

Acceptance criteria:

- Account tracks number of assessments.
- Account tracks graded submissions.
- Usage can be compared to plan limit.
- Overuse can be reported even if not billed automatically.

### US-091: Payment Evidence Link

**Priority:** P1

As an operator, I want to link payment or commitment evidence to a customer so business validation is auditable.

Acceptance criteria:

- Customer/pilot record can store evidence link.
- Revenue event can be marked paid/commitment/manual.
- Related-party flag can be set.

## Epic 11: Question Bank and Closed Assessment Creation

### US-100: Generate Question Batch With AI

**Priority:** P0

As a teacher, I want to generate a batch of objective questions from a learning objective so I can build an assessment bank quickly.

Acceptance criteria:

- Teacher defines subject, topic, difficulty, question count, and type (TF/SC/MC).
- Question Generation Agent produces questions with alternatives, answer key, explanation, and difficulty.
- Output enters review queue in `pending_review` state.
- Agent run is logged with cost estimate.

### US-101: Review AI-Generated Questions

**Priority:** P0

As a teacher, I want to review each AI-generated question and approve, edit, or reject it so only quality questions enter the bank.

Acceptance criteria:

- Review queue shows each question with alternatives, answer key, quality flags, and distractor analysis.
- Teacher can approve, edit, regenerate, or reject each question.
- Approved questions move to `active` state in bank.
- Rejected questions are logged with optional reason.
- All curation actions are audited.

### US-102: Question Bank

**Priority:** P0

As a teacher, I want a searchable bank of approved questions so I can reuse and compose assessments without starting from scratch.

Acceptance criteria:

- Bank shows approved/active questions.
- Filterable by subject, topic, difficulty, type, and learning outcome.
- Each question shows usage history.
- Teacher can retire questions; retired questions are not available for new assessments.
- Bank does not show rejected or pending questions by default.

### US-103: Compose Closed Assessment From Bank

**Priority:** P0

As a teacher, I want to compose a closed assessment from bank questions, with optional AI assistance, so I can configure a balanced evaluation.

Acceptance criteria:

- Assessment Assembly Agent proposes a question set given difficulty distribution and learning outcomes.
- Teacher can accept, swap individual questions, or manually add from bank.
- System validates that all questions have an answer key and are approved.
- Teacher defines scoring policy and grade scale.
- Teacher approves final composition before publish.

### US-104: Publish Closed Assessment and Freeze Snapshot

**Priority:** P0

As a teacher, I want to publish the closed assessment with a frozen snapshot so that subsequent bank edits do not corrupt in-flight results.

Acceptance criteria:

- Publishing creates immutable snapshots of questions, options, answer key, scoring policy, and grade scale.
- Published assessment cannot be structurally edited.
- Changes after publication require a new assessment version or explicit teacher action (annulment/key correction).
- Snapshot creation is logged.

### US-105: Annul Question and Recalculate

**Priority:** P1

As a teacher, I want to void a specific question after grading and trigger an audited recalculation so errors do not penalize students unfairly.

Acceptance criteria:

- Teacher can annul a specific question with a mandatory reason.
- System recalculates all student scores excluding the annulled question.
- Original results are preserved in the audit trail.
- Recalculation event is logged.

## Epic 12: Student Invitation and Access

### US-110: Create Learner List

**Priority:** P0

As a teacher, I want to create or import a list of students for an assessment so I can send them access links.

Acceptance criteria:

- Teacher can add learners manually (email, optional name, optional external ID).
- Teacher can import a CSV with learner emails.
- Each learner is associated with the assessment.
- System does not require learner to create an account.

### US-111: Send Assessment Access Links

**Priority:** P0

As a teacher, I want the system to send secure access links to students so they can respond to the closed assessment without an account.

Acceptance criteria:

- System generates a unique signed token per learner per assessment.
- System sends an email with the access link.
- Teacher can resend links.
- Teacher can revoke access for specific learners.
- Access events are logged.

### US-112: Student Response via Link

**Priority:** P0

As a student, I want to respond to a closed assessment using the link sent to my email, so I do not need to create an account.

Acceptance criteria:

- Opening the link validates the token (not expired, not revoked, assessment accepting responses).
- Student sees questions and selects alternatives.
- Student can review before submitting.
- System confirms submission.
- Link is marked as used after submission.
- System records the attempt.

### US-113: Publish Results and Student Result Access

**Priority:** P0

As a teacher, I want to publish results so students can view their grade and feedback via a secure link.

Acceptance criteria:

- Teacher confirms result publication.
- System sends or makes available a result access link per learner.
- Student sees their grade, score, and approved feedback.
- Correct answers and item details are shown only if teacher has configured visibility.
- Student cannot see other students' results.

### US-114: Item Analytics Report

**Priority:** P0

As a teacher, I want to see difficulty and correct-rate analytics per question so I can understand the quality of my assessment and plan reinforcement.

Acceptance criteria:

- Item Analytics Agent produces correct rate, difficulty index, and distribution per question.
- Agent flags items with possible ambiguity or key errors.
- Agent produces reinforcement suggestions per learning outcome.
- Teacher reviews analytics before sharing.
- Agent run is logged.

## Epic 13: Subject and Curriculum Structure

### US-120: Tag Question With Subject and Learning Outcome

**Priority:** P0

As a teacher, I want every question in the bank to carry a subject, topic, and learning outcome so the system can filter the bank correctly and AI agents have a clear generation scope.

Acceptance criteria:

- Teacher can set `subject_area`, topic tags, and `learning_outcome` on each question.
- Question Generation Agent suggests these values; teacher confirms at curation.
- A question without at least a `subject_area` and `learning_outcome` cannot be set to `active`.
- Assessment assembly filters available bank questions by the declared subject and outcome scope.

### US-121: Filter Question Bank by Curriculum Metadata

**Priority:** P0

As a teacher, I want to filter the question bank by subject, topic, difficulty, and learning outcome so I can find relevant questions quickly.

Acceptance criteria:

- Bank supports filter by `subject_area`, topic tag, `learning_outcome`, difficulty, question type, and status.
- Filters are combinable.
- Results are accurate; a question tagged "OOP / Inheritance" does not appear in a filter for "OOP / Polymorphism" unless also tagged.

### US-122: Generate Curriculum Structure With AI

**Priority:** P1

As a teacher, I want to describe a course and have AI generate a subject structure with units and learning outcomes so I can set up a question bank scope quickly.

Acceptance criteria:

- Teacher provides course description, duration, and content areas.
- AI proposes subject, units/topics, and learning outcomes.
- Teacher reviews and approves before the structure is used for question generation.
- AI-generated curriculum structure enters `pending_review` state.

### US-123: Validate Assessment Curriculum Coverage

**Priority:** P1

As a teacher, I want the system to warn me if my closed assessment does not cover all declared learning outcomes so I can fix gaps before publishing.

Acceptance criteria:

- System checks that each declared learning outcome has at least one question in the composition.
- Missing outcomes generate a non-blocking alert with option to generate additional questions or acknowledge the gap.
- System warns if questions from an unrelated subject are included.

## Explicitly Out Of MVP

### US-OUT-001: Student Chatbot

**Priority:** Out

Student-facing chatbot is not part of MVP.

### US-OUT-002: Fully Autonomous Grading

**Priority:** Out

AI must not finalize grading without teacher approval.

### US-OUT-003: Full LMS

**Priority:** Out

Course content, forums, attendance, calendars, and institutional administration are not part of MVP.

### US-OUT-004: Physical Paper Ingestion (OMR/OCR)

**Priority:** P1 for closed assessments; P2 for open assessments

Paper answer sheet processing with OMR/QR is deferred to P1 and not required for MVP demo.

### US-OUT-005: Enterprise SSO

**Priority:** Out

SSO and institutional integration are deferred.

## MVP Story Cut

The minimum viable story set is:

- US-001
- US-002
- US-010
- US-011
- US-020
- US-021
- US-022
- US-030 / US-031 / US-034
- US-033
- US-040
- US-041
- US-042
- US-050
- US-051
- US-060
- US-061
- US-070
- US-080
- US-081
- US-082
- US-090

If those stories work end to end, GradeOps AI can demo the core business.


---

## Source: `02-product/workflows.md`

# Workflows

This document defines the main product workflows for GradeOps AI MVP.

The workflow principle is:

> AI agents operate repetitive assessment steps; teachers retain judgment, standards, and final approval.

## Student Submission Principle

The product is teacher-led, but not teacher-only.

Student answers are represented as `StudentSubmission` records loaded by the teacher. The MVP does not require student login, but it must process real student responses because graded submissions are the economic and technical usage unit.

```text
1 student answer analyzed = 1 graded submission
```

## Workflow Map

| Workflow | Primary User | MVP Priority |
| --- | --- | --- |
| Teacher onboarding | Teacher | P0 |
| Open assessment creation | Teacher + Assessment Agent | P0 |
| Rubric generation and approval | Teacher + Rubric Agent | P0 |
| Open submission intake | Teacher | P0 |
| Grading assistance (open) | Teacher + Grading Agent | P0 |
| Feedback approval | Teacher + Feedback Agent | P0 |
| Learning gap and recovery | Teacher + Learning Gap/Recovery Agents | P0 |
| Teacher report | Teacher + Teacher Report Agent | P0 |
| Evidence dashboard | Operator / demo | P0 |
| Closed assessment — question generation and curation | Teacher + Question Generation/Distractor/Ambiguity Agents | P0 |
| Closed assessment — composition and publish | Teacher + Assessment Assembly Agent | P0 |
| Student invitation and access | Teacher + System | P0 (closed) / P1 (open) |
| Closed response intake and grading | System + Teacher | P0 |
| Item analytics and reinforcement | Teacher + Item Analytics Agent | P0 |
| Pilot/business evidence | Operator | P1 |

## Core End-To-End Workflows

### Open Assessment

```text
Teacher logs in
  -> creates open assessment brief
  -> Assessment Agent drafts assessment
  -> Rubric Agent drafts and validates rubric
  -> teacher edits/approves assessment and rubric
  -> teacher uploads/pastes submissions or students submit via link
  -> Grading Agent generates rubric-based suggestions
  -> Feedback Agent drafts student feedback
  -> Learning Gap Agent summarizes cohort gaps
  -> Recovery Agent suggests reinforcement activity
  -> teacher reviews/edits/approves outputs
  -> Teacher Report Agent generates report
  -> teacher publishes results
  -> Ops Evidence Agent records logs, cost, usage, and evidence
```

### Closed Assessment

```text
Teacher logs in
  -> creates closed assessment intent
  -> Question Generation Agent produces question batch
  -> Distractor Quality Agent and Ambiguity Review Agent flag issues
  -> teacher reviews and approves questions into bank
  -> Assessment Assembly Agent proposes composition
  -> teacher reviews and approves composition
  -> system creates snapshot and publishes assessment
  -> system sends secure links to students
  -> students respond via portal
  -> deterministic engine grades responses
  -> teacher reviews exceptions
  -> Item Analytics Agent analyzes item performance
  -> teacher publishes results
  -> students view results via result link
  -> Ops Evidence Agent records logs, cost, usage, and evidence
```

## Workflow 1: Teacher Onboarding

### Goal

Teacher reaches the workspace and can start a first assessment.

### Steps

1. Teacher signs in.
2. Teacher sees workspace.
3. Teacher sees CTA: `Create assessment`.
4. Product explains control principle:
   - AI drafts;
   - teacher approves;
   - agent actions are logged.
5. Teacher starts first assessment.

### Required Data

- teacher account;
- email;
- organization or individual label;
- pilot/customer status;
- plan/usage limits if available.

### Success Criteria

- Teacher can reach `Create assessment` without confusion.
- Teacher understands AI will not finalize grading alone.

## Workflow 2: Assessment Creation

### Goal

Generate a practical programming assessment from a teacher-defined learning goal.

### Steps

1. Teacher enters:
   - learning goal;
   - topic;
   - level;
   - language/pseudocode;
   - duration;
   - student count;
   - constraints;
   - optional context.
2. Teacher clicks `Generate assessment`.
3. Assessment Agent runs.
4. Product stores agent run log.
5. Teacher reviews draft.
6. Teacher edits or regenerates.
7. Teacher accepts draft for rubric generation.

### Agent Output

Assessment Agent should return structured data:

```json
{
  "title": "Basic Java Control Flow Assessment",
  "context": "Students must solve...",
  "learning_objectives": [],
  "instructions": [],
  "deliverables": [],
  "constraints": [],
  "estimated_duration_minutes": 90,
  "difficulty": "basic"
}
```

### Failure Handling

| Failure | Handling |
| --- | --- |
| Agent timeout | Show retry option and log failure |
| Output invalid | Show validation error and allow regeneration |
| Teacher dislikes draft | Allow edit or regenerate with notes |
| Missing input | Require minimum fields before running agent |

## Workflow 3: Rubric Generation And Approval

### Goal

Create a structured rubric that can drive grading suggestions.

### Steps

1. Teacher requests rubric.
2. Rubric Agent generates criteria and weights.
3. Rubric Agent validates consistency.
4. Product displays:
   - criteria;
   - weights;
   - levels;
   - validation notes;
   - ambiguity warnings.
5. Teacher edits rubric.
6. Teacher approves rubric.
7. Approved rubric becomes grading baseline.

### Approval Rule

Grading cannot proceed unless:

- rubric is approved; or
- workflow is explicitly marked as demo/draft with visible warning.

### Rubric Output Structure

```json
{
  "criteria": [
    {
      "id": "C1",
      "name": "Correct use of conditionals",
      "weight": 25,
      "levels": [
        {
          "label": "Excellent",
          "score": 25,
          "description": "Uses conditionals correctly..."
        }
      ],
      "common_mistakes": []
    }
  ],
  "validation_notes": [],
  "total_weight": 100
}
```

## Workflow 4: Open Submission Intake

### Goal

Collect student answers/submissions in a simple MVP-compatible way without requiring student accounts.

### Supported Intake

- paste code/text;
- upload simple files;
- simple bulk import/paste if available.

### Steps

1. Teacher opens assessment.
2. Teacher adds student submissions.
3. For each student submission:
   - `student_identifier` is added;
   - optional display name can be added;
   - code/text/file is stored;
   - status becomes `received`.
4. Teacher reviews submission list.
5. Teacher starts analysis.

### Failure Handling

| Failure | Handling |
| --- | --- |
| Unsupported file | Reject with clear message |
| Empty submission | Mark invalid |
| Duplicate student identifier | Warn teacher |
| Large submission | Warn and estimate higher cost or require confirmation |

## Workflow 4b: Closed Assessment — Question Generation and Curation

### Goal

Build an approved question bank from AI-generated questions, curated by the teacher.

### Steps

1. Teacher defines evaluative intent: subject, topic, difficulty distribution, question count, question types, level.
2. Question Generation Agent produces question batch with alternatives, answer key, explanations, and difficulty.
3. Distractor Quality Agent evaluates each incorrect alternative.
4. Ambiguity Review Agent checks each question for interpretation problems.
5. System presents curation queue showing questions with quality flags.
6. Teacher reviews each question:
   - approve: question moves to `approved` in bank;
   - edit and approve: teacher edits content, then approves;
   - regenerate: system requests new question for same slot;
   - reject: question discarded with optional reason.
7. Approved questions become available for assessment composition.

### Curation Queue States

| State | Meaning |
| --- | --- |
| `ai_generated` | Question created by agent |
| `pending_review` | Waiting for teacher action |
| `approved` | Teacher validated and accepted |
| `needs_revision` | Teacher flagged for rework |
| `rejected` | Teacher discarded |

### Failure Handling

| Failure | Handling |
| --- | --- |
| No questions generated | Show error; allow retry with adjusted parameters |
| All questions flagged critical ambiguity | Warn teacher; allow approval with explicit confirmation |
| Question generation timeout | Log failure; allow retry |

## Workflow 4c: Closed Assessment — Composition, Publish, and Student Invitation

### Goal

Compose a closed assessment from approved bank questions, publish it, and deliver secure access links to students.

### Steps

1. Teacher creates a new closed assessment (or continues from question bank).
2. Teacher defines: title, date, duration, learner list, scoring policy, grade scale.
3. Assessment Assembly Agent proposes a question composition from the approved bank.
4. Teacher reviews composition: questions selected, difficulty distribution, outcome coverage, scores.
5. Teacher approves composition (or modifies and approves).
6. System validates:
   - all questions are approved;
   - all questions have a defined correct answer;
   - total score is consistent;
   - no retired or rejected items are included.
7. System creates snapshot: questions, options, answer key, scoring policy, scale are frozen.
8. Assessment transitions to `published`.
9. System generates a unique `AssessmentInvitation` per `LearnerRef`.
10. System sends email with access link to each learner.

### Failure Handling

| Failure | Handling |
| --- | --- |
| Bank does not have enough approved questions | Alert teacher; suggest generating more questions |
| Learning outcome gap | Alert teacher; allow proceed with explicit acknowledgment |
| Snapshot fails | Rollback; prevent publication |
| Email delivery fails | Log; teacher can resend from invitation management |

## Workflow 4d: Student Response via Secure Link

### Goal

Enable students to respond to an assessment without a registered account.

### Steps — Closed Assessment

1. Student receives email with `assessment_access_link`.
2. Student opens link; system validates token (not expired, not revoked, assessment in `accepting_responses` state).
3. Student sees assessment instructions and questions.
4. Student selects alternatives for each question.
5. Student reviews their selections.
6. Student confirms submission.
7. System records `AssessmentAttempt` with `ClosedResponse`.
8. System closes or marks link as used.
9. Deterministic engine processes response against snapshot.
10. After teacher approves results, system sends `result_access_link` or student can request via email.

### Steps — Open Assessment

1. Teacher shares access link or student submits file/text via teacher-managed flow (same as Workflow 4).
2. Open assessment digital submission via link: P1.

### Security Rules at Intake

| Rule | Handling |
| --- | --- |
| Token expired | Show friendly error; allow magic link request |
| Token already used (submitted) | Show confirmation page; do not allow re-submission by default |
| Assessment not in `accepting_responses` | Inform student; do not expose internal state details |
| Attempt from different device | Allow unless single-device policy is set |

## Workflow 5: Grading Assistance

### Goal

Generate rubric-based scoring suggestions while preserving teacher authority.

### Steps

1. Teacher clicks `Analyze submissions` for selected `StudentSubmission` records.
2. Grading Agent processes each student submission.
3. Agent returns score suggestion per rubric criterion.
4. Agent flags uncertainty.
5. Product displays review queue.
6. Teacher reviews each suggestion.
7. Teacher approves, edits, rejects, or marks needs review.

### Grading Output

```json
{
  "submission_id": "SUB-001",
  "suggested_total_score": 82,
  "criteria_results": [
    {
      "criterion_id": "C1",
      "suggested_score": 20,
      "evidence_summary": "Uses if/else correctly...",
      "issues": [],
      "uncertainty": "low"
    }
  ],
  "overall_feedback_basis": [],
  "uncertainty_flags": []
}
```

### Teacher Review Actions

| Action | Meaning |
| --- | --- |
| Approve | Teacher accepts suggestion |
| Edit | Teacher changes score or notes |
| Reject | Teacher rejects AI output |
| Needs review | Teacher defers decision |
| Exclude | Submission excluded from report |

### Control Principle

AI output must be labeled as suggestion until teacher approval.

## Workflow 6: Feedback Draft And Approval

### Goal

Generate useful student-facing feedback based on rubric and teacher-reviewed grading.

### Steps

1. Feedback Agent uses grading suggestion or teacher-approved score.
2. Agent drafts feedback.
3. Teacher reviews feedback.
4. Teacher edits tone/content if needed.
5. Teacher approves final feedback.
6. Feedback becomes available for export/delivery.

### Feedback Output

```json
{
  "student_identifier": "student-01",
  "summary": "Good progress...",
  "strengths": [],
  "improvement_areas": [],
  "next_steps": [],
  "rubric_references": []
}
```

### Delivery

MVP delivery can be:

- copy/export;
- downloaded report;
- manual sending by teacher.

Automatic student delivery is not required for MVP.

## Workflow 7: Learning Gap And Recovery

### Goal

Summarize repeated cohort issues and suggest recovery actions.

### Steps

1. Learning Gap Agent reads rubric results and feedback basis.
2. Agent groups common mistakes.
3. Agent identifies affected criteria and severity.
4. Recovery Agent suggests reinforcement activity.
5. Teacher reviews suggestions.
6. Approved recovery action appears in report.

### Learning Gap Output

```json
{
  "gaps": [
    {
      "topic": "Loop termination condition",
      "criterion_ids": ["C2"],
      "affected_submissions": 12,
      "severity": "high",
      "evidence_summary": "Students often used..."
    }
  ]
}
```

### Recovery Output

```json
{
  "activity_title": "Fixing loop termination errors",
  "target_gap": "Loop termination condition",
  "instructions": [],
  "expected_output": "",
  "teacher_notes": ""
}
```

## Workflow 8: Teacher Report

### Goal

Generate a teacher-facing summary of the assessment run.

### Steps

1. Teacher requests report.
2. Teacher Report Agent gathers:
   - assessment;
   - rubric;
   - submission results;
   - feedback status;
   - learning gaps;
   - recovery suggestions;
   - usage/cost evidence.
3. Report is generated.
4. Teacher can edit summary.
5. Report can be exported or screenshotted.

### Report Sections

- assessment overview;
- submission count;
- grading summary;
- common mistakes;
- learning gaps;
- recommended next teaching action;
- recovery activity;
- time-saved estimate;
- agent/evidence summary.

## Workflow 9: Agent Logs And Evidence Dashboard

### Goal

Prove AI-native operations, cost awareness, and business evidence.

### Steps

1. Every agent run creates an event.
2. Events are stored.
3. Dashboard aggregates:
   - assessments;
   - submissions;
   - agent runs;
   - feedback outputs;
   - model usage;
   - cost estimates;
   - approval states;
   - failures/retries.
4. Operator uses dashboard for demo and submission evidence.

### Dashboard Minimum

| Metric | Purpose |
| --- | --- |
| Assessments processed | Product usage |
| Submissions reviewed | Operational volume |
| Feedback outputs | Value output |
| Agent runs | AI-native proof |
| Teacher approval rate | Trust and quality |
| Estimated AI cost | Unit economics |
| Time saved estimate | Business value |
| Failed/retried runs | Reliability evidence |

## Workflow 10: Pilot Business Evidence

### Goal

Connect product usage to business validation.

### Steps

1. Operator creates customer/pilot record.
2. Customer is associated with assessment runs.
3. Payment/commitment evidence is stored externally or linked.
4. Product logs usage.
5. Operator records testimonial/feedback.
6. Evidence is summarized for hackathon.

### Evidence Fields

- customer ID;
- segment;
- related-party flag;
- offer/plan;
- payment/commitment status;
- assessments processed;
- submissions processed;
- agent runs;
- estimated cost;
- time saved;
- testimonial status.

## Workflow 5b: Closed Assessment — Grading and Exception Review

### Goal

Grade closed responses deterministically and surface exceptions for teacher review.

### Steps

1. System receives `AssessmentAttempt` records.
2. Deterministic engine compares each `ClosedResponse` against the `AssessmentOptionSnapshot` (frozen answer key).
3. Engine applies `ScoringPolicy` (full credit, partial credit, penalty) per question.
4. Engine calculates total score and converts to grade using the frozen scale.
5. System identifies exceptions:
   - blank answers;
   - duplicate attempts;
   - student not associated to `LearnerRef`;
   - response with invalid option reference.
6. Teacher reviews exception queue.
7. Teacher resolves exceptions (exclude, assign manually, flag for re-intake).
8. Teacher confirms results.
9. System generates item analytics report via Item Analytics Agent.
10. Teacher reviews analytics.
11. Teacher publishes results.
12. System sends `result_access_link` to students.

### Teacher Override Actions

| Action | Audit |
| --- | --- |
| Annul a question | Triggers recalculation for all students; logged with reason |
| Correct answer key | Triggers recalculation; original result preserved |
| Exclude a student attempt | Logged with reason |
| Manual grade override | Logged with reason; AI does not override teacher |

## Workflow States

### Assessment Lifecycle (Unified)

```text
draft
  -> pending_teacher_review         (AI output ready: rubric or question batch)
  -> approved                       (Teacher approved rubric / question composition)
  -> published                      (Snapshot created; links sent)
  -> accepting_responses            (Open for student input)
  -> responses_received             (At least one response)
  -> grading_in_progress            (Grading engine or agents running)
  -> pending_teacher_review         (Grading results ready for teacher)
  -> graded                         (Teacher confirmed results)
  -> results_published              (Results visible to students)
  -> archived
```

### Open Assessment Lifecycle (legacy states preserved for compatibility)

```text
draft
  -> rubric_pending_review
  -> ready_for_submissions
  -> submissions_received
  -> grading_in_progress
  -> pending_teacher_review
  -> approved
  -> reported
  -> archived
```

### Submission Lifecycle

```text
received
  -> analysis_pending
  -> analyzed
  -> needs_review
  -> approved | edited_by_teacher | rejected | excluded
```

### Agent Run Lifecycle

```text
queued
  -> running
  -> succeeded | failed | retried
  -> requires_human_review
  -> approved | edited | rejected
```

## Critical Failure Workflows

### Agent Failure

1. Agent fails.
2. Status becomes `failed`.
3. Failure is logged.
4. Teacher sees retry option.
5. Product prevents silent loss of work.

### Low Confidence Output

1. Agent marks uncertainty.
2. Submission becomes `requires_human_review`.
3. Bulk approval is blocked or warned.
4. Teacher must inspect manually.

### Teacher Rejects Output

1. Teacher rejects score/feedback.
2. Rejection reason can be captured.
3. Final report notes teacher override count.
4. Agent output remains in audit trail.

### Cost Spike Warning

1. Submission is unusually long or model fallback is required.
2. Product warns operator/teacher if needed.
3. Cost is logged.
4. Premium fallback is not default.

## Workflow Conclusion

The product workflow should feel controlled, transparent, and operational.

The best demo is not a tour of screens. It is a proof that:

> A real assessment moved from learning goal to rubric, submissions, grading suggestions, feedback, report, teacher approval, and auditable AI-agent evidence.


