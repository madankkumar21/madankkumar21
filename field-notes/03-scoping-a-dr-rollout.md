# Scoping a $3.1M disaster-recovery rollout

**Customer:** a private bank. **My role:** lead sales engineer at Cutover, a runbook orchestration platform.

## Situation

The bank had to recover a growing estate of applications after an outage. Disaster recovery (DR) is the plan and the steps that bring applications back. Tier 0–1 applications, the bank's most critical, had to recover in under an hour. Cutover turns DR procedures into runbooks that run and track each step.

## What I measured

- I split the bank's playbook inventory into two groups: patterns that repeat across applications, and patterns unique to one application.
- I estimated the effort for each integration type: Ansible, Bash and ServiceNow.

## What I decided

- I scoped the rollout in phases: about 100 applications in year one, and 250 by year three.
- I led scoping for the company's first implementation services contract.

## Result

- The bank signed a $3.1M deal in H1 2024, measured as total contract value (TCV).
- It was the largest new logo in company history, by TCV and by annual recurring revenue (ARR).

## What I tell the next customer

- Sort the inventory into repeatable and unique patterns before you estimate. The estimate for a repeatable pattern applies to every application that uses it.
- Estimate effort per integration type, such as Ansible, Bash or ServiceNow.
- Phase the scope across years, with a first year that the customer's team can deliver.
