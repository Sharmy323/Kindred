# PM Interview Transcript (Lawrence)

**Participants:** Lawrence, TRM PM (Speaker A), Anish Sharma (Speaker B)

---

**Lawrence:** So that this is equitable and it goes both ways — at any point you want a clarification or whatever, don't be shy, all is good. So if that sounds good, let me know. Otherwise, let me know if you have any questions.

**Anish:** Cool, sounds good. Let's do it.

**Lawrence:** Awesome. Okay, I'm going to jump right into it. So I'm curious if you can tell me about a specific situation where you had to make a decision where speed was the most important factor but you had legitimate risk that you also had to weigh out. And what I'm curious about is what kind of information you had, what the trade offs were that you considered and what you actually did with that info.

**Anish:** Yeah, absolutely. So let me talk to you about my time at Defense Storm where I was the lead product manager focused on building a system — [echo issue resolved] — so speed under some constraints, right, where I had to make a decision and some of the trade offs.

Yeah, I was the lead product manager at Defense Storm on our fraud product and when I came into the company, I had surveyed all 10 to 15 of our customers and found that the biggest theme for them was that our system was not proactive — it was reactive. And what that means is, primarily cybersecurity company with kind of a bolted-on fraud product. But ultimately our system responded to suspicious activity five minutes after the fact. So fraud investigator comes in, they see — hey, weird IP address or weird device or impossible travel because someone's in Russia logging in and then they're in Nebraska trying to move money. But it happened five minutes after the fact. And so the core theme is how do we transition that to be more real time and be proactive.

And so I was tasked with moving that problem forward. And so there was ambiguity around:
- Which events and signals do we actually prioritize from that online banking experience within this first version of proactive product?
- What are the required latencies that we need to target for this solution? Because different online banking providers have different constraints and there's different user experience impacts to a millisecond/hundreds of milliseconds based decision versus a couple seconds.
- What do we do with the policy and what actions are we going to enable? Because if we approve somebody that turns out to be fraudulent, there's a cost for the financial institution. If we do step-up authentication and it's the legitimate user, there's a cost from a user experience perspective.

So there were varying trade offs and considerations that had to be made. And so overall:

1. **Prioritized account takeover use case.** There's first party fraud, second party fraud, third party fraud — third party fraud was the biggest business case problem.
2. **Built the system to be two seconds from a latency perspective instead of hundreds of milliseconds.** That narrowed which online banking providers we could work with but also allowed us time to build out that MVP and not create a more complex architecture.
3. **Going forward with rules-based system for v0 with initial pilot customers** and tackling ML later in shadow mode.
4. **Only enabled approve and step-up authentication** — no declines, no lockouts for the first version.

The result: early signs showed about a **30% reduction in financial losses** for key early beta customers.

**Lawrence:** Wow, that's impressive. By trimming the scope down to just that third party risk case and reducing the number of — what kind of a difference do you think you got in terms of the speed that you could ship? How much scope did you remove by doing that?

**Anish:** By just focusing on third party fraud? A significant amount, because there's so much more of a defined business case around third party fraud losses from our customers. Like authorized push payment fraud and social engineering is much more of an ambiguous challenge.

Another intentional decision was I had to look through what signals we were receiving from the online banking vendor — it's just audit data. So it's like what did this person do within their online banking session or account. There are vendors out there that do behavioral biometrics — they're actually looking at how fast people are browsing around, are they hesitating, and so forth — that would have complicated the overall MVP.

By choosing to just focus on this narrow initial use case with actual financial losses I could attribute with our initial pilot customers — definitely saved at least a quarter of time.

**Lawrence:** Nice. That's really cool.

---

**Lawrence:** I'm gonna shift gears a little bit. I want to talk about a time when you've had more high priority work than your team is actually able to do. What kind of decision-making do you use in that situation?

**Anish:** Yeah, absolutely. Kind of using this example from Defense Storm again. When I joined the company, I was the only product manager resourced to the fraud product. And they're just like, hey, here's — what do you think we should do?

In a nutshell, I went and audited every single customer — called it the "fraud squad." A few of us went and spoke to every customer, did customer research to understand: what's good, what's bad, what's terrible about your experience with the product? What were you promised? Is this solving the problems you hired our software to do?

