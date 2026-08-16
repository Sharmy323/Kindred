# Proposed Pivot: From Post-Case Linking to Proactive Scam Defense

## Decision to reconsider

The current proposal, Kindred, searches a financial institution's historical cases after a scam case is opened, identifies potentially related cases, and helps an investigator assemble them into a suspected scam operation.

This solves a plausible problem, but it is not differentiated enough. Chainalysis, Elliptic, enterprise fraud platforms, and TRM's own Co-Case Agent already claim graph analysis, hidden-relationship discovery, case assistance, and investigative escalation. TRM also includes Co-Case Agent with Forensics at no additional cost. A paid product centered on "find similar cases" could therefore look like an incremental Co-Case feature rather than a new workflow that Sales can attach to revenue.

## Proposed product direction

Pivot from **post-case historical linking** to **proactive scam intelligence and intervention for large US financial institutions**.

The core promise:

> Turn the first credible scam signal into protection for the next potential victim.

When a customer report, Chainabuse report, or TRM intelligence signal reveals an emerging scam operation, the product connects the available evidence to potentially related activity among the bank's other customers. It shows investigators which customers may be exposed, explains the supporting and contradictory signals, and enables an institution-approved intervention before another payment occurs.

The product does not autonomously declare that a customer is being scammed or block a payment. It gives the bank earlier, evidence-backed awareness and routes the activity into its existing review and customer-intervention controls.

## Customer and user

- **Customer segment:** Large US financial institutions with meaningful scam exposure, relevant payment or crypto activity, and mature fraud operations
- **Economic buyer:** Head of Fraud or Financial Crime
- **Champion:** Head of Scam Strategy or Fraud Operations
- **Primary user:** Scam investigator or fraud operations analyst responsible for reviewing emerging threats and intervening with potentially affected customers
- **Customer goal:** Identify and protect additional customers once the institution has credible evidence of an active scam operation

## Current limitation

Today, the institution often learns about a scam only after a customer reports a loss. That report may contain valuable information about a wallet, website, payment sequence, narrative, or off-ramp. However, the evidence remains inside an individual case and does not immediately become a protection signal for other customers.

The institution can investigate the reported loss while failing to identify another customer who is preparing to send money into the same or behaviorally related operation.

## New capability

This product changes the user's capability from:

> Investigate a reported scam after the loss.

to:

> Use the first credible scam signal to identify and protect other potentially affected customers.

The workflow is:

1. A customer report or TRM signal reveals suspicious scam infrastructure or behavior.
2. TRM assembles a suspected scam-operation profile using available on-chain, off-chain, behavioral, and victim-reported evidence.
3. The system evaluates relevant bank activity for customers showing related pre-payment or repeat-payment behavior.
4. The investigator reviews evidence for and against each connection.
5. The investigator selects an institution-approved action, such as customer outreach, payment review, enhanced monitoring, or dismissal.
6. The outcome is recorded and the confirmed intelligence informs subsequent detection and investigation.

## Why AI is necessary

Exact matching can identify a reused wallet or beneficiary. It cannot reliably recognize an operation that changes wallets, websites, language, payment routes, and accounts while preserving its behavioral pattern.

AI is used to reason across heterogeneous evidence, including victim narratives, transaction sequences, timing, wallet behavior, attributed infrastructure, and known scam typologies. It produces a grounded explanation for human review. Deterministic systems remain responsible for permissions, exact matching, policy rules, auditability, and enforcement.

## TRM strategic advantage to test

The differentiation is not generic case linking or graph analysis. The thesis is that TRM can operationalize emerging scam intelligence earlier by combining:

- firsthand victim and scam reports from Chainabuse;
- TRM on-chain attribution and behavioral intelligence;
- AI-based detection of emerging scam infrastructure;
- institution-specific customer and payment signals;
- existing Wallet Screening and Transaction Monitoring workflows; and
- relationships with exchanges, law enforcement, and the Beacon Network for downstream disruption.

This is not yet a proven superiority claim. Chainalysis and Elliptic also offer broad on-chain intelligence, monitoring, and investigation capabilities. The testable differentiation claim is:

