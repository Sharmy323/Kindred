# Jenny Conversation Prep — Quick Reference

**30 min, 1:1. She's pulling threads from your presentation. This is a working-fit conversation, not a rubric.**

**Reminders:** Keep answers under 60 seconds. Don't re-present. Ask her questions. Don't say "ultimately."

---

## Thread 1: Case Management Integration (she WILL ask this)

**Her question from presentation:** "Did you think about a path where our AI agent could plug into an existing case management system?"

**Your answer:** "The moat isn't the interface — it's the data. The smart play is embedding Kindred's intelligence into where investigators already work. The Unit21 partnership is already heading this direction. Kindred would be the next layer through that same pipe. 'Add this to what you have' beats 'replace what you have.'"

**If she pushes:** "In the presentation I treated this as a technical question. The real insight you were pointing to is that integration IS the go-to-market strategy. You don't win by building the best investigation UI. You win by being the intelligence layer that makes every investigation UI smarter."

**How it actually works (if she asks for detail):**
- Today: Unit21 → calls TRM API → gets wallet risk data back → shows it to investigators
- Kindred: widen the pipe the other direction. Case data (already in Unit21) → flows to TRM → Kindred processes against attribution layer → connections flow back into Unit21
- The bank doesn't do anything new. The negotiation is TRM ↔ Unit21, not TRM ↔ bank
- Unit21's incentive: Kindred makes their platform stickier. Bank can't switch to Actimize without losing the intelligence

**Phased rollout (if she asks about sequence):**
1. **Wallet cluster matching** — no ML, just cross-reference case wallets against TRM's attribution graph. Immediate value.
2. **Behavioral patterns** — transaction timing, amounts, routing. Needs labeled data from confirmed cases investigators already closed. Light ML.
3. **Narrative similarity** — compare victim stories. Needs text data, bigger data sharing agreement. Last to build.

**Integration surface:** Start with API (fastest). Graduate to embedded widget (TRM controls the experience). Skip push alerts (alert fatigue risk).

---

## Thread 2: Competitive Positioning

**Your answer:** "Cross-case correlation already exists in fiat — Actimize, SAS, Featurespace do it. We didn't invent this. What they don't have: crypto wallet behavioral data, on-chain fund flow tracing, wallet attribution. The honest pitch: 'We bring a proven pattern into the one data domain only TRM can power.' That's sellable because it's true."

**On Chainalysis:** "Their AI agents are within-case investigation assistance — OSINT, tracing, report generation. That's Co-Case Agent's scope. Not cross-case correlation. Different value prop entirely."

**On Actimize:** Don't position against them. Position alongside. "TRM extends your existing Actimize deployment into the asset class Actimize can't cover." Otherwise you're fighting a 20-year incumbent relationship.

**Honest weakness:** If the scam doesn't touch the blockchain (pure wire fraud to domestic accounts), Kindred's on-chain intelligence doesn't add value. Don't oversell coverage you don't have.

---

## Thread 3: Buyer Hierarchy

- **Champion** (investigations manager): "This makes my team faster and catches things we're missing"
- **Buyer** (BSA/AML Officer): "This reduces institutional risk and gives me proof for regulators"
- **Sponsor** (CCO): "This protects the bank"

Same product, three conversations. Jenny needs messaging for all three.

---

## Thread 4: Privacy Blockchains

**Your answer:** On public chains, TRM maps wallets to entities (attribution). On privacy chains, that breaks — transactions are encrypted. But money enters and exits through public chains, so TRM traces the entry/exit points. You shift from "who is this wallet" to "does this behavior match confirmed scam patterns." Be honest: confidence is lower. Require more evidence before recommending action.

---

## If She Asks About You

**Background (keep tight):** ~10 years in product, last 4-5 in fraud/risk. Forter: led PSP expansion (Stripe, Adyen), 8-10% of revenue, in the deal running POCs. DefenseStorm: sole PM on fraud product for banks, real-time alerting. Building a scam intervention product independently right now.

**What excites you:** Mission is real. How TRM builds matches how I work. FIs are the growth segment and that's my experience.

**PM-PMM collaboration:** Best pattern is PMM in customer calls hearing the buyer's actual language. Bring PMM in when the problem is clear, not when the feature is done. "What I'd want from you: push back on my framing. If I say 'helps investigators find connected cases' and you say 'they care about reducing time-to-SAR' — that's the most valuable thing a PMM can tell me."

---

## Questions to Ask Jenny

1. "How do you think about positioning TRM's newer products versus the established blockchain analytics story — extension of the brand or a new conversation?"
2. "What's the hardest part of enabling sales to sell AI products — explainability, proof points, or something else?"
3. "What does the FI buyer need to hear that's different from what a crypto exchange buyer needs?"

---

## Key Risks to Be Honest About (if she probes)

- **Cold start:** Need a bank with enough scam case volume for patterns to emerge
- **Data access:** Banks are paranoid — but Unit21 already has the data and the agreements
- **False positive on holds:** Cost is orders of magnitude higher than on alerts — that's why the org-level threshold exists
- **Adoption:** If Kindred creates noise, investigators ignore it within a week. Feedback loop is critical.

---

## Positioning AI Without Hype

"AI is how the product works, not what the product is. The product is: you catch more connected fraud faster with fewer people."

Show evidence, not the model. "These three cases share a wallet cluster and similar victim narratives" — not "the model gave this a 0.87 similarity score." Evidence is auditable. Scores aren't.

---

## FIs vs. Crypto Exchanges

- Exchanges: crypto-native, faster sales, fewer legacy tools. Market maturing.
- FIs: growth market. Already have fraud/AML workflows — TRM adds crypto coverage to existing ops. Procurement is 6-12 months. Need a champion inside.
- **Messaging shift:** Exchanges hear "we help you comply." FIs hear "we extend your compliance into a new asset class you can't ignore."

---

## First 90 Days (if asked)

- Days 1-30: Customer calls, shadow investigators, learn where deals stall
- Days 31-60: Find the highest-leverage gap — what unblocks the most ARR?
- Days 61-90: Ship something. Not a roadmap — a working improvement.
- What I'd want from Jenny: tell me what sales struggles to explain, what objections have no good answer, which competitive deals we're losing
