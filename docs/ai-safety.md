# Responsible AI boundaries

## Product position

AI is optional infrastructure for explanation and organization. It is not the decision-maker, the source of truth, or the clinician.

## Allowed uses

- Restate provider-approved text in plainer language
- Translate approved non-emergency content under reviewed language workflows
- Extract explicit dates and tasks from approved instructions
- Organize existing tasks by due date and owner
- Draft a patient question for review before sending
- Identify that required information is absent or contradictory

## Prohibited uses

- Diagnosis or differential diagnosis
- Symptom triage or urgency determination
- Treatment, procedure, medication, or dosage recommendation
- Personalized recovery prediction
- Inference of instructions that are not present in an approved source
- Autonomous message sending, appointment changes, consent, or record incorporation
- Concealing, rewriting, or delaying the original clinical record
- Using unreviewed patient content to train a general model

## Output contract

Every AI explanation must:

1. Identify itself as an AI-generated explanation.
2. Name and link the source document and version.
3. Preserve clinically meaningful qualifiers, negation, dose, frequency, date, and uncertainty.
4. Separate direct source statements from interface labels.
5. Say when information is missing or conflicting.
6. Provide the original content and a care-team contact path.
7. Avoid new medical advice.

## Layered controls

| Stage | Control |
|---|---|
| Eligibility | Approved document types, user consent, access policy, language support |
| Retrieval | Exact source version, bounded context, prompt-injection filtering |
| Generation | Constrained transformation prompt, low creativity, structured output |
| Validation | Entailment/grounding checks, medication and number comparison, prohibited-content classifier |
| Display | AI label, citations, original source, timestamp, feedback and escalation |
| Monitoring | Stratified human audit, incident severity, drift and subgroup performance |

## Human oversight

Clinical governance approves supported document types and incident thresholds. Patients control optional AI display. Clinicians do not need to approve every low-risk explanation if a validated governance model permits it, but high-risk content types remain excluded or require explicit review.

## Risk register

| Risk | Example | Mitigation |
|---|---|---|
| Hallucination | Adds an activity restriction absent from the source | Grounding validator; suppress on failure; audit |
| Omission | Leaves out a warning or date | Required-field comparison; original always visible |
| Automation bias | Patient trusts simplified text over source | Clear label, citations, original-first option, education |
| Stale content | Summary survives after instructions change | Bind to source version; expire on update |
| Proxy disclosure | Sensitive item shown to an authorized but restricted proxy | Item-level access check at display time |
| Language inequity | Translation quality varies by language | Language-specific validation; fallback; monitor gaps |
| Prompt injection | Uploaded document instructs the model | Treat document as data; content isolation; allowlisted tasks |
| Workflow displacement | Staff assume the portal handled follow-up | Explicit ownership; operational monitoring and escalation |

## Incident response

Log the source version, output, model, policy version, affected workflow, and user-visible disposition. Triage severity with clinical safety leadership. Disable the narrowest affected workflow, notify stakeholders under policy, correct persistent content, and complete root-cause and recurrence-prevention review.
