# MVP and backlog

## MVP outcome

An eligible outpatient can understand the state of a care episode and complete required non-clinical and provider-defined follow-up tasks without searching across multiple portal areas or making an avoidable status call.

## Scope rules

- Use existing authoritative data and content wherever possible.
- Introduce workflow state, not a parallel medical record.
- Start with one or two outpatient specialties with structured instructions.
- Treat missing data as a visible dependency, not a prompt for generation.
- Preserve phone, interpreter, and accessibility alternatives.

## Prioritized backlog

| Priority | Capability | User story | MVP acceptance signal |
|---|---|---|---|
| P0 | Episode timeline | As a patient, I can see completed, pending, and next actions in one view. | Every item has state, owner, timestamp, and source. |
| P0 | Preparation checklist | I can see provider-approved tasks before a visit. | No task is generated without an approved source. |
| P0 | Outside-record tracking | I can see what happened after I share a record. | Receipt, review, needs-action, and final-disposition states are distinct. |
| P0 | After-visit tasks | I can track follow-up from the documented plan. | Tasks map to source text and never infer treatment. |
| P0 | Escalation | I can ask the right team when something is unclear. | Message draft includes context; patient approves before sending. |
| P0 | Audit and consent | I can see when AI was used and control optional AI features. | AI output is labeled, logged, and disableable. |
| P1 | Plain-language view | I can read an easier explanation of approved content. | Sentence-level source links; unsupported statements blocked. |
| P1 | Reminders | I can receive reminders for chosen tasks and channels. | Opt-in, quiet hours, accessibility, and unsubscribe supported. |
| P1 | Proxy experience | An authorized caregiver can help without overreaching access. | Existing proxy permissions enforced per item. |
| P1 | Language support | I can view approved content in my preferred language. | Translation status and original are always visible. |
| P2 | Cross-episode dashboard | I can prioritize tasks across several care episodes. | Tasks deduplicate and preserve episode provenance. |

## Acceptance criteria for the timeline

1. The timeline groups events by care episode and orders them by clinical/workflow time.
2. Each card shows title, status, owner, due date when applicable, updated time, and source.
3. Status terms have plain-language definitions.
4. A stale or unavailable source produces an explicit unavailable state.
5. Sensitive items respect existing portal visibility and proxy-access rules.
6. Keyboard-only and screen-reader users can navigate the same actions.
7. The patient can reach a non-digital support path from every blocked task.

## Non-goals

- Diagnosing symptoms or conditions
- Determining urgency or replacing emergency guidance
- Recommending or changing treatment, medication, or dosage
- Writing new clinical instructions without provider approval
- Automatically incorporating outside data into the legal medical record
- Predicting recovery time for an individual patient
- Replacing clinicians, schedulers, health-information-management staff, or interpreters
- Claiming universal MyChart behavior across organizations

## Release plan

### Phase 0: discovery and baseline

Map the workflow, interview users and staff, define denominators, and measure current task completion and contact burden.

### Phase 1: deterministic timeline

Launch without generative AI. Aggregate approved objects, add state and ownership, and test whether coherence alone improves outcomes.

### Phase 2: source-linked explanation

Add optional plain-language transformation for narrowly approved document types. Require grounding, citations, safety checks, and monitoring.

### Phase 3: broader workflows

Expand specialties and task types only after equity, workload, privacy, and clinical-safety guardrails pass.
