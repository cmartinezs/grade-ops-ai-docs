# Cost Model

GradeOps AI must be priced and operated as a measurable business, not as a free AI demo.

The hackathon rewards real revenue, real users, AI-native operations, and business viability. That means the product must track unit economics from the first MVP: token usage, model routing, cloud runtime, payment fees, revenue, marketing spend, and related-party revenue.

## Canonical Cost Principles

- Do not assume Google Cloud or Gemini usage is free.
- Use credits and free tiers to reduce short-term cash burn, not to define pricing.
- Price by usage volume, especially graded submissions.
- Never sell unlimited AI corrections.
- Separate product operating costs from personal AI development tooling.
- Track cost per agent run, assessment, graded submission, active teacher, and customer.
- Report marketing and customer acquisition spend separately, even if it is zero.

## Required Hackathon Reporting

Devpost requires evidence around both revenue and costs. GradeOps AI should be ready to report:

| Reporting Item | GradeOps AI Interpretation |
| --- | --- |
| Total Revenue | Arms-length third-party revenue earned during the hackathon period, in USD. |
| Revenue by Month | Revenue broken out for May, June, July, and August 2026. |
| Total Costs | Product and development costs incurred during the hackathon period, excluding marketing and customer acquisition spend. |
| Marketing and Customer Acquisition Spend | Paid acquisition, ads, outreach tools, campaign spend, or `US$0` if no paid spend was used. |
| Related-Party Revenue | Revenue from team members, family, related entities, or pre-existing customer relationships, reported separately. |
| Product Evidence | Agent execution logs, API usage records, dashboards, screenshots, and production evidence. |

Sources:

- Devpost rules: https://xprize.devpost.com/rules
- Devpost challenge page: https://xprize.devpost.com/

## Product Operating Costs

These costs affect unit economics and should be tracked as product runtime or product operations.

| Cost Area | Track As | Notes |
| --- | --- | --- |
| Gemini API / Vertex AI | AI API usage | Track model, input tokens, output tokens, retries, and estimated cost. |
| Cloud Run | Hosting/backend execution | Good default for API and agent workers. |
| Firestore or Cloud SQL | Database | Store users, assessments, submissions, rubrics, reports, and logs. |
| Cloud Storage | File storage | Store uploaded code files, exports, and artifacts. |
| Cloud Logging / Monitoring | Observability | Keep technical logs; store agent business logs in DB too. |
| Email provider | Product communication | Transactional notifications and pilot communication. |
| Payment processor | Payment fees | Stripe, PayPal, MercadoPago, Flow, Transbank, or equivalent. |
| Domain | Product/domain cost | Small but should be reported. |
| Contractors | Contractor fees | Only if used. |

## AI Development Tooling

Personal subscriptions can accelerate development but should not be used as runtime infrastructure.

| Tool | Correct Use | Reporting Treatment |
| --- | --- | --- |
| Google AI Pro | Ideation, prototyping, AI Studio, Antigravity, development support. | Pre-existing AI development tooling; note any credits used. |
| Claude Code Pro | Implementation, refactor, debugging, architecture. | Allocated AI development tooling if counted. |
| ChatGPT Plus / Codex | Product design, code review, docs, coding support. | Allocated AI development tooling if counted. |
| GitHub Copilot Pro teacher benefit | IDE productivity. | Free verified teacher benefit, `US$0` cash cost if applicable. |
| OpenCode + free models | Low-cost local/CLI coding support. | Free/open tooling, `US$0` cash cost. |

Runtime rule:

> Personal AI subscriptions accelerate construction; the deployed product must use traceable API/cloud billing.

Do not run production grading through personal ChatGPT, Claude, Gemini web, or AI Studio sessions. The production path must use Gemini API or Vertex AI from the deployed backend and log each agent execution.

## Unit Of Business

Primary unit:

> 1 assessment = activity + rubric + grading assistance for 30 submissions + personalized feedback + teacher report.

Estimated token budget per 30-student assessment:

| Operation | Estimated Input Tokens | Estimated Output Tokens |
| --- | ---: | ---: |
| Create activity + rubric | 15,000 | 8,000 |
| Validate rubric | 10,000 | 2,000 |
| Grade 30 submissions | 480,000 | 150,000 |
| Final teacher report | 40,000 | 8,000 |
| **Total** | **545,000** | **168,000** |

