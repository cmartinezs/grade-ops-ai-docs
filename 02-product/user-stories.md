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

## Epic 4: Submission Intake

### US-030: Manual Submission Creation

**Priority:** P0

As a teacher, I want to add a student submission manually so I can process real assessment answers.

Acceptance criteria:

- Teacher can create submission record.
- Submission has student identifier.
- Teacher can paste code/text.
- Submission is associated with an assessment.

### US-031: File Upload Submission

**Priority:** P0

As a teacher, I want to upload simple code/text files so I can process student work without retyping.

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

As a teacher, I want to see submission processing status so I know what is pending.

Acceptance criteria:

- Submission state is visible.
- States include received, pending, analyzed, needs review, approved, rejected/excluded.
- Errors are visible and recoverable.

## Epic 5: Grading Assistance

### US-040: Rubric-Based Grading Suggestion

**Priority:** P0

As a teacher, I want grading suggestions tied to rubric criteria so I can review rather than score from scratch.

Acceptance criteria:

- Grading Agent analyzes submission against approved rubric.
- Suggested score is produced per criterion.
- Evidence snippets or summaries are linked to each criterion.
- Overall suggested score is visible.
- Output is marked as suggestion, not final.
- Agent run is logged.

### US-041: Uncertainty Flags

**Priority:** P0

As a teacher, I want uncertainty flags so I know where to review carefully.

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

### US-OUT-004: OCR-First Grading

**Priority:** Out

Photo/OCR workflows are deferred.

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
- US-030 / US-031
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
