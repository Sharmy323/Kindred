# Domain Glossary

Terms you should be able to use naturally in a TRM interview.

## Compliance / regulatory

- **AML** — Anti-Money Laundering. Rules and processes to detect/prevent laundering.
- **CFT** — Combating the Financing of Terrorism. Often paired: "AML/CFT."
- **KYC** — Know Your Customer. Verifying customer identity at onboarding.
- **BSA** — Bank Secrecy Act (US). Foundational AML law; requires monitoring & reporting.
- **SAR** — Suspicious Activity Report. Filing to regulators (FinCEN in the US) when
  suspicious activity is detected.
- **OFAC** — US Office of Foreign Assets Control. Administers sanctions; publishes the
  SDN list (see below).
- **SDN list** — Specially Designated Nationals list. Sanctioned entities/individuals;
  transacting with them is prohibited. OFAC has added specific crypto addresses to it.
- **FATF** — Financial Action Task Force. Global standard-setter for AML/CFT.
- **Travel Rule** — FATF requirement that VASPs share originator/beneficiary info for
  transfers above a threshold — hard in crypto because addresses aren't identities.
- **VASP** — Virtual Asset Service Provider. Exchanges, custodians, some wallets — the
  regulated entities in crypto.
- **CDD / EDD** — Customer / Enhanced Due Diligence.

## Blockchain / on-chain

- **Address (wallet)** — pseudonymous public identifier that holds/sends funds.
- **UTXO vs. account model** — Bitcoin tracks unspent outputs; Ethereum tracks account
  balances. Different data models to ingest.
- **Clustering** — heuristics grouping many addresses under one controlling entity.
- **Mixer / tumbler** — service that pools and shuffles funds to break traceability
  (e.g., Tornado Cash, which was sanctioned). A major risk signal.
- **Bridge** — moves assets across chains; a common laundering and exploit vector.
- **Hop** — one transaction step; "3 hops away" = funds moved through 3 transactions.
- **Exposure (direct/indirect)** — whether an address touched a risky entity directly or
  through intermediary hops.

## Threat / typology

- **Typology** — a recognized pattern of illicit behavior (e.g., peel chains, structuring).
- **Peel chain** — repeatedly moving funds, peeling off small amounts, to obscure a trail.
- **Ransomware** — extortion paid in crypto; a major on-chain investigation category.
- **Darknet market** — illicit marketplace settling in crypto.
- **Pig butchering** — long-con investment/romance scam; a growing fraud typology.
