# 01 Business Consolidated

> Generated for NotebookLM from `01-business`. This is a full-content consolidation, not a summary.

## Source Files

- `01-business/README.md`
- `01-business/business-model.md`
- `01-business/customer-discovery.md`
- `01-business/go-to-market.md`
- `01-business/hackathon-strategy.md`
- `01-business/pricing.md`

## Consolidated Content


---

## Source: `01-business/README.md`

# 01 Business

This folder defines how GradeOps AI becomes a real, measurable business.

It answers:

> Who buys this, why they buy, how we validate willingness to pay, and how we prove business viability?

## Essence

`01-business` translates the strategic foundation from `00-project` into market execution:

- business model;
- customer discovery;
- go-to-market;
- pricing;
- hackathon business evidence.

The focus is not broad market theory. The focus is getting real educators, real usage, real payment signals, and credible evidence during the hackathon window.

## How To Use This Folder

Use these files when planning outreach, pilots, pricing, and business validation:

1. `business-model.md` — ICP, segments, value proposition, revenue streams, risks, and validation gates.
2. `customer-discovery.md` — hypotheses, interview scripts, scoring, consent, and evidence capture.
3. `go-to-market.md` — founder-led sales motion, outreach messages, landing copy, funnel, and pilot path.
4. `pricing.md` — plans, usage limits, CLP/USD testing prices, overuse, discounts, and margins.
5. `hackathon-strategy.md` — business evidence map for the hackathon submission.

## What Belongs Here

- Customer segments.
- Paid pilot offers.
- Pricing experiments.
- Sales scripts.
- Discovery scripts.
- Funnel metrics.
- Revenue and customer evidence strategy.

## What Does Not Belong Here

- Product implementation details.
- Internal agent contracts.
- Database/API design.
- Architecture deployment choices.
- Raw notes or unvalidated assumptions without a clear validation plan.

## Operating Principle

Business evidence is a product output. Every pilot should produce usage, revenue, cost, feedback, and testimonial evidence wherever possible.


---

## Source: `01-business/business-model.md`

# Business Model

GradeOps AI is an AI-native assessment operations business for programming educators.

It helps teachers, tutors, bootcamps, and small academies run practical programming assessments with AI agents while preserving teacher authority over grading, feedback, and student-facing decisions.

This document defines the business model for the hackathon and early market validation. The canonical strategic foundation remains `../00-project/`.

## Canonical Alignment

| Source Decision | Business Interpretation |
| --- | --- |
| Project name | GradeOps AI |
| Initial wedge | Practical programming assessments |
| Initial market | Programming educators, tutors, bootcamps, and small academies |
| Category | Education & Human Potential |
| Core promise | Run the next programming assessment with AI agents |
| Pricing model | Bounded by assessments and graded submissions |
| Human role | Teacher reviews and approves important outputs |
| AI role | Agents execute repetitive workflow steps and produce structured evidence |
| Evidence policy | Usage, cost, revenue, testimonials, and agent logs are first-class outputs |

## Business Thesis

Programming educators do not only need help writing tests. They need assessment operations capacity.

The recurring business pain is:

> Creating practical assessments, reviewing code, applying rubrics, writing personalized feedback, identifying learning gaps, and deciding recovery actions takes too much manual time and is hard to scale consistently.

GradeOps AI converts that pain into a measurable business offer:

> We operate your next programming assessment with AI agents: activity design, rubric, grading assistance, feedback drafts, learning-gap report, teacher approval, and evidence logs.

The business is viable if customers believe the workflow saves enough time, improves feedback quality, and creates enough reporting value to justify a recurring software spend or a paid pilot.

## Ideal Customer Profile

### Primary ICP

Independent or small-team programming educators who run recurring practical assessments and do not have dedicated academic operations support.

| Attribute | Target |
| --- | --- |
| Teaching domain | Programming, algorithms, introductory software development, web/mobile/backend basics |
| Assessment type | Practical exercises, code submissions, short projects, rubric-based tasks |
| Team size | Solo educator, tutor, small academy, small bootcamp, cohort-based training team |
| Buying power | Can pay directly or approve a small pilot without institutional procurement |
| Pain intensity | High grading and feedback workload |
| Trust requirement | Teacher must remain in control |
| Adoption requirement | Workflow must work without replacing current teaching style |

### Secondary ICP

Small education providers that need standardization across multiple cohorts or instructors.

Examples:

- small coding academies;
- bootcamp operators;
- technical training teams;
- continuing education programs;
- instructors coordinating repeated sections of the same course.

## Customer Segments

| Segment | Pain | Buying Trigger | Best Offer |
| --- | --- | --- | --- |
| Independent programming teacher | Time spent grading and writing feedback | Upcoming assessment with many submissions | Pilot Pack |
| Tutor with several students | Need to give feedback faster and look professional | Growing student base | Teacher Lite / Teacher Pro |
| Small academy | Need consistent grading and reporting across cohorts | New cohort starts or quality issue appears | Cohort Pro |
| Bootcamp instructor | Fast feedback cycle and student risk visibility | Sprint project, module exam, capstone milestone | Pilot Pack / Cohort Pro |
| Program manager | Evidence of learning progress and instructor consistency | Reporting pressure or student retention risk | Cohort Pro / custom pilot |

## Jobs To Be Done

### Functional Job

When I run a programming assessment, I want to move from learning goal to reviewed feedback and teacher report with less manual effort, so I can spend more time teaching and supporting students.

### Emotional Job

I want to trust that feedback is consistent and useful without feeling that AI is replacing my professional judgment.

### Business Job

I want to deliver better assessment operations without hiring more staff or manually scaling every part of the workflow.

## Value Proposition

### For Teachers

- Save time on repetitive grading and feedback preparation.
- Generate structured rubrics faster.
- Detect repeated misconceptions earlier.
- Approve or edit AI outputs before delivery.
- Produce reports without manual consolidation.

### For Students

