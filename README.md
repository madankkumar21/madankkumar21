# Madan Kumar

**Founding sales engineer for AI and data platforms.** I build the pilots and evals that take enterprise deals from first call to production.

I was the founding or early sales engineer at four startups: Coactive AI (multimodal AI), Cutover (runbook orchestration), Imply (real-time analytics on Druid) and Alluxio (data orchestration). Before that, I was a big data consultant at Teradata. I work from Philadelphia and New York.

| Result | Detail |
|---|---|
| **$3.1M** | Largest new logo in Cutover's history: a private bank's disaster-recovery rollout |
| **83%** | Share of North America new-logo revenue I contributed to at Cutover, FY21–23 |
| **Pilot → production** | An agentic search pilot I designed and debugged went to production: 2.2x more precise on archive research |
| **SE of the Year** | Cutover, FY22 and FY23 |

## Field notes

These are short case studies from customer work, with customer names removed. Each one covers the situation, what I measured, what I decided, the result, and what I tell the next customer.

1. [An agent pilot that went to production](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md). The agent answered 38 of 101 real queries on the first run and 96 after three instruction changes. One failure returned wrong results that looked right.
2. [A 21.5% precision complaint, solved by thresholds](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/02-one-threshold-cannot-fit-all.md). The average hid categories that ranged from 0% to 100%.
3. [Scoping a $3.1M disaster-recovery rollout](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/03-scoping-a-dr-rollout.md). I turned an application inventory into a three-year plan and the company's first services contract.

## Builds

| Repo | What it shows a buyer |
|---|---|
| [durable-eval-temporal](https://github.com/madankkumar21/durable-eval-temporal) | I test infrastructure the way a customer would before they adopt it. A model-eval harness on Temporal, measured against a plain loop through crashes, hung calls, human approval and deploys in the middle of a run. |
| [bookly-support-agent](https://github.com/madankkumar21/bookly-support-agent) | I design agents that a business can trust with money. The model talks, code owns the refund rules, and the customer confirms. 0 wrong refunds in 80 test conversations. |

## How I run a deal

- **Qualify before I build.** Sales engineering (SE) effort grows in tiers. A custom demo needs a named owner and date for the next decision. A pilot needs the customer's data in hand and success criteria in writing.
- **Agree on the win before the pilot.** I fix the success criteria with the buyer before the first run, so the result answers a question that the buyer already asked.
- **Measure the base rate before I accept a precision target.** The base rate is how often the target class occurs in the data. Some targets are out of reach for any vendor at that rate, and I find that out first.
- **Evaluate on the customer's data, graded on the customer's labels.** A public benchmark does not tell a buyer how the system works on their content.
- **Decide where human review stays.** The agent does the repeatable work. Publishing, refunds and other steps that cannot be undone need a person's approval.
- **Turn field findings into product work.** Each failure I diagnose becomes a runbook for the next customer or a backlog item for product.

## What I work with

Agents and evals (Claude Code, MCP servers, LLM and VLM judges, confidence intervals, threshold calibration) · multimodal AI (vision-language models, video and image classification) · data platforms (Spark, Druid, Presto, Databricks, OpenSearch, PostgreSQL) · AWS (Certified Solutions Architect) · Python and SQL.

## Contact

[LinkedIn](https://www.linkedin.com/in/madan-kumar-a7679a74) · madan.k.kumar21@gmail.com · Resume on request