And also used Pendo, a product analytics tool, so I could understand: are people actually logging into our tool? Are they using the product as we expect?

Three themes came out of this overall audit:

1. **Customers want a more proactive solution** — they don't want to be alerted on fraud after the fact.
2. **Configuration complexity** — the system was completely rules-driven, so the customer needed know-how and expertise to configure those rules and know what fraud patterns to look for.
3. **Investigation experience** — after that alert shows up in the fraud inbox, the whole North Star objective for a fraud investigator is: what is happening? Why is this alert showing up? Is it as I would expect for this type of customer? One data point: when I looked at Pendo, I saw that **10% of our customers were logging in weekly**, which is pretty poor.

The framework I used: **RICE** — Reach, Impact, Confidence, Effort. I looked at how many customers each problem impacts, the size of the impact on their business, my confidence in the user research and Pendo data, and the cost (data science, engineering) for each initiative.

The result: I deprioritized the second bucket (improving the rules-based configuration system) and focused on building the proactive real-time system and improving the investigation experience based on those business cases.

**Lawrence:** Did you experience pushback? Was the org generally aligned?

**Anish:** I did have to convince people. When I brought this recommendation to my leadership team, they were pretty understanding that we needed to revamp the entire experience. Part of my story was I sized the work with my head of engineering and we quite simply didn't have capacity to do all of the tasks with the story points required for the quarter's work. I had to make a decision and a recommendation to the business: if we want to grow the business and retain as many customers as possible, here's what the data's saying and here's my take on where we should push forward.

---

**Lawrence:** Do you have a specific product decision that was made primarily based on customer direct feedback or user inputs, even if it conflicted with something you already had planned or pre-held conceptions?

**Anish:** Yeah. I'll shift gears to Forter where I owned our Forter Element product — a sub-second fraud decisioning solution for payment service providers. Think Stripe, Square, Adyen — a merchant has their hosted payment page integrated, someone's shopping online, they reach out to Forter and we respond with either approve or decline.

When I was in discovery mode and working with my initial design partners, the hypothesis — validated by their conversations — was that the user interface where our system shows business metrics (how many transactions approved, how much fraud, why was something declined) was the key value. And that thesis held up: our three initial pilot customers came into the dashboard, were regularly signing in, happy with the product.

Fast forward a couple quarters — I'm in a meeting with my go-to-market team and my head of sales says: **"We have $5 million of pipeline and these customers do not care about the dashboard or the portal."** They care about the intelligence we're surfacing but they want to bring it back into their own system. They want to provide that transparency to their end merchants. If you think about Wix or Shopify — the merchant logs into the Shopify experience. They don't want to teach this merchant to go log into the Forter Dashboard, some random enterprise software tool.

Then there was a whole discussion with our customer success team around how we're going to support all these little merchants.

The thesis changed — and I ended up shipping an **API** that would allow customers to call us for particular decisions and get a much richer set of insights that they could then customize and move into their own interface for their merchants.

**Lawrence:** Do you have a theory on why the customer tastes changed so significantly?

**Anish:** I don't think it was necessarily a change in taste. I think it was a topic that came up in the initial pilot customers, but they weren't pushing hard on "we really care about our merchant experience and want to get the data out of the system" — because the core value proposition was: we're going to give you higher approval rates (more top line revenue because the PSP has a take rate) and help you keep fraud under control via chargebacks.

As that surface area expanded and sales talked to more customers, that theme became increasingly important. Outside of just "you're going to increase our top line and bottom line" — they also care about merchant stickiness. They want to give them better experience around fraud. They don't want them to go to another vendor and build a relationship there.

---

**Lawrence:** Can you tell me about a time that you have had to move faster than you were comfortable with in order to get something to users' hands? What did get shipped, what didn't get shipped, and what the reasoning for the in and out were?

**Anish:** Can it be an example of like it wasn't exactly great? Because that's part of the issue here.