Working cost estimate:

- with efficient routing, a 30-student assessment should usually cost about **US$0.50-US$1.20** in AI usage;
- if every step uses a higher-cost model, the same assessment can approach **US$3.00** in AI usage;
- budget extra for retries, long submissions, logs, failed calls, and premium fallbacks.

## Model Routing Policy

Use cheaper models for high-volume tasks and stronger models where quality matters most.

| Workload | Default Model Policy | Rationale |
| --- | --- | --- |
| Assessment generation | Gemini Flash-class model | Quality matters; moderate volume. |
| Rubric generation | Gemini Flash-class model | Needs consistent structure and pedagogy. |
| Rubric validation | Gemini Flash-class model | Needs reasoning and calibration. |
| Bulk grading | Gemini Flash-Lite-class model | Highest volume; cost control matters. |
| Individual feedback | Flash-Lite by default; Flash fallback | High volume with occasional quality escalation. |
| Teacher report | Gemini Flash-class model | Lower volume; quality matters. |
| Complex cases | Premium fallback only | Avoid premium models for default volume. |

Prices change. Before launch and submission, verify current pricing on the official Gemini API pricing page:

- https://ai.google.dev/gemini-api/docs/pricing

Also verify the Google Cloud runtime pricing pages before final submission:

- Cloud Run pricing: https://cloud.google.com/run/pricing
- Firestore pricing: https://cloud.google.com/firestore/pricing
- Cloud Storage pricing: https://cloud.google.com/storage/pricing

## Initial Pricing

Pricing should reflect teacher value and usage volume, not only API cost.

| Plan | Price | Included Usage | Purpose |
| --- | ---: | --- | --- |
| Free | US$0 | 1 assessment / 30 submissions | Controlled demo and lead capture. |
| Teacher Lite | US$12/month | 3 assessments / 90 submissions | Entry-level paid plan. |
| Teacher Pro | US$29/month | 10 assessments / 300 submissions | Main individual teacher plan. |
| Cohort Pro | US$79/month | 30 assessments / 1,000 submissions | Bootcamps, tutors, and small academies. |
| Pilot Pack | US$99 one-time | 3 real assessments / up to 150 submissions / onboarding | Best hackathon revenue offer. |

For Chile/LatAm testing:

| Plan | Suggested CLP Price |
| --- | ---: |
| Teacher Lite | $9.990 CLP/month |
| Teacher Pro | $19.990-$24.990 CLP/month |
| Cohort Pro | $59.990-$79.990 CLP/month |
| Pilot Pack | $39.990-$79.990 CLP one-time |

## Overuse Policy

Do not sell unlimited AI corrections.

Recommended overuse pricing:

| Extra Usage | Suggested Price |
| --- | ---: |
| Additional graded submission | US$0.08 |
| Additional assessment without submissions | US$0.50 |
| Additional assessment with up to 30 submissions | US$3.00 |
| Additional advanced report | US$1.00 |
| Premium model review | US$0.20-US$0.50 per submission |

## Cost Dashboard Requirements

The MVP should include an internal dashboard that tracks:

- input tokens by agent;
- output tokens by agent;
- model used by agent;
- estimated cost per agent execution;
- retries and failed calls;
- cost per assessment;
- cost per graded submission;
- cost per teacher;
- revenue by customer;
- revenue by month;
- marketing spend;
- payment fees;
- costs covered by credits;
- cash costs actually paid;
- related-party revenue separated from arms-length revenue.

## Initial Operating Budget

For the hackathon period, budget conservatively:

| Scenario | Expected Monthly Runtime Cost |
| --- | ---: |
| Controlled MVP | US$26-US$175 |
| Recommended planning buffer | US$150-US$250 |
| Serious pilot | US$165-US$695 |

Recommended cash reserve for the hackathon:

> US$500-US$1,000, excluding the value of founder time.

## Final Rule

Charge for value and usage volume, not for how cheaply the MVP was built.

GradeOps AI should be able to say:

> We know what every assessment, correction, agent run, and customer costs. This is a measurable AI-operated business, not a demo.
