# Reproducibility and assumptions

This document makes the evidence boundary of **Closing the Loop** explicit so the case study can be reviewed without confusing a product concept with measured production results.

## What can be reproduced from this repository

A reviewer can independently:

1. trace the core problem statements to the sources and confidence notes in [Research and evidence](research-and-evidence.md);
2. inspect the proposed workflow states and acceptance criteria in [MVP and backlog](mvp-and-backlog.md);
3. review the conceptual data flow and authority boundaries in [Architecture](architecture.md);
4. inspect the allowed and prohibited AI behaviors in [AI safety](ai-safety.md);
5. review the KPI definitions, denominators, guardrails, and proposed experiment design in [Metrics and measurement](metrics-and-measurement.md);
6. compare those artifacts with the public product narrative in the repository README.

There is no hidden production dataset or unpublished customer-level analysis behind the claims in this case study.

## Evidence boundary

The project uses:

- secondary research and publicly available product information;
- a conceptual workflow and prototype artifacts;
- proposed metrics and measurement definitions;
- explicit decision and risk documentation.

The project does **not** use:

- private customer or patient data;
- proprietary portal telemetry;
- production experiment results;
- measured causal effects;
- a deployed AI decision system.

## Assumptions that still require validation

The following are hypotheses, not findings:

- clearer ownership and status states will improve closed-loop completion;
- source-linked explanations will reduce avoidable clarification contacts;
- a unified timeline will reduce workflow fragmentation across teams;
- reminders tied to documented next steps will improve on-time task completion;
- narrowly scoped AI assistance can improve comprehension without increasing unsupported-summary incidents;
- the proposed guardrails are operationally feasible in a real deployment.

A pilot should test these assumptions rather than treating them as established outcomes.

## How to validate the concept

A credible pilot would define an eligible journey cohort and compare the proposed workflow with the current experience using pre-specified metrics.

Minimum evidence should include:

- closed-loop completion rate;
- customer task completion rate;
- clarification-contact rate;
- information review cycle time;
- staff workload impact;
- unsupported-summary incident rate for any AI-assisted feature;
- completion-rate gaps for relevant accessibility or access-need groups.

The study design should distinguish descriptive association from causal claims. If a causal claim is desired, use an appropriate randomized or quasi-experimental design rather than inferring causality from before/after dashboard movement alone.

## AI scope

AI is optional to the core product concept.

The deterministic MVP can organize authoritative records, statuses, owners, due dates, and escalation paths without generation. If AI is introduced later, its role is limited to approved source-grounded assistance such as summarization, question drafting, and explanation.

AI must not:

- invent missing instructions;
- alter source records;
- resolve high-impact decisions autonomously;
- present unreviewed output as authoritative;
- hide uncertainty or missing source material.

## Non-claims

This repository does not claim that:

- the concept has been deployed in production;
- the proposed metrics have improved;
- AI improved customer outcomes;
- the workflow reduced staff workload;
- the concept is clinically validated;
- the proposed intervention causes better completion.

Those questions remain for discovery, pilot implementation, and measurement.
