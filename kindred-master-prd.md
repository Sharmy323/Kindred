# Kindred: Linked Scam Intelligence for Financial Institutions

**Document status:** Product proposal for validation  
**Customer segment:** Financial Institutions (AML & Compliance)  
**Initial ICP:** Large US banks with high crypto-scam case volume  
**Primary user:** Financial-crime investigator handling customer-reported crypto scams  
**Decision owner:** Head of Fraud / Financial Crime Investigations  
**Product principle:** Suggest, explain, and document; the investigator decides.

## 1. Executive summary

Bank investigators usually review reported scams as individual cases. Existing rules can connect cases that share exact identifiers, but coordinated scam campaigns often vary wallets, payment paths, identities, and language across victims. The result is a visibility ceiling: an investigator can resolve the case in front of them while missing that it belongs to a larger campaign.

Kindred is a cross-case scam-intelligence workflow built on Co-Case Agent and Forensics. When an eligible crypto scam case is opened, Kindred evaluates prior narratives, fiat payment patterns, dispositions, and counterparties alongside TRM blockchain intelligence. A confirmed connection creates a persistent suspected-operation record, supports collaboration, and produces an auditable escalation summary.

V1 is institution-scoped, post-report, read-only with respect to enforcement actions, and limited to discovering related cases. It does not detect the original payment, share data across institutions, freeze funds, or declare that fraud occurred.

## 2. Strategy and prioritization

### Strategic diagnosis

TRM observed approximately USD 35 billion sent to fraud schemes globally in 2025. Large banks investigate many scam incidents as separate cases, even when several may belong to the same campaign. Evidence is fragmented across customer reports, bank records, payment activity, and blockchain data, creating a visibility ceiling: the institution has evidence that could reveal a campaign, but cannot reliably assemble it across cases. The USD 35 billion figure establishes the scale of customer harm; it is not a measure of bank losses, preventable losses, or TRM's addressable market. Kindred's initial ICP is therefore determined by case density, data readiness, investigative maturity, and the ability to act on campaign-level evidence.

TRM already provides tracing, victim-report intelligence, behavioral detection, case management, and Co-Case assistance. Kindred builds on those assets by combining institution-owned case context with TRM attribution and fund-flow behavior, then turning potential connections into an operation-level investigation workflow.

### Why this customer

The initial segment is large US banks that:

- receive enough reported crypto scam cases to create a useful historical corpus;
- can provide narratives and relevant transaction data under institution-level access controls; and
- have mature fraud-investigation teams responsible for customer harm and financial-crime escalation.

This is narrower than "enterprise financial institutions" and is not based on asset size alone. An institution with little crypto-scam volume or inaccessible case history has neither the data density nor deployment readiness required for V1. Smaller banks and credit unions remain a possible later segment once shared intelligence, consortium data, or lower-volume deployment economics are proven.

### Opportunity selection

| Opportunity | Customer impact | TRM differentiation | V1 feasibility | Decision |
| --- | --- | --- | --- | --- |
| Summarize individual cases | Medium | Medium | High | Defer: improves speed, not investigative scope |
| Predict scam risk before payment | Very high | Medium | Low | Defer: requires real-time decisioning and higher error tolerance |
| Share campaigns across institutions | Very high | High | Low | Defer: requires governance, network density, and data-sharing agreements |
| Discover related cases within one institution | High | High | Medium-high | Build first |

### Product strategy kernel

- **Diagnosis:** Investigators lack a reliable way to recognize campaigns when cases share patterns but no exact identifier.
- **Guiding policy:** Surface a few explainable candidate connections inside existing case review, using AI to expand investigative perception without automating judgment.
- **Coherent actions:** Start with one institution's closed and active cases; combine narrative and crypto signals; capture investigator feedback; measure confirmed discovery and earlier escalation before expanding the network or automating intervention.

## 3. User and problem

### Persona and job to be done

Maria is a financial-crime investigator at a large US bank whose customers encounter crypto through exchanges, payment flows, supported products, or partners.

**Job to be done:** When I investigate a reported crypto scam, help me determine whether it is an isolated event or part of a campaign so I can escalate the full pattern before more customers are harmed.

