# Madan Kumar

**I show buyers how to test AI agents on their own data before they sign, and I design agents that pass the test.**

I am a founding sales engineer for AI and data platforms. I was the founding or early sales engineer at four startups: Coactive AI (multimodal AI), Cutover (runbook orchestration), Imply (real-time analytics on Druid) and Alluxio (data orchestration). Before that, I was a big data consultant at Teradata. I work from Philadelphia and New York.

| Result | Detail |
|---|---|
| **$3.1M** | Largest new logo in Cutover's history: a private bank's disaster-recovery rollout |
| **83%** | Share of North America new-logo revenue I contributed to at Cutover, FY21–23 |
| **38 → 96 of 101** | Real customer queries that an agentic search pilot answered before and after three instruction changes I made. It was 2.2x more precise on archive research. |
| **SE of the Year** | Cutover, FY22 and FY23 |

## Field notes

These are short case studies from customer work, with customer names removed. Each one covers the situation, what I measured, what I decided, the result, and what I tell the next customer.

1. [An agent that went from 38 to 96 of 101 real queries](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md). One failure returned wrong results that looked right.
2. [A 21.5% precision complaint, solved by thresholds](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/02-one-threshold-cannot-fit-all.md). The average hid categories that ranged from 0% to 100%.
3. [Scoping a $3.1M disaster-recovery rollout](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/03-scoping-a-dr-rollout.md). I turned an application inventory into a three-year plan and the company's first services contract.

## Builds

| Repo | What it shows a buyer |
|---|---|
| [video-eval-uncertainty](https://github.com/madankkumar21/video-eval-uncertainty) | I check what a benchmark score measures before I trust it. On a video counting task, three models scored 44–52% with 8 frames and 38–43% with no frames. A rule that always answers "3" scored 41%. I scored 8 of 20 from the same frames. Write-up: [Ask for the no-video score](https://github.com/madankkumar21/video-eval-uncertainty/blob/main/docs/posts/buyer-post.md). |
| [durable-eval-temporal](https://github.com/madankkumar21/durable-eval-temporal) | I test infrastructure the way a customer would before they adopt it. A model-eval harness on Temporal, measured against a plain loop through crashes, hung calls, human approval and deploys in the middle of a run. |
| [bookly-support-agent](https://github.com/madankkumar21/bookly-support-agent) | I design agents that a business can trust with money. The model talks, code owns the refund rules, and the customer confirms. 0 wrong refunds in 80 test conversations. |
| [inference-poc](https://github.com/madankkumar21/inference-poc) | I measure a model-serving stack before I advise on one. A 48-hour inference proof of concept on one GPU. Storing the model weights in 8 bits (FP8 quantization) gave 1.5–1.7x throughput at 1–32 concurrent requests. Reusing a shared prompt prefix (prefix caching) cut the server's wait before the first token from 1,238 ms to 44 ms. |
| [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo) | I test a vendor's claim the way a customer would. One agent task over three ways to give an agent API access, with nine behavior claims checked. For one agent and one task, a hand-built tool matched the graph. |

## Agent design practices

These are the rules I follow when I design an agent that a business can trust. Each rule links to the build or field note that shows it, and the list will change as I learn.

- **The model talks, and code owns the rules.** In [bookly-support-agent](https://github.com/madankkumar21/bookly-support-agent), code owns the refund rules and the customer confirms each refund. The agent made 0 wrong refunds in 80 test conversations.
- **Split tools by risk.** Proposing a change and applying it are separate operations with separate permissions. The agent gets only the safe operation, and a person applies the change. In [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo), the router refused the agent's direct call to apply a budget move.
- **Limit the agent in two places.** The tool server limits the operations it will run, and the token limits the fields the agent can read. In [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo), 0 personal-data values reached the model.
- **Describe every data field before you turn the agent on.** In [field note 01](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md), an agent dropped filters on fields that had no description. It still returned results that looked right.
- **Check the AI grader against people before you trust its grades.** In [field note 01](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md), a blind AI grader agreed with human reviewers 97% of the time.
- **Test the agent through failures as well as clean runs.** [durable-eval-temporal](https://github.com/madankkumar21/durable-eval-temporal) runs the test through crashes, hung calls, human approval and deploys in the middle of a run.

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