- Receive faster and more actionable feedback.
- Understand mistakes by rubric criterion.
- Get targeted recovery recommendations.
- Experience more consistent evaluation criteria.

### For Small Education Providers

- Operate with more academic capacity without immediately hiring.
- Standardize assessment workflow across instructors.
- Produce evidence of learning outcomes.
- Reduce feedback bottlenecks.
- Improve visibility into cohort risk.

## Productized Offer

### Initial Hackathon Offer

> **Pilot Pack — US$99 one-time**  
> We operate 3 real programming assessments with AI agents, up to 150 graded submissions, onboarding, feedback drafts, teacher report, and evidence dashboard.

This is the primary early revenue vehicle because it is easier to sell than a self-serve subscription before the product has full polish.

### Subscription Path

After pilot validation, customers can move into bounded monthly plans:

| Plan | Target Customer | Included Usage |
| --- | --- | --- |
| Teacher Lite | Tutor or solo educator testing the workflow | 3 assessments / 90 graded submissions |
| Teacher Pro | Active programming educator | 10 assessments / 300 graded submissions |
| Cohort Pro | Small academy or bootcamp | 30 assessments / 1,000 graded submissions |

The business should never sell unlimited AI grading. The commercial unit is assessment operations plus graded-submission volume.

## Revenue Model

| Revenue Stream | Timing | Notes |
| --- | --- | --- |
| Pilot Pack | One-time | Best for immediate hackathon validation |
| Monthly subscription | Recurring | Bounded by assessments and submissions |
| Overuse fees | Usage-based | Additional graded submissions, reports, or premium review |
| Guided onboarding | One-time or bundled | Useful for small academies and bootcamps |
| Cohort setup | One-time or premium tier | Applies when several instructors/courses are involved |

## Unit Economics

The primary unit is:

> 1 assessment = activity + rubric + grading assistance for 30 submissions + personalized feedback + teacher report.

The business must track:

- cost per agent run;
- cost per assessment;
- cost per graded submission;
- cost per active teacher;
- cost per customer;
- revenue per customer;
- gross margin per plan;
- payment fees;
- marketing/customer acquisition spend;
- related-party revenue separately from arms-length revenue.

## Business Evidence Required

Every pilot should produce business evidence, not only product feedback.

| Evidence | Why It Matters |
| --- | --- |
| Customer identity and role | Proves real market contact |
| Pain severity | Shows whether the problem is worth paying for |
| Current workflow | Reveals switching friction |
| Payment or commitment | Proves willingness to pay |
| Assessment processed | Proves product usage |
| Submissions processed | Proves volume and operational value |
| Agent logs | Proves AI-native operations |
| Time saved estimate | Supports business value |
| Testimonial | Supports pitch and category impact |
| Cost per run | Supports sustainability |

## Acquisition Strategy

GradeOps AI starts with founder-led sales.

The first customers should come from:

- existing educator networks;
- programming teachers;
- bootcamp instructors;
- small academies;
- technical communities;
- LinkedIn outreach;
- referral conversations from educators.

Do not start with large schools, universities, or procurement-heavy institutions. Their sales cycles are too slow for the hackathon window.

## Retention Strategy

Retention depends on assessment recurrence.

The product should make it easy for a teacher to reuse a successful workflow:

- clone assessment setup;
- reuse rubric patterns;
- compare cohorts;
- track recurring learning gaps;
- export reports;
- keep a history of approved feedback;
- move from one assessment to the next with less setup.

## Competitive Positioning

GradeOps AI should not compete as a generic AI quiz generator.

| Alternative | Why It Falls Short | GradeOps AI Position |
| --- | --- | --- |
| LMS | Organizes courses but leaves assessment work mostly manual | Operates the assessment workflow |
| Quiz generator | Generates questions but does not manage grading/feedback/reporting | Runs end-to-end assessment operations |
| Generic chatbot | Helpful but unstructured and hard to audit | Produces structured outputs, logs, and approval states |
| Manual grading | Trusted but slow and inconsistent under workload | AI drafts; teacher approves |
| Autograder | Useful for tests but narrow for rubric and feedback | Combines rubric-based judgment, feedback, and reporting |

## Business Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Teachers distrust AI grading | Low adoption | Keep teacher approval mandatory and show uncertainty flags |
| Product becomes too broad | Slow delivery and weak pitch | Stay focused on programming assessments |
| Pricing is too low | Weak business viability | Sell value and bounded usage, not token cost |
| Usage is unbounded | Margin risk | Cap assessments and submissions |
| Revenue comes only from friends | Weak hackathon evidence | Separate related-party revenue and prioritize arms-length pilots |
| Procurement cycles are long | No revenue in time | Sell to small buyers with direct decision power |
| Customer evidence is weak | Poor submission | Capture interviews, testimonials, payment evidence, and dashboard screenshots from day one |

## Validation Gates

| Gate | Pass Signal | Fail Signal |
| --- | --- | --- |
| Problem validation | 10+ educators confirm grading/feedback pain | Pain is occasional or low-value |
| Buyer validation | 3+ customers accept paid pilot or strong commitment | Users like the idea but will not pay |
| Workflow validation | Teachers complete full assessment flow | The team must manually patch every run |
| Trust validation | Teachers approve AI-assisted feedback | Teachers reject AI involvement in grading |
| Margin validation | Cost per assessment remains controlled | Long submissions or retries destroy margin |
| Repeat-use validation | At least one customer wants another assessment | Product is seen as one-time demo |

## Current Business Conclusion

GradeOps AI should be treated as a focused assessment-operations business, not a broad education platform.

The immediate business objective is not to maximize feature breadth. It is to prove:

1. programming educators have a painful recurring assessment workflow;
2. they will pay for AI-assisted assessment operations;
3. AI agents can execute meaningful parts of that workflow in production;
4. teachers can remain in control;
5. the business can track revenue, cost, usage, and value per customer.


---

## Source: `01-business/customer-discovery.md`

# Customer Discovery

Customer discovery for GradeOps AI exists to validate whether programming educators will pay for AI-operated assessment workflows.

