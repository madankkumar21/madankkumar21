# An agent pilot that went to production

**Customer:** a global news agency, already a customer. **My role:** founding sales engineer at Coactive AI.

## Situation

The customer already ran semantic search in production on their archive. Semantic search matches a query to content by meaning, not by exact words. We had a new agentic search mode, where an AI agent plans the search and applies filters itself. The question was whether the agent beat the customer's current search on the customer's own queries.

## What I measured

- I designed a head-to-head pilot: agentic search against the customer's production semantic search, on 101 of their real queries.
- We fixed the success criteria in writing before the first run.
- An AI model graded the results blind, without knowing which system produced each result. It agreed with human reviewers 97% of the time. That agreement let us use the AI grade as evidence.

## What I decided

- On the first run, the agent answered 38 of 101 queries. I diagnosed the failures and made three changes to the agent's instructions. The agent then answered 96 of 101.
- One failure was silent. The agent dropped filters on metadata fields that had no description, and it still returned results that looked right.
- I wrote a field-description runbook. The team uses it before they turn on the agent for a new dataset.

## Result

- Agentic search went to production. It was equal or better on 70% of queries, and 2.2x more precise on archive research.
- I then designed the conversion measurement for an upsell.

## What I tell the next customer

- Fix the success criteria before the pilot. Without them, the pilot result does not answer a question that anyone asked.
- Treat a low first score as a diagnosis task. Read the failures before you judge the agent.
- Look for silent failures. An agent that drops a filter gives a confident, wrong answer. Describe every metadata field before you turn the agent on.
