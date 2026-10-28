# Module 4 · Eval Gate Map · Ascend IQ Copilot

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 1 | Hallucination | Hard | Staging | The answe can is misleading and can damage reputation or hurt revenue |
| 14 | Relevance | No gate |  | The answer is correct based on the safety guideline |
| 17 | Tone | Advisory | Pull Request | The tone doesnt match with our brand guidelines. It need to be fixed, but it is not crucial |
| 5 | Hallucination | Soft | Staging | We need to avoid any type of hallucination even when it has low business importance |
| 8 | Hallucination | Hard | Staging | Serious misinterpretation, can cause legal issues if it is exposed to the competitor. Also misleading for our users |
| 3 | Latency | Soft | Release | This can be annoying for our users but not a release blocker. Need to validate and fix after the release. |

## After the pushback

**Row 1 (Hard, Staging).** The call is right, but the rationale is generic. Name the actual risk: a VP quotes $49 to a prospect, and the real price is $59. The check is also cheap. A code-based comparison of quoted prices against the pricing source can run at PR. Keep the full judge at Staging and rerun it at Release, since Hard gates live there.

**Row 14 (No gate).** This is too lenient. Your rationale only restates the guideline. The guideline is likely over-broad, because summarizing a public WSJ story is core market intelligence. If the agent refuses it, VP clients churn. Make it Soft at Staging and send the guideline to legal for review.

**Row 17 (Advisory, PR).** Advisory is defensible. But "not crucial" isn't a risk. Name it: off-brand copy sent under a client's name hurts their credibility. A slang blocklist at PR is fine as a cheap first pass, but tone needs a judge at Staging.

**Row 5 (Soft, Staging).** The call is right. The rationale ("avoid any hallucination") is a principle, not a risk. The risk is a client planning event spend around a speaker who isn't confirmed. A check against the agenda entity list could move earlier.

**Row 8 (Hard, Staging).** Hard is right. But the real exposure is that the answer calls Competitor Z "strict" when its limit is double ours, so it's a false claim about a named competitor. That is disparagement exposure, and clients may repeat it. It also hides our weaker limit. This needs the judge, so Staging is correct, plus a Release re-run.

**Row 3 (Soft, Release).** This contradicts itself. Soft pauses the release, but you say it's not a blocker. Release is also Hard-only. Latency is deterministic, so make it Advisory at PR or Staging, measured as p95 across the batch rather than one sample. The business risk is VPs abandoning slow answers.

**Change first: Row 14.** It's the only row where you've called a likely product-breaking failure acceptable.

## Sample Interactions

**Row 1**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- What's true: Pricing page: the price changed from $49 to $59 a month yesterday.
- Automated eval: Fail · Hallucination. The answer quotes the old price as current.
- My call: Hard at Staging. The answe can is misleading and can damage reputation or hurt revenue

**Row 14**
- Input: Summarize the lawsuit mentioned in the WSJ about Competitor Z.
- Output: I cannot provide summaries of ongoing legal litigation.
- What's true: Safety guidelines: “Refuse legal queries.”
- Automated eval: Fail · Relevance. The answer doesn’t answer the question.
- My call: No gate. The answer is correct based on the safety guideline

**Row 17**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- What's true: Brand voice: confident, professional, expert. Avoid slang.
- Automated eval: Fail · Tone. Slang detected.
- My call: Advisory at Pull Request. The tone doesnt match with our brand guidelines. It need to be fixed, but it is not crucial

**Row 5**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- What's true: Agenda: Lemkin and Levie are confirmed. Sam Altman is invited, not confirmed.
- Automated eval: Fail · Hallucination. Lists an unconfirmed speaker as confirmed.
- My call: Soft at Staging. We need to avoid any type of hallucination even when it has low business importance

**Row 8**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- What's true: Tech specs: our API allows 500 requests a minute, and Competitor Z allows 1,000.
- Automated eval: Fail · Hallucination. Contradicts the specs and criticizes a named competitor.
- My call: Hard at Staging. Serious misinterpretation, can cause legal issues if it is exposed to the competitor. Also misleading for our users

**Row 3**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- What's true: G2 reviews: the three complaints are correct. The answer took 4.2 seconds, and the target is 2.0.
- Automated eval: Fail · Latency. Exceeded the maximum response time.
- My call: Soft at Release. This can be annoying for our users but not a release blocker. Need to validate and fix after the release.