The goal is not to confirm that educators find AI interesting. The goal is to prove that the assessment workflow is painful enough, frequent enough, and valuable enough to support a real business.

## Discovery Goals

| Goal | Question To Answer |
| --- | --- |
| Problem severity | Is assessment work painful enough to pay for? |
| Workflow clarity | Which steps consume the most time and produce the most frustration? |
| Trust model | What must remain under teacher control? |
| Buying trigger | What event makes a teacher or academy pay now? |
| Offer validation | Is the Pilot Pack understandable and credible? |
| Pricing validation | Which price points create real willingness to pay? |
| Evidence validation | What proof does the buyer need before adoption? |

## Canonical Hypotheses

GradeOps AI is currently built around these hypotheses:

1. Programming assessment workflows are operationally heavy.
2. Teachers spend significant recurring time creating assessments, grading code, writing feedback, and preparing reports.
3. Small education providers cannot easily hire academic operations support.
4. Teachers will consider AI support if they keep final approval.
5. Customers are more likely to buy a guided pilot than a self-serve subscription before trust is established.
6. Pricing must be bounded by assessments and graded submissions.
7. Agent logs, approval states, and cost tracking are not only technical features; they are trust and business evidence.

## Who To Interview First

Prioritize buyers or direct workflow owners, not generic education observers.

| Priority | Target | Why |
| --- | --- | --- |
| P0 | Independent programming teachers | Fastest path to real pain and direct payment |
| P0 | Tutors with recurring students | Small buyer, clear workload, direct decision |
| P0 | Bootcamp instructors | High submission volume and fast assessment cycles |
| P1 | Small academy founders | Can buy pilots and care about reporting/consistency |
| P1 | Program managers | Understand quality and cohort-level reporting needs |
| P2 | University/college instructors | Strong problem, but procurement may be slow |
| P2 | School administrators | Useful later, not ideal for first hackathon revenue |

## Interview Screening

Use a short screener before a full interview.

### Must-Have Criteria

- Teaches programming or programming-adjacent skills.
- Runs practical assessments, exercises, labs, assignments, or projects.
- Reviews student work manually at least sometimes.
- Has experienced feedback or grading workload pressure.
- Can influence adoption or payment for a small pilot.

### Good-Fit Signals

- Has 20+ submissions per assessment.
- Reuses or adapts rubrics.
- Teaches cohorts repeatedly.
- Needs to report results to students, managers, or clients.
- Has complained about grading, feedback, consistency, or student recovery.

### Poor-Fit Signals

- Only uses auto-graded multiple-choice quizzes.
- Has no recurring assessment workflow.
- Cannot pay or influence payment.
- Wants a full LMS replacement.
- Wants AI to replace teacher judgment entirely.

## Interview Structure

Keep the interview focused on current behavior, not hypothetical enthusiasm.

### 1. Context

- What do you teach?
- Who are your students?
- How often do you run programming assessments?
- What kinds of submissions do students deliver?
- How many submissions do you typically review per assessment?

### 2. Current Workflow

- Walk me through your last programming assessment from planning to final feedback.
- What tools did you use?
- Where did students submit their work?
- How did you define the rubric or criteria?
- How did you grade?
- How did you send feedback?
- Did you prepare any report or summary afterward?

### 3. Pain And Time

- Which step took the most time?
- Which step was the most annoying or repetitive?
- How many hours did the whole assessment cycle take?
- How much of that time felt low-value or administrative?
- What happens when you are overloaded?
- What quality tradeoffs do you make when time is short?

### 4. Trust And Control

- Which parts would you allow AI to draft?
- Which parts would you never allow AI to decide alone?
- What would you need to review before sending feedback to students?
- What kind of audit trail would make you trust the workflow?
- What mistakes would be unacceptable?

### 5. Buying And Adoption

- Have you paid for teaching, grading, automation, or AI tools before?
- Who decides whether a tool can be used?
- What would make you try a paid pilot?
- What would block adoption?
- What evidence would convince you after the first run?
- Would you rather pay per assessment, per month, or per student/submission?

### 6. Offer Test

Show the offer in plain language:

> We operate your next 3 programming assessments with AI agents: activity design, rubric, grading assistance, personalized feedback drafts, learning-gap report, and teacher approval. Up to 150 graded submissions.

Ask:

- Is this clear?
- Which part is most valuable?
- Which part feels unnecessary?
- What would make this feel unsafe?
- Would you pay for this as a pilot?
- At what price would it feel too cheap to trust?
- At what price would it feel expensive but possible?
- At what price would it be clearly too expensive?

## Do Not Pitch Too Early

During discovery, avoid selling immediately. The first goal is to understand the real workflow.

Bad question:

> Would you use an AI grading platform?

Better question:

> Tell me what happened the last time you had to review 30 programming submissions.

Bad question:

> Would this save you time?

Better question:

> Which step did you postpone, rush, or simplify because you did not have enough time?

## Evidence To Capture Per Interview

| Field | Description |
| --- | --- |
| Interview ID | Unique identifier |
| Date | Interview date |
| Contact | Name, email, phone if permitted |
| Role | Teacher, tutor, instructor, founder, manager |
| Segment | Independent, tutor, bootcamp, academy, etc. |
| Current workflow | Summary of tools and process |
| Assessment volume | Submissions per assessment and assessments per month |
| Time estimate | Hours per assessment cycle |
| Pain severity | 1-5 score |
| Trust requirement | What must be reviewed/approved |
| Buying authority | Can buy, influence, or only recommend |
| Price reaction | Response to Pilot Pack and subscription ideas |
| Objections | Trust, privacy, cost, workflow, accuracy, policy |
| Next step | No fit, follow-up, demo, pilot, paid pilot |
| Related-party flag | Whether customer is related to team/founder |
| Consent status | Whether testimonial/contact evidence can be used |

## Pain Severity Scoring