So I can talk about my experience working on a third-party partnership with a company called Ethoca. Ethoca is a company owned by MasterCard. Their value proposition is twofold:
1. They provide an early indication that a chargeback is coming in from the customer — like customer calls up Chase, Chase says this is potentially fraud, and Ethoca has built infrastructure to alert merchants or fraud vendors that this is coming in.
2. The merchant can stop the shipment of goods because they now know it's fraudulent — saving money.

I took this project over from a previous PM. Their due diligence said that from CAB (customer advisory board), **30% of our customers** were like, "hell yeah, we want this Ethoca product integrated within Forter and we're going to pay for it." There would be a revenue split where Forter would resell Ethoca's technology.

I just moved really quickly, took that hypothesis and was like, let's go. **A month into engineering build** — we'd built the front-end interface, the back-end to hook up that refund button to varying payment processors like Stripe and Adyen. We burned engineering work for about a month. My leadership team's forecasting revenue for this product.

Then I go to several customers with my BD team for deeper customer research. Once I go deeper into "hey, you said you wanted to buy this — are you still in? Are you going to resource it?" — because they needed to staff somebody to set up policies and manually click refund. **All 10 customers I spoke to were like, "things have shifted, the macro has changed, we don't need this anymore."** They didn't see the business case in chargebacks prevented vs. staffing a team to handle it.

The big learning: it's important to move quickly, but it's critical to go deep on discovery, especially if there's significant engineering cost attached.

**Lawrence:** If you had the chance to do it again, where would you spend your time?

**Anish:** There were some positives — we were able to use those early chargeback indications to adjust our fraud models and **saved the company about a million dollars a year in chargeback costs** for insured customers. So there was still value in what we'd done.

But the bigger finding: with enterprise software especially, you need to really go deep on how big of a problem this is for the customer and whether they're willing to resource it versus all the other initiatives they have. Financial institutions, merchants — they've got 30 different things rolling around. If there's not a very clear top-line uplift or bottom-line savings or operational savings, who knows what happens from one quarter to the next. And keeping them in the loop — making sure the initial hypothesis continues to be validated and they remain design partners.

---

**Lawrence:** Can you tell me about a cross-team initiative where things didn't go as planned — what did you own, what did you change?

**Anish:** During my time at Forter, I was working with our head of engineering and he had already staffed some work to a certain initiative — engineering work had started, one sprint in. My head of engineering had gotten direction from a stakeholder in their department that **reducing the latency on our portal** was a critical initiative. It surfaced through an engineer who found a way to make the portal infrastructure better and load the tool faster.

I had done sizing and work to focus on actually **reducing our time to integration** for customers. At the time it took about **eight weeks** for a customer from signing contract to being live. That eight-week timeline was mostly driven by the fact that we had a human implementation person going in, looking at data quality — with internal tooling but nothing exposed to the end customer.

Eight weeks meant we're not realizing revenue until that decision is actually happening. So I'd done initial work to figure out how to reduce that by automating some tests and displaying errors for customers to troubleshoot on their own within a sandbox environment.

I had a conflict with my engineering counterpart. He pushed back initially, but when I showed him: if we can bring this testing to life in a live dashboard for customers, we might reduce onboarding from eight weeks down to something more significant. And that's going to move booked revenue to realized revenue — one of the critical metrics our executives had lined out for the year.

He understood and we paused the portal latency work to a later quarter.

**Learnings:** Be really communicative with engineering stakeholders from the start. Help them understand the business case and tie it back to why this initiative matters. Not to say that improving portal latency wouldn't have some incremental impact — but this was a much more critical initiative.

**Lawrence:** Once the EM understood the business impact, was it a tough conversation?

**Anish:** It was tough initially. Part of it was cultural challenges — engineering wants to own the work they think is really important. I gave this feedback back up through my product leadership team and was like, "hey, we need to be very much in lockstep with our engineering counterparts and that needs to go both up and down the chain so that we're all moving in the right direction."

**Lawrence:** After you said that, did you notice any macro shifts in culture?

**Anish:** Yeah. What ended up happening was we had a more frequent product and engineering meeting. It was a remote-ish environment — R&D teams were in Tel Aviv, product team in North America. Ultimately, my head of product pushed for a meeting where at the beginning of every quarter the product leads and engineering leads got together and aligned on all initiatives, making sure everyone had their say before work starts.