### Current workflow

1. A customer report or internal referral creates a case.
2. Maria reviews the narrative, account activity, beneficiaries, crypto transaction details, and available blockchain intelligence.
3. She searches case history for exact identifiers or relies on memory and informal team knowledge.
4. She determines the individual case disposition and documents it.
5. A campaign is recognized only if an exact identifier matches or someone manually notices repetition.

### Illustrative failure

A customer reports losing USD 85,000 over six weeks to a person met on a dating app who promoted a crypto investment. Funds were converted to stablecoins and moved through an exchange. Three earlier cases at the same bank share the grooming arc, escalating deposit cadence, two-day cash-out pattern, and off-ramp behavior, but not a wallet, beneficiary, or exact phrase. Maria handles the fourth case in isolation because the connection is not visible.

### Problem statement

A bank can resolve each scam case correctly and still miss that several customers are connected to the same scam operation. Scammers change wallets, beneficiaries, routes, and language, so exact search does not connect the records. No investigator can manually compare every new case with the institution's full case history. The evidence remains fragmented, causing repeated work and delaying operation-level escalation.

### Desired outcome

Help investigators determine whether a new case is isolated or part of a larger scam operation, and reduce the time required to escalate the linked activity with traceable evidence.

## 4. Product experience

### Value proposition

Kindred turns an individual scam report into a campaign-level investigative lens by finding and explaining related cases the investigator would not otherwise know to examine.

### Primary workflow

1. **Trigger:** Maria opens an eligible crypto scam case. Kindred begins an institution-scoped search automatically and shows progress without blocking case review.
2. **Candidate results:** Kindred returns up to three candidate cases grouped by evidence strength. It does not show a false-precision percentage.
3. **Explanation:** Each candidate identifies supporting and weakening evidence across narrative, money movement, timing, counterparties, and blockchain behavior. Every assertion links to its source.
4. **Comparison:** Maria opens a side-by-side view that highlights similarities, meaningful differences, case status, and chronology.
5. **Judgment:** She marks the candidate `Useful connection`, `Not related`, or `Unsure`, with an optional reason. These labels inform evaluation; they do not silently retrain production models.
6. **Action:** Maria can add selected cases to a suspected campaign and generate an editable evidence summary. Existing approval and escalation workflows remain authoritative.
7. **Share downstream:** A confirmed match can support an evidence package for Beacon or the institution's approved consortium workflow, subject to existing governance; Kindred does not share institution data automatically.
8. **Record:** Kindred writes the reviewed evidence, investigator decision, model/version metadata, and timestamp to the audit log and case record.

### Key states

- **Searching:** Non-blocking progress and scope searched.
- **Candidates found:** Ranked candidates with explainable evidence.
- **No strong candidates:** Clear empty state; no weak matches added merely to fill the list.
- **Insufficient data:** Missing inputs identified and remediation suggested.
- **Conflicting evidence:** Contradictions displayed alongside supporting evidence.
- **Source unavailable:** Existing case remains usable; Kindred explains which source could not be evaluated.

### How work changes

Today, Maria asks, "What happened in this case?" Kindred enables her to ask, "Where else has this pattern appeared, what evidence connects it, and is the pattern strong enough to escalate?" The product expands the scope of her decision rather than merely drafting the same disposition faster.

## 5. AI system requirements

### Why AI is necessary

Rules and exact search work when cases share known identifiers. They fail when campaigns preserve meaning and behavior while changing language, wallets, accounts, and routes. AI is needed to compare unstructured narratives and heterogeneous behavioral evidence, then synthesize a reviewable explanation. Deterministic retrieval and rules should still be used for exact matches, permissions, filters, and source citation.

### Inputs

- victim and investigator narratives;
- case type, status, disposition, and timestamps;
- relevant fiat transaction metadata and payment sequence features;
- crypto addresses, transactions, assets, chains, services, and attributed entities;
- institution-approved TRM intelligence available to the investigator.

### Outputs

For each candidate: case ID, evidence-strength tier, supporting evidence, weakening evidence, source links, chronology, and recommended next investigative step. Kindred must never state that two cases are definitively connected unless an investigator records that conclusion.