| Score | Meaning | Interpretation |
| --- | --- | --- |
| 1 | Mild annoyance | Not a buyer |
| 2 | Occasional inconvenience | Useful feedback, weak buyer |
| 3 | Recurring pain | Potential buyer if workflow is easy |
| 4 | Strong recurring pain | Good pilot candidate |
| 5 | Urgent operational bottleneck | Highest priority pilot candidate |

## Buying Intent Scoring

| Score | Meaning |
| --- | --- |
| 0 | No interest |
| 1 | Likes idea but no action |
| 2 | Wants demo |
| 3 | Wants to test with a real assessment |
| 4 | Willing to pay or sign pilot commitment |
| 5 | Paid, committed, or introduced another buyer |

## Discovery Targets For Hackathon

Minimum evidence target:

- 10+ educator discovery conversations;
- 5+ strong pilot candidates;
- 3+ paid pilots or payment commitments;
- 1+ testimonial with permission;
- 1+ clear arms-length customer if possible;
- explicit record of related-party revenue if any.

Stretch target:

- 20+ discovery conversations;
- 10+ demo calls;
- 5+ pilots;
- 3+ paying customers;
- 100+ submissions processed;
- repeated-use signal from at least one customer.

## Discovery Synthesis Template

After every 5 interviews, summarize:

```markdown
# Discovery Batch Summary

## Batch
- Dates:
- Number of interviews:
- Segments:

## Patterns
- Top repeated pain:
- Most time-consuming step:
- Strongest buying trigger:
- Strongest trust requirement:
- Most common objection:

## Pricing Signals
- Pilot Pack reaction:
- Subscription reaction:
- Preferred billing unit:
- Price resistance:

## Product Implications
- Must build:
- Can fake/manual-assist temporarily:
- Should not build:
- Needs clarification:

## Business Decision
- Continue:
- Pivot:
- Narrow segment:
- Change offer:
```

## Interview Output Classification

| Classification | Meaning | Next Action |
| --- | --- | --- |
| Research only | Useful insight, no sales path | Keep as evidence, no immediate follow-up |
| Demo candidate | Interested but not ready to pay | Schedule demo |
| Pilot candidate | Has real assessment coming soon | Offer Pilot Pack |
| Paid pilot | Will pay or has paid | Onboard and capture evidence |
| Referral source | Not a buyer but knows buyers | Ask for introductions |

## Privacy And Consent

Customer discovery must be evidence-ready without exposing private educational data unnecessarily.

Rules:

- Ask permission before using names or testimonials publicly.
- Keep student data out of discovery notes unless strictly necessary.
- For hackathon evidence, store customer contact information securely.
- Separate public testimonial text from private contact evidence.
- Do not publish student submissions or grades without explicit permission.
- Mark related-party relationships honestly.

## Discovery Conclusion

Customer discovery is successful only if it produces business decisions.

The expected decision after discovery is one of:

1. sell the Pilot Pack to the strongest segment;
2. narrow the ICP further;
3. adjust the offer;
4. adjust the pricing unit;
5. delay features that do not help paid pilots;
6. reject assumptions that did not survive customer evidence.


---

## Source: `01-business/go-to-market.md`

# Go-To-Market

GradeOps AI should enter the market through founder-led sales, paid pilots, and proof-heavy educator outreach.

The first go-to-market objective is not broad brand awareness. It is to generate real conversations, real pilots, real usage, real revenue, and evidence for the hackathon submission.

## GTM Thesis

The fastest path to business evidence is:

> Sell a guided assessment-operations pilot to programming educators who already have an upcoming assessment and feel grading/feedback pressure.

This avoids slow institutional procurement and keeps the offer concrete.

## Initial Market Wedge

| Attribute | Focus |
| --- | --- |
| Domain | Programming education |
| Assessment type | Practical programming assessments |
| Customer type | Independent teachers, tutors, bootcamps, small academies |
| Buyer size | Small enough to approve a pilot quickly |
| First offer | Pilot Pack |
| Core CTA | Run your next programming assessment with AI agents |

## Positioning

GradeOps AI is not a quiz generator.

It is:

> An assessment operations layer where AI agents help create assessments, generate rubrics, analyze submissions, draft feedback, detect learning gaps, and prepare teacher reports while teachers stay in control.

## Entry Offer

### Pilot Pack

| Item | Definition |
| --- | --- |
| Price | US$99 one-time, or CLP equivalent for LatAm testing |
| Scope | 3 programming assessments |
| Volume | Up to 150 graded submissions |
| Included | Onboarding, assessment setup, rubric, grading assistance, feedback drafts, learning-gap report, teacher approval, evidence dashboard |
| Goal | Revenue, testimonial, usage logs, cost data, and workflow validation |

The Pilot Pack should be sold before the product is fully self-serve if necessary. Early guided operation is acceptable as long as AI-agent execution and product evidence are real.

## Target Personas

| Persona | Message |
| --- | --- |
| Independent teacher | Save hours grading and generate better feedback without changing how you teach |
| Tutor | Look more professional and give each student more actionable feedback |
| Bootcamp instructor | Process cohort submissions faster and detect learning gaps before the next module |
| Small academy founder | Standardize assessment quality without hiring academic operations staff |
| Program manager | Get visibility into cohort performance and grading consistency |

## Channel Strategy

### Primary Channels

| Channel | Why It Fits | Action |
| --- | --- | --- |
| Existing educator network | Highest trust and fastest conversations | Ask directly for pilot candidates |
| LinkedIn | Good for teachers, tutors, founders, bootcamp people | Founder posts + direct outreach |
| Programming education communities | Domain-specific and pain-aligned | Share problem/offer, not generic promo |
| Referrals | Warm trust path | Ask each interviewee for 2 names |
| Hackathon visibility | Credibility and urgency | Convert attention into demos/pilots |

### Secondary Channels

- local tech communities;
- teaching communities;
- bootcamp alumni networks;
- Discord/Slack groups for educators;
- newsletter/community posts;
- short demo clips.

Avoid paid ads at the beginning unless the message has already converted in direct outreach.

## Sales Motion

