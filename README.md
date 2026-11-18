# Madan Kumar

**Notes and open tools on testing AI agents: how to set pass criteria, measure the results, and build agents that meet them.**

For about ten years I was an early sales engineer at AI and data startups. Most of that work was running evaluations with teams on their own data. This page collects what I learned from it: field notes from real evaluations, small open builds that each test one question, and the agent design practices I follow. The builds use public or synthetic data and are MIT licensed. Corrections and counter-examples are welcome.

Background: Coactive AI, Cutover, Imply, Alluxio and Teradata.

## Field notes

Lessons from real evaluations, with company names removed. Each note covers the situation, what I measured, what I decided, the result, and what I would tell the next team.

1. [An agent that went from 38 to 96 of 101 real queries](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md). One failure returned wrong results that looked right.
2. [One threshold cannot fit every category](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/02-one-threshold-cannot-fit-all.md). An average precision of 21.5% hid categories that ranged from 0% to 100%.

## Builds

| Repo | What it explores |
|---|---|
| [video-eval-uncertainty](https://github.com/madankkumar21/video-eval-uncertainty) | What a video benchmark score measures. On a counting task, three models scored 44–52% with 8 frames and 38–43% with no frames. A rule that always answers "3" scored 41%. A person scored 8 of 20 from the same frames. Write-up: [Ask for the no-video score](https://github.com/madankkumar21/video-eval-uncertainty/blob/main/docs/posts/buyer-post.md). |
| [durable-eval-temporal](https://github.com/madankkumar21/durable-eval-temporal) | An eval harness that keeps going through failures. It runs on Temporal and is compared with a plain loop through crashes, hung calls, human approval and deploys in the middle of a run. |
| [bookly-support-agent](https://github.com/madankkumar21/bookly-support-agent) | A support agent that handles money safely. The model talks, code owns the refund rules, and the customer confirms. 0 wrong refunds in 80 test conversations. |
| [inference-poc](https://github.com/madankkumar21/inference-poc) | A 48-hour model-serving test on one GPU. Storing the model weights in 8 bits (FP8 quantization) gave 1.5–1.7x throughput at 1–32 concurrent requests. Reusing a shared prompt prefix (prefix caching) cut the server's wait before the first token from 1,238 ms to 44 ms. |
| [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo) | Three ways to give an agent API access, with nine behavior claims checked. For one agent and one task, a hand-built tool matched the graph layer. |

## Agent design practices

These are the rules I follow when I design an agent that people can trust. Each rule links to the build or note that shows it. The list will change as I learn, and I welcome counter-examples.

- **The model talks, and code owns the rules.** In [bookly-support-agent](https://github.com/madankkumar21/bookly-support-agent), code owns the refund rules and the customer confirms each refund. The agent made 0 wrong refunds in 80 test conversations.
- **Split tools by risk.** Proposing a change and applying it are separate operations with separate permissions. The agent gets only the safe operation, and a person applies the change. In [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo), the router refused the agent's direct call to apply a budget move.
- **Limit the agent in two places.** The tool server limits the operations it will run, and the token limits the fields the agent can read. In [agent-ready-apollo](https://github.com/madankkumar21/agent-ready-apollo), 0 personal-data values reached the model.
- **Describe every data field before you turn the agent on.** In [field note 01](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md), an agent dropped filters on fields that had no description. It still returned results that looked right.
- **Check the AI grader against people before you trust its grades.** In [field note 01](https://github.com/madankkumar21/madankkumar21/blob/main/field-notes/01-agent-pilot-to-production.md), a blind AI grader agreed with human reviewers 97% of the time.
- **Test the agent through failures as well as clean runs.** [durable-eval-temporal](https://github.com/madankkumar21/durable-eval-temporal) runs the test through crashes, hung calls, human approval and deploys in the middle of a run.

## How I run an evaluation

- **Agree on the pass criteria before the first run.** Write them down with the people who will use the result. Then the result answers a question that they already asked.
- **Measure the base rate before you accept a precision target.** The base rate is how often the target class occurs in the data. At a low base rate, some targets are out of reach for any system.
- **Evaluate on your own data, graded on your own labels.** A public benchmark does not tell you how a system works on your content.
- **Decide where human review stays.** The agent does the repeatable work. Publishing, refunds and other steps that cannot be undone need a person's approval.
- **Turn each failure into a check.** A failure that I diagnose becomes a step that the next evaluation runs first.

## What I work with

Agents and evals (Claude Code, MCP servers, LLM and VLM judges, confidence intervals, threshold calibration) · multimodal AI (vision-language models, video and image classification) · data platforms (Spark, Druid, Presto, Databricks, OpenSearch, PostgreSQL) · AWS (Certified Solutions Architect) · Python and SQL.

## Contact

[LinkedIn](https://www.linkedin.com/in/madan-kumar-a7679a74) · madan.k.kumar21@gmail.com · Questions and corrections are welcome.
