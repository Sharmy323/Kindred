# Presentation Round — Key Takeaways

**Interviewers:** Adam (hiring manager, Speaker C), Jenny (PMM, Speaker A)
**Format:** 20-min prototype walkthrough, 10-min brief review, 15-min live iteration

---

## What Jenny Asked and Said

### 1. Case management integration
She asked whether the AI agent could plug directly into an existing case management system (Nice Actimize, Verifin, etc.) since most banks already have their case data sitting there. She wasn't asking a general question — she was pointing to a specific path: don't ask banks to send you data, go to where it already lives.

### 2. Privacy blockchains are the big opportunity
- Financial institutions expect confidentiality (payroll, vaults, etc.)
- Projects are moving from pilots to production on private chains
- She called the current work "really unsexy" but said the opportunity from it is massive

### 3. Behavioral detection is the future
Her exact framing: "more and more behavioral detection... pattern detection at scale is going to be even more critical because money laundering and crime is just going to look less and less obvious."

In plain English: as criminals get better at hiding, you can't rely on knowing who owns a wallet. You have to spot suspicious behavior patterns instead.

### 4. How attribution still works on private chains
Key insight: transactions typically move from a public chain to a private chain and back to a public chain at some point. So TRM's existing attribution data is still useful — you can trace the entry and exit points even when the middle is hidden on a private chain. TRM also has privileged view access on some private chains but is intentionally not using that for attribution.

### 5. She liked the prototype
"This is really cool prototype. Love seeing a local host." — genuine positive reaction to seeing a working product built with real tools, not a slide deck.

---

## What Adam Asked and Said

### 1. Scale question
With a million scam reports to the FBI last year (just the ones reported), how does this work when you have thousands of scam operations happening at once and limited analysts? He wasn't asking about infrastructure — he was asking about the product decision: at what point does human review become the bottleneck, and how do you handle that?

### 2. "Useful connection" button — the feedback loop
Asked what's being captured when the investigator clicks "useful connection." Wanted to understand how the system learns from investigator decisions over time.

### 3. Risk score presentation is unsolved
Adam was honest — TRM hasn't figured this out yet:
- A number like 72% doesn't mean anything to an analyst
- Labels like "low/medium/high/severe" still raise "what does high mean?"
- Some customers want "just give me the answer, green or red"
- Others already have their own risk models and want raw signals as inputs
- No one-size-fits-all solution exists

### 4. Immediate roadmap priorities
- Near-term: improved entity due diligence and monitoring, better risk scoring
- Bigger picture: explosion in stablecoins and tokenized real world assets

### 5. Live iteration — transaction holds
Asked to build real-time transaction blocking into the prototype. Key discussion points:
- Setting hold thresholds at the organizational level, not per-investigator
- Only showing a "place hold" option when confidence is very high (red), not at 72%
- The cost of a false positive on a hold is extremely high
- Need to re-explain the evidence at the point of action, even though earlier screens showed it

---

## How Anish Answered

### Strong moments
- Scoped down before scaling up — prove value at one institution first
- Named the false positive cost clearly: if the agent creates noise, investigators leave the tool
- Referenced FinCEN regulation for cross-institution data sharing as a future unlock
- On risk scores: suggested org-level controls where an admin sets the threshold, investigators just see red/not red — clean separation of policy from execution
- Called out that different customers want different levels of transparency
- Good rapport — "Until you might be blocking a transaction. You don't want to keep clicking Allow."

### Where answers could have been stronger
- Jenny's integration question: answered "it certainly can" and moved on instead of treating it as a go-to-market insight about reducing adoption friction
- Adam's scale question: answered about precision and false positives (correct) but didn't address how automation or triage could help analysts focus on highest-value cases at scale
- Could have been more specific about minimum viable data requirements for the POC
