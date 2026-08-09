# Conceptual architecture

## Design goal

Create a coordination view over existing portal and clinical systems without becoming a second source of clinical truth.

![Conceptual architecture connecting authoritative sources, orchestration, constrained AI, and people](../assets/visuals/conceptual-architecture.svg)

```mermaid
flowchart TB
    subgraph Sources["Authoritative sources"]
        A["Appointments and scheduling"]
        B["Orders, results, and documents"]
        C["Care-plan tasks and instructions"]
        D["Outside-record exchange or upload"]
        E["Identity, consent, and proxy access"]
    end

    subgraph Orchestration["Care Timeline services"]
        F["Episode resolver"]
        G["Task and state engine"]
        H["Policy and access control"]
        I["Notification service"]
        J["Audit and analytics events"]
    end

    subgraph AI["Optional constrained AI layer"]
        K["Approved-source retrieval"]
        L["Plain-language transformation"]
        M["Grounding and safety checks"]
    end

    N["Patient or authorized proxy"]
    O["Care-team review queues"]

    Sources --> F
    F --> G
    E --> H
    H --> G
    G --> N
    G --> I
    I --> N
    G --> O
    G --> K
    K --> L
    L --> M
    M --> N
    G --> J
    M --> J
```

## Component responsibilities

| Component | Responsibility | Must not do |
|---|---|---|
| Episode resolver | Associate approved objects with a care episode. | Merge ambiguous identities silently. |
| Task/state engine | Normalize workflow states and dependencies. | Infer new clinical instructions. |
| Policy layer | Enforce patient, proxy, sensitive-data, and organizational rules. | Broaden access for convenience. |
| AI layer | Restate retrieved approved content in plain language. | Diagnose, triage, recommend, or fill missing clinical facts. |
| Review queues | Route record and clarification work to the right team. | Promise a clinical response time without policy support. |
| Analytics | Measure product behavior and guardrails with minimum necessary data. | Store unrestricted clinical text in analytics events. |

## Core data object

A timeline item should minimally contain:

```text
item_id
episode_id
item_type
display_title
workflow_state
owner_type
source_system
source_object_id
source_updated_at
due_at (optional)
access_policy_reference
ai_transformation_status (none, pending, passed, blocked)
```

Clinical content stays in the authoritative source. The timeline stores references and presentation state wherever feasible.

## AI request flow

```mermaid
sequenceDiagram
    participant U as User
    participant P as Policy service
    participant R as Approved-source retrieval
    participant L as Language model
    participant V as Validator

    U->>P: Request plain-language view
    P->>P: Check access, consent, and document type
    P->>R: Fetch approved source and version
    R->>L: Bounded content and constrained instruction
    L->>V: Candidate explanation with citations
    V->>V: Check grounding, unsupported advice, and required warnings
    alt Pass
        V->>U: Labeled explanation plus original source
    else Block
        V->>U: Original source plus contact-care-team path
    end
```

## Security and privacy principles

- Minimum necessary data in events, logs, prompts, and caches
- Encryption in transit and at rest
- Short retention for generated text unless explicitly saved under policy
- No model training on patient content without a separately authorized program
- Access checks at retrieval and display time
- Immutable audit trail for source version, prompt policy, model version, output, and disposition
- Threat modeling for prompt injection inside uploaded documents
- Vendor, HIPAA, consent, information-blocking, records-retention, and accessibility review before implementation

## Failure modes

| Failure | Safe behavior |
|---|---|
| Source unavailable or stale | Show unavailable/stale state and original location; do not summarize cached content as current. |
| Conflicting instructions | Show both authoritative sources, flag conflict, and route to the care team. |
| AI grounding check fails | Suppress explanation and show original content. |
| Outside record cannot be matched | Hold outside the chart, request correction, and show non-incorporated status. |
| Notification fails | Preserve in-product task state and retry within policy. |
| Proxy permission changes | Recheck at display time and remove access immediately. |
