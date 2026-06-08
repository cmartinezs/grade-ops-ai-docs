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
| Student | Feedback recipient | Impact beneficiary | P2 for MVP |
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

## P2 Persona: Student

### Profile

A learner receiving feedback from a programming assessment.

Students are not the primary MVP user, but their experience matters.

### Goals

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

### Trust Requirements

- Should know teacher has final authority.
- Should receive understandable feedback.
- Should not receive raw AI uncertainty or internal logs.
- Should not have personal data exposed unnecessarily.

### Success Moment

> I know what I missed, why it matters, and what to practice next.

### Product Messaging

Student-facing messaging is not primary for MVP. If needed:

> Faster, clearer feedback reviewed by your teacher.

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
5. Student recipient experience;
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
| Student | Receive clear teacher-approved feedback |
| Reviewer | Support review without replacing teacher authority |

## Persona Conclusion

GradeOps AI should not try to satisfy every education stakeholder in the MVP.

The first product must delight the educator who feels the pain directly:

> The person who has to turn 30 programming submissions into fair scores, useful feedback, and a clear next teaching action.