> TRM's combination of firsthand scam reports, bank-specific activity, on-chain behavioral intelligence, and disruption relationships identifies actionable customer exposure earlier or more accurately than the institution's existing controls and competing intelligence feeds.

The product should be stopped or repositioned if that lift cannot be demonstrated on customer data.

## Commercial thesis

Package the workflow as a paid **Scam Defense** or **Scam Intelligence and Intervention** module attached to Wallet Screening and Transaction Monitoring, rather than as a paid Co-Case feature.

The commercial thesis is expansion revenue from existing financial-institution customers that have sufficient scam volume and intervention readiness. Do not invent an ARR estimate without TRM's internal account, pricing, and pipeline data.

Commercial validation requires:

- at least one qualified financial institution willing to provide design-partner data;
- evidence that the product surfaces useful exposure beyond existing controls; and
- commitment to a paid pilot, contract expansion, or credible procurement path.

Usage without willingness to pay is not sufficient validation.

## Prototype scenario

Use one narrow, synthetic scenario:

> A customer reports an investment scam. TRM connects the reported wallet and website to an emerging scam operation, then identifies two other bank customers whose recent activity may indicate exposure to the same operation. One is preparing another transfer; the other previously sent a smaller payment.

The interactive prototype demonstrates:

1. **Emerging signal:** the initiating report and relevant TRM intelligence.
2. **Suspected operation:** the connected wallets, infrastructure, behaviors, and evidence quality.
3. **Potentially affected customers:** ranked candidates with supporting and contradictory evidence.
4. **Human decision:** customer outreach, payment review, monitoring, or dismissal.
5. **Outcome:** the intervention and customer response are recorded, with an auditable explanation.

The key product moment is not that the system finds a similar case. It is that evidence from one victim becomes an actionable protection signal for another customer.

## Initial scope

### Build first

- One initiating customer report or high-confidence TRM scam signal
- One institution-scoped search for potentially exposed customers
- Up to three explainable customer matches
- Supporting and contradictory evidence with citations
- Human-approved intervention routing
- Outcome capture and audit record

### Do not build

- Automatic payment blocking
- Autonomous fraud determinations
- A new payment-processing engine
- Cross-bank sharing of customer data
- Full production Chainabuse or Beacon integration
- New blockchain ingestion or attribution coverage
- Automated SAR filing
- Continuous model training from unreviewed outcomes

The prototype may use realistic synthetic data. It demonstrates the workflow and decision model, not production detection infrastructure.

## Success

### Primary outcome

**Median time from the first credible scam signal to identification of additional potentially affected customers.**

### Supporting measures

- Investigator-confirmed precision of high-confidence exposure matches
- Incremental potentially exposed customers found beyond existing controls
- Payment value surfaced before a subsequent transfer
- Customer interventions that confirm or interrupt scam activity
- False or unsupported interventions
- Investigation time required per reviewed match
- Paid pilot or account-expansion commitment

Avoided loss is a longer-term outcome. It should be claimed only when a specific intervention occurred and a credible counterfactual or matched baseline exists.

## Key assumptions and risks

- The bank can legally and technically use the relevant customer and payment signals for this purpose.
- There is enough time between scam payments for intervention to matter.
- TRM intelligence adds measurable lift over the bank's existing fraud controls.
- Investigators can act on the signal through an established customer-protection workflow.
- False interventions do not create unacceptable customer harm or operational burden.
- Chainabuse and other shared intelligence can be used with appropriate provenance, consent, and access controls.
- A paid module is commercially distinct from capabilities already included in Forensics or Co-Case Agent.

## Questions for critique

1. Is this a coherent product or an over-broad combination of intelligence, detection, and intervention?
2. Is the claimed TRM advantage actually differentiated from Chainalysis Signals and Elliptic's intelligence products?
3. Is the primary user correctly defined, or should this target a fraud-strategy manager rather than an investigator?
4. What is the smallest workflow that still delivers the new proactive capability?
5. What bank action can the product realistically trigger without becoming a payment-decisioning system?
6. Which metric best demonstrates customer value without making an unsupported avoided-loss claim?
7. Can this be packaged as a paid module without conflicting with Co-Case Agent being included in Forensics?
8. What evidence would invalidate the product thesis quickly?