---

## Anish's Questions for Lawrence

**Anish:** You focus on the Web3 and crypto portion. Can you tell me what that means?

**Lawrence:** Largely it rolls up to customers who are actively transacting on chain. You can break it down by: are you moving money on chain every day as part of your regular business operations? If yes, you fall under my universe — crypto exchanges, DeFi, custodians. Their core business is transacting on chain. Then we have the financial institutions who are moving on chain but it's a new motion for them — that's the split.

**Anish:** So concretely, is that like a Coinbase or Binance versus a JP Morgan or Deutsche Bank?

**Lawrence:** Yes. And majority of it turns into **screening and monitoring** on my side. Anyone transacting on chain is obligated to have some form of a screening scheme and transaction monitoring scheme. So we're not limited by feature sets, but practically speaking, because most of my customers start an investigation because a transaction monitoring alert fires or because a wallet screening results in something ambiguous they need to untangle — it basically ends up being wallet screening and transaction monitoring plus the investigation that follows.

**Anish:** Sounds a lot like what Forter's product does, but in the on-chain crypto space.

**Lawrence:** Yeah.

**Anish:** What are your core metrics?

**Lawrence:** As a company, a lot of focus on **ARR**. We generally have a hypothesis on where that ARR generation is going to come from — well informed by our sales team and understanding of the market, deals won, deals lost. That generates the **claims** we want to be able to make in the market.

Claims tend to last six months to a year — we want to speak to a specific thing in the market. Every quarter we set a key result. For my side, it's focused on **customer outcomes** that roll up into ARR — time to resolution for an alert, reducing false positives, discovering unalerted risk.

**Anish:** Interesting. I hear product-driven orgs, engineering-driven, sales-driven. What's your take on how you guys function?

**Lawrence:** Probably **sales-driven**, with the caveat that we have a pretty unique go-to-market team. Quite a lot come from the compliance space themselves — they have experience being users — or from national security / investigator backgrounds. So it's not traditional SaaS sales with cowboys selling what doesn't exist.

But because we have really tight customer relationships, it does end up being very sales driven. Our **CKRs** (Claims and Key Results) — we don't do OKRs, we do CKRs. The claim is framed like you'd put on a landing page or elevator pitch to a prospect. You preemptively create the marketing collateral.

Top level company has ARR goals. For the product org, we have strong hypotheses on what achieves those goals — that's our target. It follows the ARR.

**Anish:** Claims — I haven't heard that. Interesting.

**Lawrence:** I think that's uniquely us.

**Anish:** How does the product-engineering relationship look for you?

**Lawrence:** Really good. We work in the **Spotify pods model** — fully enabled pods with EM counterpart, designer, front end, back end, data. Within your little crew you have everyone you need for pretty much every project.

It leads to a really nice tight team. TRM isn't the biggest company but has a lot of specialties — there's someone with a really niche job function. It's nice having a well-defined team so you're not constantly looking for resourcing. You have your own house and can run it how you want as a PM. You have your goals, your team — and beyond that there isn't a lot of oversight or permission-giving unless you want it.

I've been able to work with the same group since I started at TRM last year. You build good relationships and understand people's strengths — what projects get them switched on.

**My pod has a team of about 12.** We do max three things because otherwise it turns into a bunch of individual work.

**Anish:** Are you pushing any code?

**Lawrence:** Yeah. TRM has invested very heavily in our AI tooling. I took a "learn to code" iOS course way back — I'm not writing code. But I've been in a customer call where they've complained about a nit, and I've been able to chat through it, get it fixed, and **push a PR while chatting with them.**

It's not just using Claude — we've invested in all our tooling. It's very code-aware, aware of our niche, blockchains, how weird and variable they are, all the specific lingo. So it's not just coming in and using Claude cold.

It's totally shaken things up for me as a PM — in a good way, but all my old habits don't work. Like saving little gimmes or easy tickets. I don't have those anymore — I'm just doing them myself.

**Anish:** Cool. Well, it was super helpful.

**Lawrence:** Awesome to meet you. Thanks so much.

**Anish:** Cheers. Have a good one.
