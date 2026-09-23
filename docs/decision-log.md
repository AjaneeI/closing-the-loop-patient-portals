# Decision log

## D-001 — Frame the problem as inconsistent task closure

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Do not claim that MyChart lacks scheduling, exchange, care-plan, or AI capabilities. Focus on variation, discoverability, cross-step coherence, and workflow completion.
- **Why:** Official product documentation establishes that relevant capabilities exist. The defensible opportunity is making them consistently understandable and actionable.
- **Tradeoff:** The story is less provocative but more credible.

## D-002 — Rename the concept Care Timeline

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Use “Care Timeline” in the product narrative and describe AI as an optional layer.
- **Why:** “AI Care Timeline” over-centers a technology that is neither necessary for the deterministic MVP nor appropriate as the product's source of authority.
- **Tradeoff:** Marketing copy can still foreground responsible healthcare AI, but the product remains useful without generation.

## D-003 — Start with deterministic orchestration

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Phase 1 aggregates authoritative objects and adds state, ownership, and escalation without generative AI.
- **Why:** This isolates the value of coherence and lowers early clinical risk.
- **Tradeoff:** Plain-language support arrives later.

## D-004 — Treat outside-record handling as a state machine

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Separate received, matched, under review, needs action, incorporated, and not incorporated.
- **Why:** “Uploaded” can falsely imply that a clinician has seen or accepted the information.
- **Tradeoff:** Requires operational integration and careful terminology.

## D-005 — Use closed-loop completion as the north star

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Optimize for eligible episodes completed on time, with safety, equity, and workload guardrails.
- **Why:** Logins and clicks do not represent completed care-navigation work.
- **Tradeoff:** The denominator and terminal states require workflow-specific governance.

## D-006 — Generalize lived experience in public materials

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Exclude specific personal medical details and use general, non-identifying language.
- **Why:** The portfolio should demonstrate insight without disclosing private health information.
- **Tradeoff:** Some narrative specificity is intentionally removed.

## D-007 — No publication before explicit approval

- **Date:** August 8, 2026
- **Status:** Superseded after approval
- **Decision:** Prepare the local repository only. Do not create a remote, push, or open a pull request until Ajanee explicitly approves publication.
- **Why:** This matches the requested review workflow.
- **Tradeoff:** GitHub rendering and public-link validation wait until approval.

## D-008 — Publish the portfolio repository publicly

- **Date:** August 8, 2026
- **Status:** Accepted
- **Decision:** Publish `closing-the-loop-patient-portals` as a public repository under Ajanee's authenticated GitHub account.
- **Why:** Ajanee explicitly approved the repository name and public publication.
- **Tradeoff:** The case study and portfolio language become publicly accessible; no explicit reuse license is granted at launch.

## D-009 — Add standalone portfolio visuals after publication

- **Date:** August 8, 2026
- **Status:** Accepted corrective action
- **Decision:** Add five accessible SVG visuals covering the interface concept, architecture, KPI framework, MVP scope, and research validation matrix.
- **Why:** The initial public commit included Mermaid diagrams but omitted the standalone visual assets promised in the marketing plan.
- **Tradeoff:** The correction is visible as a second commit rather than part of the original publication; the decision log preserves that history transparently.

## D-010 — Publish an explicit reproducibility and assumptions boundary

- **Date:** September 23, 2026
- **Status:** Accepted
- **Decision:** Document which parts of the case study can be independently reviewed, which claims are hypotheses, what data is not present, and what evidence a credible pilot would need.
- **Why:** The repository should make it difficult to mistake a well-developed product concept for a measured production deployment.
- **Tradeoff:** The case study becomes more conservative in its claims, but the evidence quality and reviewability improve.
