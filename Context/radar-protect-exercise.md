# Radar Protect — Product Exercise

**Role:** Senior / Staff Product Manager, Fraud
**Format:** 2-page memo + 1-2 optional wireframes, 45-min session (10 min presenting, rest discussion)
**Panel:** CEO or CTO + Protect engineer

## Context

Radar Protect uses location, device, and network signals to make real-time fraud and geo-compliance decisions. Three primary tools today:

1. **Location checks** — calls to `Radar.trackVerified()` return signals + overall pass/fail
2. **Risk scores** — configurable weights on signals, classify users/devices as no/low/medium/high risk
3. **Fraud rules** — combine signals and behavioral criteria to create cases or block users/devices

Current system is primarily deterministic and manually configured. Goal: evolve from binary (red/green) to probabilistic (red/yellow/green) that is explainable and measurable.

## Voices in Your Inbox

**Large gaming customer:**
"How are you using machine learning? I need to know which users to allow, challenge, review, or block, and how that affects false positives."

**Prediction market prospect:**
"Will we benefit from risky devices, locations, and behaviors Radar has seen across its network?"

**Your CTO:**
"Customer outcomes will be delayed, incomplete, and biased. We also cannot create a black box or expose enough logic for fraudsters to game the system."

## Assignment

Choose one workflow (signup, login, deposit, or withdrawal). Propose how to evolve Protect's labeled data, risk scores, fraud rules, and reporting for that workflow.

### 1. Labeled Data
How should Radar collect and use confirmed fraud and non-fraud outcomes?

Consider:
- What customers should submit and how
- What entity labels should attach to (user, device, session, transaction)
- Delayed, incomplete, or contradictory outcomes
- Differences in fraud definitions across customers
- Bias from only investigating suspicious activity
- What Radar can learn across customers vs. what stays customer-specific

### 2. Risk Scores and Fraud Rules
How should labeled data improve existing risk scores and fraud rules?

Explain:
- Respective roles of risk scores vs. rules
- Whether to recommend weights, recommend rules, introduce ML, or combine
- What the product returns to customers
- How customers set thresholds for allow, step-up, review, block
- How probabilistic fraud decisions coexist with deterministic compliance checks
- Explainability without making the system easy to game

### 3. Reporting and Measurement
Describe the reporting experience for measuring decision quality and business impact.

Cover:
- Pass, step-up, review, and block rates
- Confirmed fraud capture
- Precision, recall, false positives, false negatives
- Label coverage
- Appeals and overturned decisions
- User friction and review costs
- Be precise about denominators
- How to avoid misleading metrics when only a subset of decisions gets labeled
- How customers evaluate new weights/rules/models/thresholds before enforcement

### 4. Execution
How would you lead this in Q3?

Cover:
- Validate with customers and internal teams
- Write spec and scope MVP
- Partner with Engineering and Design on tradeoffs
- Drive alignment with Nick (closely involved in product area)
- Pilot with customers and measure success