### Matching approach

Use a hybrid retrieval and ranking pipeline:

1. Apply institution, permission, eligibility, and time-window filters.
2. Retrieve candidates using semantic narrative similarity, structured transaction features, temporal patterns, exact entities, and blockchain-behavior signals.
3. Re-rank candidates using validated feature contributions and quality thresholds.
4. Generate a grounded explanation only from retrieved source evidence.
5. Suppress results that lack sufficient evidence or source traceability.

### Trust and safety requirements

- Institution data cannot be used to retrieve another institution's cases in V1.
- Access inherits source-system permissions and is checked at query and display time.
- Every generated claim must cite underlying evidence.
- Supporting and contradictory signals receive equal visual availability.
- Investigators control linkage, escalation, and enforcement decisions.
- All searches, outputs, feedback, edits, and actions are auditable.
- Sensitive victim data is minimized in previews and revealed only when authorized.
- Offline evaluation must test performance across scam types, writing styles, languages represented in pilot data, and protected-class proxies where relevant.

## 6. V1 requirements and scope

### Must have

- Automatic search from an eligible case
- Institution-scoped historical retrieval
- Narrative, transaction-pattern, timing, and blockchain-signal matching
- Maximum of three evidence-ranked candidates
- Evidence for and against each candidate, with source links
- Side-by-side case comparison and chronology
- Investigator feedback and suspected-campaign escalation
- Editable evidence summary and immutable audit record
- Searching, no-match, insufficient-data, conflicting-evidence, and error states
- Role-based access controls and source permission enforcement

### Should have

- Investigator-adjustable historical time window
- Filters by scam typology, asset, chain, and case status
- Team-level view of suspected campaigns created through Kindred

### Explicitly out of scope

- Cross-institution retrieval or data sharing
- Pre-transaction detection or customer intervention
- Automatic fraud determination, account restriction, or fund freezing
- Full criminal-network mapping
- Automated SAR filing or regulatory submission
- Open-web, social, messaging, or dark-web expansion in V1
- Adding chains or expanding TRM's underlying data coverage
- Continuous self-training from unreviewed investigator behavior

These omissions reduce initial network value but materially simplify privacy, model-risk, workflow, and deployment requirements.

## 7. Success measurement

### North-star outcome

**Time to linked-campaign escalation:** median time from the first related case entering the institution to an investigator escalating the suspected campaign.

### Pilot metrics

| Dimension | Metric | Initial target / decision use |
| --- | --- | --- |
| Quality | Precision of high-evidence candidates marked useful | Establish baseline, then require at least 60% before expansion |
| Discovery | Incremental useful connections per 100 eligible cases | Demonstrates new investigative scope |
| Timeliness | Median time from first related report to campaign escalation | Improve at least 25% against matched historical baseline |
| Adoption | Candidate review rate among eligible cases | Diagnose workflow fit; target at least 70% |
| Outcome | Incremental cases and exposure included in escalated campaigns | Quantifies campaign-level value without claiming prevented loss |
| Safety | Unauthorized evidence exposures | Zero tolerance |
| Calibration | Dismissal rate by evidence tier and scam type | Detect weak segments and threshold problems |

Fraud loss avoided is a longer-term business outcome, not a reliable primary pilot metric. Kindred starts after a report or alert, and campaign recognition alone does not prevent a loss. Any future claim must compare post-escalation exposure with a credible baseline and account for the intervention the bank actually took.

### Guardrails

- No increase in unsupported escalations per 100 eligible cases
- No material disparity in candidate quality across supported languages or scam types
- No degradation in case completion or system responsiveness that causes workflow abandonment

## 8. Assumptions and validation plan

| Assumption | Risk if false | Fastest validation |
| --- | --- | --- |
| Pilot banks have enough relevant historical cases | Sparse retrieval produces little value | Case-volume and field-completeness audit with 3-5 design partners |
| Narratives and transaction fields are accessible and usable | Integration or data quality blocks matching | Sample export and schema mapping before product build |
| Pattern matches lead to earlier campaign action | Interesting results do not change outcomes | Concierge test using historical cases and blinded investigator review |
| Explanations create appropriate trust | Users ignore results or over-rely on them | Prototype usability study measuring comprehension and calibration |
| TRM signals materially improve matching | Generic case search is sufficient | Ablation test: narrative-only vs. structured-only vs. combined TRM signals |
| Institutions can use case data for this purpose | Legal/model-risk review delays deployment | Early privacy, security, legal, and model-risk assessment |

