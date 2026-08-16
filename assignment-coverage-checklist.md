# TRM Take-Home Assignment Coverage Audit

This is a production control, not part of the two-page submission. `Covered` means the artifact visibly demonstrates the requirement; prose that promises a prototype behavior does not prove it.

## Prompt coverage

| Prompt requirement | Evidence | Status |
| --- | --- | --- |
| Choose one customer segment | Brief names `Financial Institutions (AML & Compliance)` | Covered |
| Explain why it is valuable | USD 35B sizes customer harm; fragmented cases create the opportunity; commercial value is tested through faster recognition, reduced effort, and paid adoption | Covered without treating scam volume as bank loss or TRM TAM |
| Choose one specific user | Maria, financial-crime investigator handling reported crypto scams | Covered |
| Identify a meaningful bottleneck or ceiling | Exact/entity search misses semantically and behaviorally related cases | Covered |
| Ground the current path to outcomes | Concrete USD 85K case example; master PRD current workflow | Covered; example is correctly labeled illustrative |
| Prioritize an AI-native solution | Cross-Case mode uses heterogeneous retrieval and grounded explanation | Covered |
| Change capability, not just automate | Decision scope expands from one case to campaign discovery | Covered |
| Use TRM's existing investigative data | Narratives, payment patterns, timing, counterparties, blockchain intelligence | Covered |
| Focus on experience, not data expansion | Adding chains and new sources is explicitly out of scope | Covered |
| Realistically scope an initial product | 48-hour proof followed by a read-only three-investigator thin slice | Covered |
| State assumptions, tradeoffs, and omissions | Explicit in brief and master PRD | Covered |
| Actionable for engineering | Pipeline, inputs/outputs, permissions, requirements, errors, auditability | Covered in master PRD |
| Actionable for design | Workflow, states, evidence hierarchy, acceptance criteria | Covered in master PRD; must appear in prototype |
| Actionable for PMM and sales | Customer claim, champion, buyer, ARR formula, objection, commercial proof | Covered |
| Standalone two-page Google Doc | Live document plus sources | Covered; connector readback and two-page PDF export verified, but rendered page images were not visually inspected |

## Product-risk audit

| Risk | Why it matters | Required defense |
| --- | --- | --- |
| Co-Case Agent overlap | TRM already markets victim-report reasoning, syndicate clustering, Signatures, next-step guidance, and auditability | Present Kindred as an operation-level FI workflow built on Co-Case; validate incremental value against the current bank workflow |
| Existing bank link-analysis tools | NICE, SAS, Unit21, and bank case systems already surface connected entities or network patterns | Benchmark against the customer's actual tools; claim narrative plus TRM fund-flow lift, not invention of link analysis |
| No direct customer evidence for the precise workflow | The scenario is plausible but illustrative | Run the retrospective design-partner test before investing beyond the thin slice |
| Case-density assumption | Many banks may not have enough reported crypto cases | Make case count and field completeness a qualification gate, not a universal-bank claim |
| Fraud/AML ownership ambiguity | Bank fraud, AML, compliance, and crypto teams may own different steps | Validate workflow owner and escalation destination during design-partner discovery |
| Too much V1 scope | Comparison, escalation, generation, audit, integrations, and model work could become a quarter-long build | Thin slice is read-only candidates, cited evidence, and feedback; sequence the rest behind proof |
| Arbitrary metric targets | 60% and 25% are hypotheses, not researched benchmarks | Label them hypotheses and reset after baseline measurement |
| Outcome attribution | Scam volume is not bank revenue loss, and recognition alone does not prevent loss | Use time saved, exposure surfaced, and earlier escalation; test post-escalation avoided exposure only later |

## Prototype coverage

No prototype artifact or URL is present in this workspace. The assignment is incomplete until each row is demonstrated in a functional build.

| Required demonstration | Required prototype evidence | Current status |
| --- | --- | --- |
| Primary workflow | Open case through campaign escalation and audit entry | Unverified / blocking |
| Core AI experience | Ranked candidates with supporting and contradictory citations | Unverified / blocking |
| Changed capability | A connection missed by exact search becomes visible and actionable | Unverified / blocking |
| End-to-end experience | Trigger, search, compare, judge, escalate, edit summary, audit | Unverified / blocking |
| Functional interaction | Reviewer choices update product state | Unverified / blocking |
| Honest failure behavior | No-match, insufficient-data, conflict, and source-unavailable states | Unverified / blocking |
| Live iteration readiness | Inputs, thresholds, and source availability can be changed quickly | Unverified / blocking |

## Lawrence feedback coverage

| Feedback signal | Submission response | Status |
| --- | --- | --- |
| Customer-centric examples | Maria's USD 85K illustrative case anchors the problem and demo | Covered |
| Show what is being built now | Cross-Case mode is connected to Co-Case Agent and Compliance360 | Covered in brief; demonstrate in prototype |
| Ship faster than a quarter | 48-hour proof and smallest read-only thin slice | Covered |
| Additional chains and data move rapidly | Kindred inherits supported TRM intelligence; data expansion is not V1 | Covered and aligned with prompt |
| Beacon / consortium downstream value | Confirmed matches can support governed downstream sharing without adding cross-bank retrieval to V1 | Covered |
| Ground team in problem | Opening sequence: customer, concrete failure, decision ceiling | Covered |
| Explain prioritization | Alternatives and explicit deferrals | Covered |
| Metrics | Customer outcome, quality, safety, and commercial proof | Covered |
| Product marketing / sales | Claim to earn, champion, buyer, objection, paid adoption/expansion | Covered |
| AI | Why AI, deterministic boundaries, and TRM-specific lift test | Covered |
| Product brief walkthrough | Two-page standalone structure | Covered; rehearse silent-review transition |
| Live product iteration | Constraint protocol and editable prototype required | Prepared in runbook; prototype unverified |
| Answer comments asynchronously | Monitor Google Doc comments during silent review; answer concisely in thread | Prepared in runbook |
| Ownership and values examples | Separate behavioral requirement, not a take-home-document section | Not part of brief; rehearse STAR stories |

## Submission gates

1. Provide and test a functional prototype URL.
2. Run the complete workflow at desktop presentation resolution with no dead ends.
3. Rehearse one live change that removes narrative access and one that lowers case volume.
4. Cold-read the Google Doc as engineering, design, PMM, and sales; every role should know its next decision.
5. Export and visually inspect the final two-page PDF after all copy edits.
