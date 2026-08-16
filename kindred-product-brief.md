# Kindred: Scam Containment for Financial Institutions

## Product scope

| | |
|---|---|
| **Customer** | Financial institutions with exposure to crypto-related fraud and scam operations |
| **Buyer** | BSA/AML Officer or Head of Fraud Investigations |
| **Core user** | Senior fraud investigator who owns case outcomes and drives intervention across the institution |
| **Problem** | As banks expand into on-chain services, their exposure to fraud grows with it. Coordinated scam rings cause significant losses across multiple customers before investigators recognize the pattern. Current tools may not detect these attacks at scale or in real time. |
| **Product** | An AI-driven workflow combining bank customer data and case management data, powered by TRM's blockchain intelligence, to detect coordinated fraud rings and help investigators intervene before more money moves |
| **Key objective** | Reduce containment time: the window from a confirmed case to shutting down the operation's ability to hit more customers |

## 1. Why financial institutions, why now

**More money is moving on-chain, and fraud follows it.** The tokenized asset market hit $310B in 2025, projected to reach $16T by 2030. JPMorgan and BNY Mellon have launched on-chain deposit products; a PNC/Citi/Wells consortium is exploring a joint stablecoin initiative. More on-chain activity means more fraud exposure: $23B in crypto fraud globally in 2025, growing 22% year over year. When funds move on-chain, the bank's visibility ends.

**TRM can see what the bank cannot.** Wallet attribution, cross-chain tracing, and fund convergence across victims. Kindred combines bank data with TRM's blockchain intelligence to surface patterns neither side can see alone.

## 2. Problem

Coordinated fraud rings direct victims to move money from their bank accounts into crypto, where funds become irreversible and the bank loses visibility. Every dollar lost to fraud costs the bank $5 in total. Each victim compounds that: reimbursement liability (UK banks paid £173M in year one of mandatory APP fraud reimbursement), 20+ hours per SAR, and regulatory scrutiny. But investigators work each case in isolation. The longer it takes to see the ring, the more it costs.

Carmen, our senior investigator, uses Co-Case to trace an $85,000 scam loss. She can investigate that case. But she has no way to know four other customers are in the same operation, connected through wallet clusters and on-chain patterns only TRM can see. The problem is not the single case. The problem is the ring she cannot see.

## 3. Solution

Kindred helps investigators identify coordinated scam rings. Carmen triggers Kindred from her confirmed case. Three steps:

1. **Understand the case.** Kindred pulls key signals: victim narrative, deposit patterns, wallet activity, on-chain movement. Carmen reviews and confirms before the search begins.
2. **Find related activity.** The agent compares signals against the bank's cases and TRM's blockchain intelligence. Returns likely related customers with evidence for and against each connection.
3. **Help Carmen intervene.** Surfaces who may still be at risk, what funds may be recoverable, and next steps. Every recommendation is explainable. Kindred recommends. It does not act.

**Co-Case explains what happened to one victim. Kindred shows where the same threat may be hitting the bank next.**

**Why AI is necessary:** Investigators can trace what happened to one victim, but cannot easily see how cases across the institution connect. AI picks up on coordinated patterns across deposit behavior, victim narratives, and on-chain fund flows at a scale and speed that humans cannot match.

## 4. Assumptions, tradeoffs, and what is not included

**Key assumptions:** (1) The bank gives TRM access to customer, transaction, and case data through a secure integration, with associated integration costs. (2) Fraud rings are coordinated enough for the AI to identify meaningful patterns at the right levels of accuracy and cost. (3) Trust is earned through explainability and accurate results, not assumed at launch.

**Key tradeoff:** Banks need to contain fraud faster, but acting on bad intelligence is worse than not acting at all. A wrongful account freeze carries regulatory and reputational risk the bank cannot delegate to software. Kindred accelerates detection of coordinated rings, but the investigator decides what action to take.

**Not included in V1:** Real-time transaction blocking (one false positive freezes a legitimate account). Automated SAR drafting (the investigator owns the filing). Cross-institution pattern matching (recent FinCEN guidance supports this, but V1 proves value within a single institution first). Direct customer outreach (the bank controls all communication with account holders).

## 5. What we build first

**Starting with:** Existing TRM bank customers with active fraud teams and meaningful scam volume. They already work with TRM and buy tools instead of building in house.

- **POC:** Offline. Run the agent against a confirmed, resolved fraud ring. Measure whether it identifies the same connections investigators already confirmed.
- **V1:** Live pilot with a small investigator team on incoming cases. Investigators agree or disagree with what the agent surfaces. Their feedback becomes labeled data to improve the agent.
- **V2:** Broader rollout across more investigators and institutions. Proven results and case studies enable expansion.

## 6. How we measure success

- **Containment time:** How fast do we go from a confirmed case to containing the broader operation? Baselined per customer before and after Kindred.
- **Match precision:** How accurately does Kindred identify coordinated cases? Measured against the validation dataset during POC, optimized before V1.