### Step 1: Identify

Find educators with a near-term assessment.

Target signal examples:

- teaches programming;
- has a cohort;
- posts about education or coding;
- runs a bootcamp or academy;
- mentions grading, feedback, assignments, or student projects;
- teaches Java, Python, JavaScript, web, mobile, algorithms, or intro programming.

### Step 2: Start Conversation

Do not lead with “AI platform”.

Lead with the pain:

> I am validating GradeOps AI, a workflow that helps programming teachers run assessments with AI agents while keeping final approval. I am looking for educators who have an upcoming assessment and want to reduce grading/feedback workload. Would you be open to a 15-minute conversation?

### Step 3: Discover

Use the discovery script. Capture workflow, volume, pain, trust, and buying signals.

### Step 4: Demo

Show a real workflow:

1. teacher enters learning goal;
2. agents create assessment and rubric;
3. sample submission is analyzed;
4. feedback is drafted;
5. teacher approves;
6. report and agent logs are shown.

### Step 5: Offer Pilot

Offer the Pilot Pack only when pain and timing are clear.

> For the pilot, we can operate your next 3 assessments with AI agents, up to 150 graded submissions, with teacher approval before anything reaches students.

### Step 6: Capture Evidence

Every pilot should produce:

- payment or commitment evidence;
- assessment run;
- submission count;
- feedback count;
- agent log events;
- time-saved estimate;
- testimonial or quote;
- objections and next-step intent.

## Outreach Messages

### LinkedIn DM

```text
Hola {Name}, estoy construyendo GradeOps AI para docentes de programación.

La idea es simple: operar evaluaciones prácticas con agentes IA — actividad, rúbrica, corrección asistida, feedback y reporte — pero manteniendo al docente con aprobación final.

Estoy hablando con profesores/tutores/bootcamps que tengan evaluaciones próximas. ¿Te puedo hacer 4-5 preguntas sobre tu flujo actual de corrección y feedback?
```

### Follow-Up After Interview

```text
Gracias por la conversación, {Name}.

Lo que entendí:
- Tu mayor carga está en {pain}.
- Hoy resuelves esto con {currentWorkflow}.
- Lo más importante para confiar sería {trustRequirement}.

El piloto que calza sería:
3 evaluaciones reales, hasta 150 entregas, rúbrica, corrección asistida, feedback individual, reporte docente y aprobación final antes de entregar nada a estudiantes.

¿Tiene sentido probarlo con tu próxima evaluación?
```

### Pilot Ask

```text
Para hacerlo serio y medir valor real, lo estoy ofreciendo como Pilot Pack.

Incluye 3 evaluaciones, hasta 150 entregas, onboarding, reporte y evidencia de tiempo ahorrado.

Precio piloto: US$99 o equivalente local.

Si lo tomamos, dejamos documentado:
- tiempo estimado antes/después;
- feedback del docente;
- costos de operación;
- resultados del flujo.
```

## Landing Page Message

### Hero

```text
Run your next programming assessment with AI agents.
```

### Subheadline

```text
GradeOps AI helps programming educators create assessments, generate rubrics, analyze submissions, draft feedback, detect learning gaps, and prepare teacher reports — with teachers in control.
```

### CTA

```text
Run my next assessment
```

### Secondary CTA

```text
Book a 15-minute discovery call
```

### Proof Blocks

- Save grading and feedback time.
- Keep teacher approval.
- Get structured rubrics and reports.
- Track agent logs, cost, and evidence.
- Built for programming educators, tutors, bootcamps, and small academies.

## Funnel Metrics

| Stage | Target |
| --- | ---: |
| Outreach messages | 50-100 |
| Discovery calls | 10-20 |
| Demo calls | 5-10 |
| Pilot candidates | 5+ |
| Paid pilots or commitments | 3+ |
| Real/semi-real assessments | 5+ |
| Submissions processed | 100+ |
| Testimonials | 1-3 |

## Weekly GTM Plan

### Week 1: Message And List

- Finalize landing copy.
- Build list of 50 target educators.
- Prepare discovery script.
- Publish first founder post.
- Send 20 direct outreach messages.

### Week 2: Discovery And Demo

- Complete 10 interviews.
- Run 3-5 demos.
- Identify strongest segment.
- Refine Pilot Pack wording.
- Capture objections.

### Week 3: First Paid Pilots

- Close 1-3 paid pilots or strong commitments.
- Process first real/semi-real assessments.
- Capture usage, cost, and testimonial evidence.

### Week 4: Repeatable Motion

- Turn first pilot into case study.
- Ask for referrals.
- Improve onboarding.
- Create short demo clip.
- Run second outreach wave.

### Final Hackathon Weeks

- Prioritize evidence over new channels.
- Package customer stories.
- Show revenue/cost proof.
- Prepare English submission narrative.
- Record demo with business proof.

## Objection Handling

| Objection | Response |
| --- | --- |
| I do not trust AI grading | The AI suggests; the teacher approves. Nothing student-facing is delivered without review. |
| My assessments are too specific | The workflow starts from your learning goal, rubric, and context. The pilot uses your real assessment style. |
| I already use ChatGPT | GradeOps AI is structured: rubrics, submissions, feedback, reports, logs, approval states, and cost evidence. |
| I do not want a new LMS | GradeOps AI is not an LMS. It operates the assessment workflow and can coexist with current tools. |
| I cannot pay yet | We can run discovery, but paid pilots are prioritized because the goal is validating real business value. |
| Student privacy matters | The pilot should use minimal necessary data and avoid sensitive personal data whenever possible. |

## Content Strategy

Keep content practical and evidence-based.

Recommended post themes:

- “Why AI quiz generators miss the real problem.”
- “The hardest part of teaching programming is not explaining loops; it is giving useful feedback at scale.”
- “Teachers should not be replaced by AI. They should approve better prepared work.”
- “What we learned after processing X programming submissions with AI agents.”
- “From learning goal to rubric, feedback, and report.”

## Referral Motion

After every interview or pilot, ask:

> Do you know 2 programming educators who regularly grade practical assignments and might be open to a short conversation?

Referral tracking fields:

- referrer;
- referred contact;
- segment;
- intro status;
- interview status;
- pilot status;
- related-party flag.

## GTM Risks

| Risk | Mitigation |
| --- | --- |
| Too much generic AI messaging | Lead with assessment workload and teacher control |
| Selling to slow institutions first | Start with direct buyers |
| Free users consume time | Cap free usage and prioritize paid pilots |
| No proof of willingness to pay | Ask for payment or signed pilot commitment early |
| Demo becomes too technical | Show business outcome, agent logs, and evidence |
| Spanish-only assets limit submission value | Prepare English landing/demo/submission copy early |

## GTM Conclusion

The go-to-market motion should be narrow, direct, and evidence-driven.

GradeOps AI wins early if it can show:

1. a clear buyer;
2. a painful recurring workflow;
3. a simple paid pilot;
4. a real AI-operated assessment run;
5. teacher approval and trust;
6. measurable time/value;
7. revenue and cost evidence.


---

## Source: `01-business/hackathon-strategy.md`

# Business Hackathon Strategy

This document translates the Build with Gemini XPRIZE requirements into a business execution plan for `01-business`.

The strategic hackathon interpretation is already defined in `../00-project/hackathon-strategy.md`. This file focuses on how the business side will generate and package evidence.

## Business Objective

GradeOps AI must be presented as a real business, not only as a product prototype.

The business case must prove:

1. real educators have a painful recurring assessment workflow;
2. GradeOps AI operates meaningful parts of that workflow with AI agents;
3. teachers remain in control;
4. customers show willingness to pay;
5. the business tracks revenue, cost, usage, and agent evidence;
6. the model can become sustainable beyond the hackathon.

## Required Business Story

The story for judges:

> Programming educators lose time creating assessments, reviewing code, writing feedback, and preparing reports. GradeOps AI gives them AI-operated assessment capacity. Agents generate assessments, rubrics, grading suggestions, feedback drafts, learning-gap analysis, recovery activities, and teacher reports. Teachers approve important outputs. The business tracks real users, revenue, costs, agent logs, and customer evidence.

## Judging Criteria: Business Interpretation

| Criterion | Business Proof Needed | GradeOps AI Evidence |
| --- | --- | --- |
| Business Viability | Real users, real revenue, sustainable model | Paid pilots, subscription pricing, revenue ledger, cost model, customer testimonials |
| AI-Native Operations | AI live in production executing key decisions | Agent logs, model/API usage, approval states, workflow dashboard |
| Category Impact | Meaningful improvement in education | Time saved, faster feedback, learning-gap reports, student support evidence |

## Hackathon Evidence Plan

| Evidence Type | Minimum Target | Where It Comes From |
| --- | ---: | --- |
| Educator conversations | 10+ | Customer discovery notes |
| Pilot users | 5+ | Pilot pipeline |
| Paid pilots or commitments | 3+ | Payment records or signed commitments |
| Assessments processed | 5+ | Product usage logs |
| Submissions processed | 100+ | Submission records |
| Feedback outputs | 300+ | Agent output logs |
| Agent log events | 500+ | Agent execution log |
| Testimonials | 1+ strong | Customer feedback |
| Cost data | Every run | Cost ledger |
| Revenue data | Every payment/commitment | Revenue ledger |
| Related-party flags | Every revenue event | Revenue ledger |

## Revenue Evidence

Accepted business evidence should be easy to understand and audit.

Potential evidence:

- Stripe dashboard export;
- bank transfer screenshot;
- invoice or receipt;
- signed pilot commitment;
- manual P&L;
- revenue ledger;
- customer confirmation.

Each revenue event should track:

| Field | Required |
| --- | --- |
| Customer | Yes |
| Amount | Yes |
| Currency | Yes |
| USD equivalent | Yes |
| Date | Yes |
| Month | Yes |
| Offer | Yes |
| Payment method | Yes |
| Evidence link | Yes |
| Related-party flag | Yes |

## Customer Evidence

Customer evidence should be credible but privacy-aware.

Capture:

- customer name;
- email;
- phone if permitted;
- role;
- organization if applicable;
- segment;
- assessment use case;
- testimonial or feedback;
- permission level;
- related-party status.

Permission levels:

| Level | Meaning |
| --- | --- |
| Private evidence only | Can be shown to judges if requested, not public |
| Anonymous public quote | Quote can be used without name |
| Named public quote | Quote can be used with name/role |
| Case study | Customer permits a short public story |

## Agent Evidence

Business proof depends on showing that AI agents operate the workflow.

Each agent event should show:

- timestamp;
- customer/teacher;
- assessment;
- submission if applicable;
- agent name;
- action type;
- model used;
- token estimate;
- cost estimate;
- input summary;
- structured output summary;
- status;
- uncertainty flags;
- teacher approval state;
- final action taken.

The business dashboard should make this visible in the demo.

## Business Dashboard For Demo

The dashboard should show, at minimum:

| Widget | Purpose |
| --- | --- |
| Assessments processed | Product usage |
| Submissions processed | Operational volume |
| Feedback outputs generated | AI workload |
| Agent runs | AI-native operations |
| Approval states | Teacher control |
| Time saved estimate | Customer value |
| AI cost estimate | Unit economics |
| Revenue collected | Business viability |
| Marketing spend | Submission transparency |
| Related-party revenue | Rules transparency |

## 3-Minute Demo Business Arc

The demo must sell the business and prove operation.

| Time | Scene | Business Point |
| --- | --- | --- |
| 0:00-0:20 | Problem | Programming assessment work is repetitive, slow, and hard to scale |
| 0:20-0:40 | Product | GradeOps AI runs assessment operations with AI agents |
| 0:40-1:25 | Workflow | Teacher creates assessment; agents generate rubric, analyze submission, draft feedback |
| 1:25-1:55 | Teacher control | Teacher reviews, edits, approves |
| 1:55-2:20 | AI-native operations | Logs show agents, models, costs, statuses, decisions |
| 2:20-2:45 | Business evidence | Show users, pilots, revenue/commitments, testimonials, costs |
| 2:45-3:00 | Close | Small education providers gain academic operations capacity without hiring |

