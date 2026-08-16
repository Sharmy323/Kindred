# Products & Technology

> Product names change; treat the names below as `[VERIFY]` and confirm on trmlabs.com.
> The *capabilities* are the durable part — those are what you should understand.

## The core capabilities

### 1. Transaction monitoring
Real-time or batch screening of transactions against risk rules and typologies. A VASP
pipes its transactions in; TRM flags ones touching high-risk counterparties (mixers,
darknet markets, sanctioned addresses, scam wallets) so a compliance analyst can review.

### 2. Wallet / address risk scoring
Given an address, return a risk assessment and the entities/categories it's connected to,
including indirect exposure (funds that passed through several hops).

### 3. Investigations tooling
A graph/visualization workspace where an investigator traces flows of funds across
addresses and chains, follows the money, and builds a case. Think of it as a purpose-built
graph explorer over the blockchain.

### 4. Sanctions & watchlist screening
Screening addresses against OFAC and other sanctions lists, plus TRM's own attribution of
which addresses belong to sanctioned entities.

## The hard technical problem underneath

1. **Ingesting many chains.** Bitcoin, Ethereum, and dozens of others each have different
   data models (UTXO vs. account-based), token standards, and quirks. Adding a new chain
   fast is a real moat.

2. **Attribution.** Mapping pseudonymous addresses → real-world entities. Done through
   clustering heuristics, known deposit addresses, exchange data, open-source intelligence,
   and investigative work. Attribution quality is the product's credibility.

3. **Scale.** Blockchains are terabytes and growing; queries like "trace all funds N hops
   from this address" are graph traversals over enormous datasets that must return fast.

4. **Precision/recall tradeoff.** Too many false positives and compliance teams drown in
   alerts; too few and illicit flows slip through. Tuning this is a core product concern.

## Recent product launches (verified via web research, 2026)

- **Beacon Network** (Aug 2025): real-time cross-institution intelligence-sharing network.
  Crypto-native only (Coinbase, Binance, Kraken, Ripple, PayPal, Stripe, law enforcement,
  researchers) — explicitly excludes traditional banks. Manual "Flagger" initiates a wallet
  flag; system auto-propagates and alerts network on tagged-fund movement. Scoped to
  high-severity categories (DPRK, ransomware, terrorism financing, CSAM, scam recovery), not
  comprehensive day-to-day fraud. Proof point: Operation Atlantic, $12M frozen, 20,000+
  victims identified.
- **Unit21 partnership** (Jul 2026): brings TRM wallet/transaction risk data into Unit21's
  case management for banks/fintechs — single-tenant, unifies crypto + fiat detection in one
  workflow. Note: Unit21 separately runs its own **Fraud Consortium** — cross-institution,
  100+ banks/fintechs/crypto platforms, ~100M US adults covered, continuous automatic
  screening against shared signals, one-click fraud confirmation propagates network-wide.
  Matches on confirmed-fraud/identity signals, not crypto wallet behavioral fingerprints or
  narrative/scam-text reasoning, and only after confirmation — not before.
- **Co-Case Agent** (Mar 2026): AI agent embedded in TRM Forensics. "Glass-box" philosophy —
  suggests, explains, documents, full audit trail, human-led. Operates *within* one
  investigation, not across cases. Validates that explainability-by-design is already how
  TRM builds AI features — any new AI pitch should assume this bar, not treat it as novel.

## Competitive landscape for cross-case AI correlation (verified, 2026)

The mechanism "AI reasons across cases within one institution to surface pre-confirmation
matches, with an evidence trail" is **already proven in fiat fraud/AML** — not novel in
general:
- **NICE Actimize** "Investigate AI" / Entity Resolution & Link Analysis: AI-driven,
  explainable, cross-case correlation within an institution, explicitly pre-confirmation,
  learns across investigations. Their "Insights Network" extends this cross-institution too.
- **SAS Fraud Management**: real-time network link analysis finding fraud rings between
  entities with no shared identifier.
- **Featurespace ARIC**: behavioral networks extended to multi-transaction scam sequences,
  adapts in real time.

**None of them have:** crypto wallet/on-chain behavioral fingerprinting (off-ramp reuse,
clustering signatures) — not their data, requires TRM's attribution engine. **None confirmed
to do:** unstructured victim-narrative/pretext-text similarity matching — they operate on
structured transaction/entity graphs, not free text.

**Chainalysis's 2026 AI agents:** confirmed to be within-case investigation assistance
(OSINT, cross-chain tracing, Q&A, report generation) — closer to Co-Case Agent's scope than
to cross-case correlation. **Elliptic:** not verified either way, genuine unknown.

**The defensible claim:** the mechanism itself is proven elsewhere (fiat fraud) — the honest
pitch is "bring a proven pattern into the one data domain (crypto behavioral + narrative
signal) only TRM can power," not "we invented cross-case AI correlation." Still net-new *to
TRM's own lineup* regardless — nothing at TRM does this today.

## How to talk about it as a PM/analyst

- Frame features in terms of the **analyst's job-to-be-done**: reduce false positives,
  cut investigation time, expand coverage, defend a decision to a regulator.
- Understand the **alert → triage → investigate → report (SAR)** workflow. SAR =
  Suspicious Activity Report, the regulatory filing a compliance team may ultimately produce.
- Know the tension between **automation and explainability** — regulated customers need to
  justify decisions, so a black-box risk score isn't enough; the *why* matters.
