# TRM Labs Leadership Principles — Interview Prep

**Interview:** Kinsey (Senior Account Director) — Values/Behavioral
**Date:** August 11, 2026

## ⎯⎯ SECTIONS (Cmd+F to jump) ⎯⎯
## RECRUITER GUIDANCE → TELL ME ABOUT YOURSELF → TRAILBLAZER → CRAFTSPERSON → COLLEAGUE → BACK-POCKET → QUESTIONS FOR KINSEY → DELIVERY REMINDERS

---

## RECRUITER GUIDANCE

- Avoid quarter-long stories. TRM ships in days, not sprints.
- Customer-centric, concrete moments — not abstract frameworks.
- This interview is about **ownership**: what you built, what you drove, end-to-end.
- Narrate your thinking out loud, including uncertainty.

---

## TELL ME ABOUT YOURSELF

### Who I am
- I'm Anish
- ~10 years in product management
- Started in cloud infrastructure and personalization
- Last 4-5 years: fraud, risk, and identity systems in e-commerce and financial services

### DefenseStorm (most recent)
- First PM building the fraud product for banks and credit unions
- I owned it end-to-end
- Took the system from minutes-level alerting to two-second real-time decisioning
- Four FIs in beta, projected six-figure monthly fraud loss reduction

### Forter (previous)
- Led expansion of fraud platform into the PSP market — Stripe, Adyen, Square
- Real-time fraud decisions embedded directly in payment flows
- Grew it to 8-10% of total company revenue in a multi-billion dollar market
- I was in the deal — ran POCs, led demos, used sales cycle learnings to decide what to build

### HavenFi (current)
- Building a social engineering/scam intervention platform for front-line support teams at FIs
- Working demo that I've been showing to FIs to validate the problem
- Same problem space TRM operates in — I'm here because I'm already working on this

### Why TRM
- TRM's mission to build a safer world is real — IRS-CI, Netflix documentary, disrupting crypto laundering globally
- 5 years building fraud/risk systems for the same customers TRM serves
- Independently building a scam intervention product in the same space
- The way TRM builds — shipping in days, PMs in the deal, AI as how you work — that's how I already operate
- I built this take-home prototype and brief in days using Claude Code

---

## TRAILBLAZER — Impact-Oriented Trailblazer

**PDF:** "Customer centricity, prioritization, and adaptability."
**JD:** "Customers first, speed, adaptability. Treat every plan like an experiment — test, ship, measure, iterate quickly."

---

### Story A — Shipping Without a Ready Component (Forter)

- **S:** Leading fraud decisioning product for PSPs. Successful POC with major customer — strong approval rates, low chargebacks. Ready to go live and pay us. Two weeks before launch, engineering flagged an internal component wasn't ready — needed two more weeks.
- **T:** Delay the launch and risk the contract, or ship without the component.
- **A:**
  - I assessed the accuracy delta with data science — marginal for this customer's profile
  - I evaluated delay cost: contract exposure, relationship risk, revenue timing
  - I made the call same-day: ship, protect the launch
  - I told the customer transparently — they accepted it
- **R:** Customer went live on schedule. Enhancement shipped next sprint, zero impact.
- **Speed:** Same-day decision.
- **Line:** "Speed vs. quality isn't about cutting corners — it's about knowing which gap matters for the customer in front of you."

**Follow-ups:**
- "How did you know?" — Data science assessed the accuracy delta. Not meaningful enough to justify delay.
- "What if wrong?" — Enhancement shipping next sprint regardless. Delay cost exceeded the risk.
- "Customer care?" — Transparent about the tradeoff. Strengthened the relationship.

---

### Story B — Investigation UX: Two-Week Design Sprint (DefenseStorm)

- **S:** Existing investigation UI was raw log feeds built for cybersecurity analysts. Fraud investigators stitching together what happened manually. 10-12 min per investigation. 10% weekly usage.
- **T:** Redesign from the ground up and validate with real investigators. Two-week sprint.
- **A:**
  - I defined one metric: time from alert to close
  - I built prototypes in Figma, put them in front of 4 investigators, 2 sessions each
  - I measured time to categorize alerts in each version — quantitative
  - I iterated: build, measure, adjust, repeat — multiple cycles in two weeks
  - I made a prioritization call: backend work to route all alerts into new view would take sprints. I shipped with 10% of alerts — measurable value now, not 100% later
- **R:** 10-12 min → 3-4 min (70% reduction). Weekly usage 10% → 50%.
- **Speed:** Two-week sprint. Multiple iterate cycles.
- **Line:** "Treat every plan like an experiment. I built it, measured it with real investigators, and kept iterating until the numbers moved."

**Follow-ups:**
- "Biggest improvement?" — Insight: investigators don't need more data, they need the deviation story. Restructured view around that.
- "When to stop?" — When time-to-close flattened and feedback shifted from "can't find it" to "this makes sense."

---

## CRAFTSPERSON — Master Craftsperson

**PDF:** "Good judgement, velocity, and grit."
**JD:** "Balance speed with high standards, own outcomes end-to-end, invest in getting better everyday."

---

### Story A — Blocking Premature ML Deployment (DefenseStorm)

- **S:** Building real-time fraud interdiction from scratch. Leadership wanted ML on day one — better customer story. No labeled fraud data.
- **T:** Assess if ML was ready or would hurt more than help.
- **A:**
  - I modeled false positive rate at expected volume vs. cost per lockout — 15% FP rate = material bad experiences monthly
  - I identified no feedback loop — without fraud labels from banks, model couldn't learn. Wrong at a fixed rate indefinitely.
  - I presented the math to leadership directly
  - I held the position against pressure
  - I defined clear criteria for when ML was justified — minimum labeled dataset + functioning feedback signal
