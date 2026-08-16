# Kindred Presentation and Live-Iteration Runbook

## 20-minute prototype walkthrough

### 0:00-2:30 — Ground the team in the customer problem

- Segment: Financial Institutions (AML & Compliance); initial ICP is large US banks with high crypto-scam case volume.
- User: Maria, a financial-crime investigator handling reported crypto scams.
- USD 35B sizes customer harm, not bank loss or TRM TAM.
- Start with the USD 85K case. Show why exact search misses three related reports.
- State the ceiling: the bank can resolve each case and still fail to recognize the campaign.

### 2:30-5:00 — Show prioritization, not just the winner

- Considered summarization, pre-payment prediction, cross-bank sharing, and within-bank discovery.
- Chose within-bank discovery because it changes decision scope, uses differentiated TRM data, and bounds privacy and model risk.
- Explicitly say what evidence would make you reverse the decision: low case density or no hybrid-model lift.

### 5:00-14:00 — Demonstrate the product end to end

1. Open the active case and show the authorized search scope.
2. Show up to three candidate cases and why each appeared.
3. Open supporting and contradictory source evidence.
4. Compare chronology and material differences.
5. Mark one case unrelated and one useful; explain human control.
6. Escalate a suspected campaign and edit the generated evidence summary.
7. Show the audit entry.
8. Briefly show no-match or insufficient-data behavior.

Narrate the changed capability throughout: Maria is making a campaign-level decision she could not reliably make before, not merely completing the same case faster.

### 14:00-17:00 — Explain AI and technical boundaries

- AI: semantic narrative comparison, heterogeneous evidence synthesis, grounded explanation.
- Deterministic: access control, institution isolation, exact matching, filters, citations, audit logging.
- TRM advantage to test: narrative context plus attribution and fund-flow behavior beats exact search, generic semantic search, and the bank's current link-analysis tools.
- Product architecture: a cross-case FI workflow built on Co-Case and Forensics, reusing TRM intelligence and glass-box controls.

### 17:00-20:00 — Close on build, measurement, and GTM

- 48-hour retrospective proof, then a three-investigator read-only thin slice.
- First gate: prove useful incremental operation-level connections beyond the institution's current workflow.
- North-star: median time from the first related case entering the bank to campaign escalation.
- Discovery metric: incremental useful connections and campaigns versus current tools.
- Economic proof: investigation time saved and additional exposure surfaced; avoided loss is a later, controlled measurement.
- Guardrails: no unauthorized exposure and no increase in unsupported escalation.
- Claim to earn: `Find related crypto-scam cases your current search misses, with traceable evidence for escalation.`
- Champion: investigations manager. Buyer: Head of Financial Crime or Fraud Risk.
- Commercial proof: paid adoption or expansion, not usage alone.
- Phase 2, only after V1 proof: turn the first credible scam signal into protection for the next potential victim; validate through retrospective backtesting before any live intervention.

## 15-minute brief review

- Stop presenting and let the panel read silently.
- Watch Google Doc comments without interrupting the review.
- Answer factual or clarification comments concisely in their threads as they arrive.
- Do not debate strategic comments asynchronously; acknowledge the assumption and bring the tradeoff into the discussion.
- Group repeated comments into one verbal response after silent review.

## Live-iteration protocol

Use this sequence out loud:

1. **Restate the new fact:** What changed, without defending the old design.
2. **Name invalidated assumptions:** Data, user, workflow, safety, economics, or technical feasibility.
3. **Protect the invariant:** Earlier, defensible campaign recognition with investigator control.
4. **Generate 2-3 options:** Include the smallest change and a stop/defer option.
5. **Choose and explain:** Customer impact, risk, speed, and what is now omitted.
6. **Update the artifact:** Change the prototype first; then update scope, metric, or claim.
7. **State the new test:** What evidence determines whether the revision works.

## Rehearsal constraints

### Narrative access is prohibited

- Invalidates the strongest semantic signal.
- Fall back to transaction cadence, amounts, timing, counterparties, and TRM fund-flow behavior.
- Lower confidence; show more `Insufficient data` outcomes.
- Re-run the ablation test and reset quality thresholds.

### The bank has only 30 relevant historical cases

- Invalidates institution-scoped case density.
- Do not force the original ICP or weak matches.
- Options: choose a higher-volume design partner, narrow to a dense scam typology, or defer until privacy-preserving network data is viable.

### Cross-bank discovery is required

- Invalidates the V1 privacy boundary.
- Separate confirmed shared indicators from raw narratives and PII.
- Require governance, contribution rules, provenance, revocation, and network-density proof.
- Treat this as a different product phase, not a toggle.

### A newly important chain lacks full attribution

- Do not add chain ingestion to Kindred; that violates the prompt and ownership boundary.
- Degrade gracefully to available transaction and narrative signals, label missing attribution, and suppress unsupported claims.
- Track candidate quality by chain and disable the chain if evidence quality misses the gate.

### Automatic enforcement is demanded

- Preserve read-only enforcement in V1.
- Offer investigator-approved escalation or a shadow-mode policy test.
- Require precision, appeal, model-risk, and customer-harm evidence before any automatic action.

## Behavioral follow-through

The Account Director and values interviews are separate from the take-home. Prepare concise ownership stories that show:

- what you personally built or changed;
- the customer or ARR outcome you owned;
- a decision shipped in days, not a quarter-long program summary;
- what you cut to move faster;
- how customer evidence changed your prior view;
- where you made a mistake and changed your operating method.