### Go / no-go gates

Proceed only if at least one design partner has adequate data and a blinded evaluation shows useful incremental matches beyond the institution's current workflow. Expand only after quality, access-control, and adoption thresholds are met.

## 9. Delivery plan

### Phase 0: 48-hour offline proof

Use 50-100 closed cases from one design partner to compare the institution's current workflow, bank-data-only retrieval, and bank-data-plus-TRM retrieval in a blinded review. Stop if combined signals produce no meaningful lift or the data is insufficient.

### Phase 1: Pilot

Deploy a read-only candidate panel to three investigators at one institution: up to three candidates, two-sided cited evidence, and `Useful`, `Not related`, or `Unsure` feedback. Require human escalation and monitor quality by evidence tier.

### Phase 2: Operationalization

Add campaign workspace, configurable eligibility and retention controls, and write-back into supported case systems after pilot validation.

### Phase 3: Expansion, contingent on evidence

**Protect the next potential victim:** after V1 proves the core correlation claim, evaluate whether the first credible scam signal can flag other at-risk customers before they report. Begin with a retrospective backtest using historical data and no live customer contact or intervention. Evaluate additional investigative data and privacy-preserving cross-institution intelligence separately; none is an assumed extension of V1.

## 10. Go-to-market hypothesis

- **Champion:** Investigations manager accountable for scam operations and analyst effectiveness
- **Economic buyer:** Head of Fraud or Financial Crime Risk accountable for losses, customer harm, and controls
- **Customer claim to earn:** Reveal linked scam activity your current workflow misses and escalate the broader operation with traceable evidence
- **Packaging hypothesis:** Paid capability for institutions with sufficient case volume; validate willingness to pay before choosing case-volume pricing
- **ARR hypothesis:** Expansion or paid adoption within eligible bank accounts; size as eligible accounts x attach rate x incremental ACV using internal account and pricing data
- **Pilot motion:** One or two existing financial-institution customers with high crypto scam volume and accessible historical data
- **Primary objection:** "Our fraud platform already links cases." Response should be demonstrated, not asserted: benchmark its exact and entity-based retrieval against Kindred's combined narrative and blockchain-behavior matching on the customer's own labeled cases.
- **Commercial proof:** At least one design partner commits to paid adoption or expansion after the pilot; do not treat usage alone as market validation.
- **Product architecture:** Package Kindred as a paid campaign-intelligence workflow built on Co-Case Agent and Forensics, not as a similarity-search feature, standalone platform, or replacement case-management system.

## 11. Open decisions

- Which case system is the first integration target, if any?
- What minimum case count and field completeness produce viable retrieval?
- Which scam typologies should be eligible in the pilot?
- What evidence taxonomy is most understandable and defensible to investigators?
- Should a suspected campaign live in TRM or remain an object in the institution's case system?
- What model-risk classification and validation standard will pilot institutions require?

## 12. Prototype acceptance criteria

The functional prototype must let a reviewer complete the entire primary workflow: open Maria's case, see Kindred search, inspect three candidates, compare supporting and conflicting evidence, dismiss one candidate, mark one useful, escalate a suspected campaign, edit the evidence summary, and view the resulting audit entry. It must also expose no-match and insufficient-data states so the experience does not imply AI always finds an answer.

## Sources

- TRM Labs, [2026 Crypto Crime Report](https://www.trmlabs.com/reports-and-whitepapers/2026-crypto-crime-report), January 28, 2026.
- TRM Labs, [Co-Case Agent announcement](https://www.trmlabs.com/resources/blog/trm-labs-launches-co-case-agent-an-ai-assistant-for-every-crypto-investigation), March 25, 2026.
- FBI Internet Crime Complaint Center, [2025 IC3 Annual Report](https://www.ic3.gov/AnnualReport/Reports/2025_IC3Report.pdf), 2026.
