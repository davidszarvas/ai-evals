# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).

## 1. Product Strategy, The Context

**Who it's for:** VP-level strategists and product leaders at Fortune 500 companies who pay upward of $50,000 a year for verified market intelligence.

**What they use it for:** Asking plain-language questions, like “Compare the pricing models of Stripe and Adyen,” and getting answers in seconds instead of digging through the platform.

**What's at stake:** Engagement is dropping, Q4 retention is at risk, and the CPO wants Ascend IQ live for the top 50 enterprise accounts next month. One poor answer to the wrong client can do lasting damage to the relationship.

## 2. Measurements, The Execution

**User promise.** For VP-level Enterprise Strategists, Ascend IQ promises to deliver verified, citation-backed competitive intelligence in under 5 seconds so that they hit their Q4 roadmap milestones without manual data digging.

**Top 3 trust metrics:**
- **Latency**, Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **UX Trust**, Subjective predictability and consistency over time.

**Why these three:** • Hallucination, VP-level clients pay $50k+ for verified data; one fabricated stat ends the contract.
• Latency, <5s response is the only thing that beats manual digging.
• Fairness, consistent factual quality across English, German & French underpins our European Enterprise expansion.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Latency
We prioritize Hallucination Rate over Latency because Ascend IQ serves VPs making $1M+ strategic decisions; a single fabricated competitor stat ends a $50k contract, whereas a 3-second wait is the cost of doing business at Enterprise-grade integrity.

### Trade-off 2 · Hallucination Rate ↔ UX Trust
We prioritize Hallucination Rate over UX Trust because Ascend IQ serves VPs making $1M+ strategic decisions; a single fabricated competitor stat ends a $50k contract, whereas an honest fallback, or insufficient answer, is "just" slightly annoying, but still can build trust.

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._