## Written Narrative Business Points

The 500-1000 word narrative should include:

- why programming assessment workflows are painful;
- what humans do versus what AI agents do;
- why teacher approval is mandatory;
- how the business acquired real users;
- how revenue was generated;
- how costs were measured;
- what jobs/economic opportunities are enabled beyond the founding team;
- why the model can scale beyond the initial pilots.

## Business Claim Discipline

Do not overclaim.

| Avoid Saying | Say Instead |
| --- | --- |
| AI grades students automatically | AI drafts grading suggestions against a rubric; teachers approve |
| We replace manual teaching work | We reduce repetitive assessment operations |
| We are an LMS | We operate the assessment workflow |
| We can serve every subject | We start with programming assessments |
| We have unlimited AI grading | Usage is bounded by assessment and submission volume |
| Revenue proves scale | Revenue proves early willingness to pay |

## Success Targets

### Minimum Credible Submission

- 10 educator interviews;
- 3 pilot commitments;
- 1-3 paid pilots;
- 5 assessment runs;
- 100 submissions processed;
- 500 agent log events;
- cost dashboard;
- one testimonial;
- English video and narrative.

### Strong Submission

- 20 educator interviews;
- 5+ paid pilots or commitments;
- 10+ assessment runs;
- 300+ submissions processed;
- 1,000+ agent log events;
- multiple testimonials;
- clear revenue/cost ledger;
- one short customer story.

## Risk Register

| Risk | Business Impact | Mitigation |
| --- | --- | --- |
| No paid customers | Weak viability | Sell Pilot Pack immediately and track commitments |
| Only related-party revenue | Weak evidence | Separate it and prioritize arms-length customers |
| Demo lacks real usage | Looks like prototype | Process real/semi-real assessments before recording |
| AI logs are hidden | Weak AI-native proof | Build dashboard early |
| Costs are not tracked | Weak unit economics | Log tokens, models, cost, and payment fees |
| Teacher trust is weak | Adoption risk | Keep approval states central |
| Narrative is too technical | Judges miss business value | Lead with pain, revenue, users, evidence |

## Final Submission Checklist

| Item | Status |
| --- | --- |
| GitHub repository ready |
| Testing instructions in English |
| 3-minute video recorded |
| Written narrative 500-1000 words |
| Revenue evidence exported |
| Revenue by month prepared |
| Related-party revenue separated |
| Total costs prepared |
| Marketing/customer acquisition spend prepared |
| Agent logs exported or screenshotted |
| API usage evidence prepared |
| Dashboard screenshots prepared |
| Customer evidence prepared |
| Testimonials approved |
| Google Cloud usage visible |
| Gemini API usage visible |
| Pre-existing templates/boilerplate disclosed if used |

## Business Hackathon Conclusion

The hackathon business strategy is simple:

> Build the narrowest workflow that can process real programming assessments, sell it as a paid pilot, and capture enough evidence to prove GradeOps AI is an AI-operated assessment business with real demand, real usage, real costs, and teacher-controlled value.


---

## Source: `01-business/pricing.md`

# Pricing

GradeOps AI pricing must validate business value while protecting margins from unbounded AI usage.

The pricing model is based on assessment operations and graded student submissions, not unlimited access.

## Pricing Principles

- Price by value and usage volume, not only API cost.
- Never sell unlimited AI grading.
- Keep plans simple enough for a hackathon demo.
- Make the first paid offer easy to buy.
- Use a paid pilot to validate willingness to pay.
- Track cost per assessment, graded student submission, active teacher, and customer.
- Separate free-tier/credit benefits from real unit economics.
- Separate related-party revenue from arms-length revenue.

## Definition Of Graded Submission

A **graded submission** is the unit consumed by the plans.

It means:

> One student answer, attempt, code file, pasted response, or delivered work item processed by the AI-assisted grading and feedback workflow.

It does **not** mean a student account.

Examples:

| Scenario | Counted Usage |
| --- | ---: |
| 30 students submit 1 answer each | 30 graded submissions |
| 10 students submit 3 exercises each | 30 graded submissions |
| 1 student submits 2 attempts and both are analyzed | 2 graded submissions |
| Teacher creates an assessment but no answers are analyzed | 0 graded submissions |

For MVP pricing, student login is not required. The teacher can upload or paste student responses. The cost driver is the number and size of responses processed, not the number of registered learners.

## Business Unit

Primary unit:

> 1 assessment = activity + rubric + grading assistance for 30 student submissions + personalized feedback + teacher report.

Primary cost drivers:

- number of submissions;
- length/complexity of submissions;
- model routing;
- retries/failures;
- premium fallback usage;
- teacher report generation;
- storage/logging;
- support/onboarding time.

## Recommended Public Pricing

| Plan | Price | Included Usage | Best For |
| --- | ---: | --- | --- |
| Free | US$0 | 1 assessment / 30 graded submissions | Controlled demo and lead capture |
| Teacher Lite | US$12/month | 3 assessments / 90 graded submissions | Tutor or low-volume educator |
| Teacher Pro | US$29/month | 10 assessments / 300 graded submissions | Main individual teacher plan |
| Cohort Pro | US$79/month | 30 assessments / 1,000 graded submissions | Bootcamps, tutors, small academies |
| Pilot Pack | US$99 one-time | 3 real assessments / up to 150 graded student submissions / onboarding | Best hackathon revenue offer |

## LatAm / Chile Testing Prices

These prices can be tested locally while reporting hackathon revenue in USD equivalent.

| Plan | Suggested CLP Price |
| --- | ---: |
| Teacher Lite | $9.990 CLP/month |
| Teacher Pro | $19.990-$24.990 CLP/month |
| Cohort Pro | $59.990-$79.990 CLP/month |
| Pilot Pack | $39.990-$79.990 CLP one-time |

