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

## How to talk about it as a PM/analyst

- Frame features in terms of the **analyst's job-to-be-done**: reduce false positives,
  cut investigation time, expand coverage, defend a decision to a regulator.
- Understand the **alert → triage → investigate → report (SAR)** workflow. SAR =
  Suspicious Activity Report, the regulatory filing a compliance team may ultimately produce.
- Know the tension between **automation and explainability** — regulated customers need to
  justify decisions, so a black-box risk score isn't enough; the *why* matters.