- **R:** Launched rules-only. No noisy model eroding trust. Introduced unsupervised anomaly detection when data supported it. Customers trusted system from day one.
- **Speed:** Three days to model and present.
- **Line:** "Leadership wasn't wrong to want ML — the timing was wrong. Quantifying what 'wrong timing' costs is what moved the decision."

**Follow-ups:**
- "How get agreement?" — False positive cost model + no feedback loop + concrete threshold for when. Not never — not yet.
- "Were you right?" — Yes. Launched clean. ML came on the schedule data could support.

---

### Story B — Finding a Hidden Revenue Leak (Kibo)

- **S:** Monitoring recommendation analytics. Found primary engine (higher conversion) only firing 70% of the time. 30% falling back to weaker model. Nobody flagged it. Not on any roadmap.
- **T:** Diagnose root cause and build business case — no budget or engineering commitment.
- **A:**
  - I found root cause: recommendations computed without customer filters. Filters narrowed results → fallback
  - I got pushback from engineering — "this is how it's always worked," fixing = more storage/compute cost
  - I built ROI model: revenue delta exceeded infrastructure cost. Could pass cost through in pricing.
- **R:** Engineering reprioritized. 70% → 90% utilization. ~10% revenue uplift for affected customers.
- **Speed:** Found Tuesday, ROI model Thursday, reprioritized following week.
- **Line:** "Nobody asked me to find that. I was in the data and something didn't look right. That's craft."

**Follow-ups:**
- "How convince engineering?" — Revenue delta, cost, math works. Business case, not technical opinion.
- "How find it?" — Proactively monitoring analytics. 70% stood out.

---

## COLLEAGUE — Inspiring Colleague

**PDF:** "Integrity, apprenticeship, and positive energy."
**JD:** "Clarity and energy, not noise. Humility, candor, one-team mindset — giving and receiving feedback to make the team stronger."

---

### Story A — Coaching Design Lead on Customer Interviews (DefenseStorm)

- **S:** Two-week sprint shipping new investigation experience. Running customer interview calls to inform design.
- **T:** Make sure we were getting real customer signal, not presenting at them.
- **A:**
  - I used AI to analyze transcripts — how much time each person was talking
  - I found: designer 70%, me 10%, customer 20%
  - I had a direct one-on-one. Showed the data: "We should be 30-40%, they should be 60-70%."
  - I didn't soften it — data and what needed to change
- **R:** He adjusted. Conversations got meaningfully better. Customer signal got stronger. Investigation UX shipped better for it.
- **Speed:** Mid-sprint course correction.
- **Line:** "The best product decisions come from customer signal, not from us talking at them."

**Follow-ups:**
- "How'd he take it?" — He understood. Data, not personal. Framed around shared goal.
- "How give feedback generally?" — Specific, data-driven, framed around outcome. Never about the person.

---

### Story B — Catching Signal Gap Before Customer Did (Forter)

- **S:** Running POC with Adidas — ATO, sign-up, registration fraud. Internal analysts flagged higher-than-expected false positives.
- **T:** Find root cause before customer escalated or POC failed.
- **A:**
  - I found root cause: not receiving MFA completion data — model couldn't learn if step-up decisions were correct
  - Customer hadn't raised it — I caught it first
  - I called Adidas that same afternoon
  - I told them: signal gap, here's my plan
  - I asked for manual MFA files as interim fix while engineering built proper API (~2 months)
- **R:** FP rate dropped ~10%. Adidas moved from POC to live customer.
- **Speed:** Root cause in a day, called customer that afternoon, interim fix immediate.
- **Line:** "Catching your own gap and calling the customer before they call you — that's integrity."

**Follow-ups:**
- "Why not wait for fix?" — Two months too long. Manual files = real data to tune immediately. Speed > cleanliness.
- "Lost confidence?" — That's why I called proactively. Transparency before they discover it.

---

## BACK-POCKET ANSWERS

### AI Fluency
- I'm building HavenFi — scam intervention platform for FIs — using AI tools
- Working demo in front of real FIs
- AI isn't something I'm planning to adopt — I'm already building a product with it
- *Backup:* Built Kindred prototype + brief in days using Claude Code

### Receiving Feedback
- At Forter, I drove a recommendation to kill a partnership product. Data was solid, leadership agreed.
- Manager's feedback afterward: your executive summaries are too long
- I was disappointed — I prided myself on thoroughness
- He was right. The thoroughness was for me, not the reader.
- I changed: lead with the decision and why. Calibrate depth to audience — CTO vs. head of sales.
- **Line:** "The thoroughness was for me, not for the reader."

### How I Bring Energy
- I bring customer signal directly into pod calls — actual quotes and clips, not summaries
- After investigation redesign: brought in clip of investigator saying product changed how they work
- When your engineer hears a real customer say that, they show up differently to the next sprint
- Not shipping tickets — solving a problem they've heard in someone's voice
- **Line:** "I bring the customer's voice into the room."

---

## QUESTIONS FOR KINSEY

- "When the product isn't where the customer needs it — how does the PM relationship work here?"
- "What does a PM do that makes your job easier versus harder?"
- "What's the hardest part of selling TRM's newer products versus the established ones?"

---

## DELIVERY REMINDERS

1. Keep each story under 90 seconds. Let her ask follow-ups.
2. Don't narrate STAR. Just tell the story. Bullets are for prep, not delivery.
3. Land the closing line flat. Period, not a pitch.
4. No jargon. "Internal component," not "Brain microservice."
5. Narrate your thinking — Lawrence flagged this.
6. Don't say "ultimately."
7. Don't credit AI for your judgement.
8. Don't say "recommendation to leadership." You made the call.
9. Investigation sprint overlaps with design lead story — acknowledge naturally if both come up.
10. Receiving feedback and energy stories are back-pocket — pull out if asked.