For hackathon validation, the Pilot Pack matters more than perfect subscription optimization.

## Offer Details

### Free

Purpose:

- product trial;
- demo lead capture;
- controlled usage;
- avoid uncontrolled AI spend.

Limits:

- 1 assessment;
- 30 graded submissions;
- basic report;
- no premium fallback by default;
- watermark or “trial” positioning if needed.

### Teacher Lite

Purpose:

- low-friction paid entry;
- tutors and occasional instructors.

Limits:

- 3 assessments;
- 90 graded submissions;
- basic reports;
- standard model routing;
- email support only.

### Teacher Pro

Purpose:

- main individual plan;
- recurring programming educators.

Limits:

- 10 assessments;
- 300 graded submissions;
- feedback drafts;
- learning-gap reports;
- exportable summaries;
- priority feature access during pilot.

### Cohort Pro

Purpose:

- small academy, bootcamp, cohort program.

Limits:

- 30 assessments;
- 1,000 graded submissions;
- cohort reporting;
- multiple courses/cohorts if MVP supports it;
- priority support;
- exportable reports.

### Pilot Pack

Purpose:

- fastest path to real revenue and testimonials;
- guided onboarding;
- hackathon business evidence.

Includes:

- 3 real programming assessments;
- up to 150 graded submissions;
- onboarding call;
- assessment/rubric setup;
- grading assistance;
- feedback drafts;
- learning-gap report;
- teacher approval workflow;
- short value report;
- testimonial request if successful.

## Overuse Pricing

| Extra Usage | Suggested Price |
| --- | ---: |
| Additional graded submission | US$0.08 |
| Additional assessment without submissions | US$0.50 |
| Additional assessment with up to 30 submissions | US$3.00 |
| Additional advanced report | US$1.00 |
| Premium model review | US$0.20-US$0.50 per submission |

Overuse should be logged and visible to the customer before it becomes a billing surprise.

## Margin Logic

Gross margin formula:

```text
Gross margin =
(Revenue - AI runtime - cloud runtime - storage/logging - payment fees - support allocation) / Revenue
```

Minimum planning targets:

| Offer | Target Gross Margin |
| --- | ---: |
| Free | Negative or break-even, capped hard |
| Teacher Lite | 70%+ |
| Teacher Pro | 75%+ |
| Cohort Pro | 70%+ |
| Pilot Pack | 60%+ after onboarding/support time |

The Pilot Pack can have lower margin because it generates evidence, testimonials, workflow learning, and revenue proof.

## Example Margin Thinking

If a 30-submission assessment costs roughly US$0.50-US$1.20 in AI usage with efficient routing, the technical AI cost is not the main price anchor.

The price anchor is customer value:

- hours saved;
- feedback consistency;
- faster student support;
- report generation;
- lower need for additional academic operations labor;
- trust and auditability.

However, technical costs still matter because long code submissions, retries, premium fallbacks, and support time can change margins quickly.

## Pricing Validation Questions

Ask during discovery:

- How often do you run practical programming assessments?
- How many submissions do you usually review?
- How many hours does grading/feedback take?
- What would saving 3-5 hours per assessment be worth?
- Would you rather pay per assessment, per month, or per submission volume?
- Is a guided Pilot Pack easier to approve than a subscription?
- Which price feels too cheap to trust?
- Which price feels expensive but possible?
- Which price is clearly too expensive?
- Who would approve payment?

## Pricing Experiments

| Experiment | Purpose | Success Signal |
| --- | --- | --- |
| Pilot Pack at US$99 | Validate paid willingness quickly | 3+ paid pilots or commitments |
| CLP Pilot Pack | Validate local market affordability | 3+ local paid pilots or strong commitments |
| Teacher Pro at US$29 | Validate recurring individual plan | 2+ customers willing to continue |
| Cohort Pro at US$79 | Validate small-team value | 1 academy/bootcamp serious conversation |
| Overuse pricing | Validate usage-bounded model | Customers accept submission caps |

## Discount Policy

Discounts should not destroy signal quality.

Allowed:

- early adopter discount;
- local market price testing;
- founder-led pilot discount;
- education/community discount;
- limited-time hackathon pilot price.

Avoid:

- unlimited lifetime deals;
- free unlimited pilots;
- hidden discounts that make revenue evidence unclear;
- discounts without written scope limits;
- free work for related parties counted as commercial traction.

Always record:

- list price;
- actual paid price;
- reason for discount;
- whether the customer is related-party;
- whether the payment is arms-length.

## Payment And Reporting

For each payment or commitment, record:

| Field | Required |
| --- | --- |
| Customer ID | Yes |
| Customer segment | Yes |
| Offer | Yes |
| List price | Yes |
| Actual amount | Yes |
| Currency | Yes |
| USD equivalent | Yes |
| Date | Yes |
| Month | Yes |
| Payment method | Yes |
| Processing fee | If known |
| Related-party flag | Yes |
| Evidence link | Yes |

## Pricing Risks

| Risk | Why It Matters | Mitigation |
| --- | --- | --- |
| Unlimited usage | Can destroy margins | Use assessment/submission caps |
| Too-low price | Weakens business viability signal | Price against value saved |
| Too-high first offer | Blocks early validation | Use Pilot Pack |
| Pricing based only on API cost | Underprices support, trust, and operations | Include support, onboarding, evidence, and value |
| Related-party payments inflate traction | Weak judge confidence | Separate and disclose |
| Local CLP pricing conflicts with USD reporting | Confusing evidence | Store original currency and USD equivalent |

## Current Pricing Decision

For the hackathon period:

1. Lead with **Pilot Pack**.
2. Keep subscription plans visible but secondary.
3. Limit usage by assessments and graded student submissions.
4. Track overuse but avoid aggressive billing friction early.
5. Report revenue, costs, discounts, and related-party status transparently.
6. Use pricing conversations as customer discovery, not only sales.

