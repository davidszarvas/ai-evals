# Module 5 · Coverage Matrix · AI Voice Agent

## Coverage Row

| Product | Hallucination Rate | Fairness | Latency | UX Trust | Robustness |
|---|---|---|---|---|---|
| AI Voice Agent | ❌ Gap | ⚠️ Partial | ❌ Gap | ✅ Covered | ✅ Covered |

## What Runs Today

- An eval gate tests its answers to 300 billing questions before every release.
- A supervisor listens to 10 random calls a week for tone.
- A drift monitor alerts when callers start asking about things the agent wasn’t tested on.

## Accepted Gap

**Latency.** Since the LLM has to read through all previous questions and evaluate drifting as well, a small delay / latency can be acceptable from our users as long as we are showing that the LLM is working.

We’ll look again: If the latency would frustratingly long for every question to  answer (more then 5 sec)

## Critical Gap

We’ve flagged Hallucination Rate as the most critical gap for AI Voice Agent because, it handles billing therefore a misinterpreted or misleading infromation could cause reputational harm and would have revenue impact as well.

## After the Pressure Test

It changed my mind a bit about latency, since this a call there is no spinner, so even a 5 sec waiting time of silence can be too long because a caller could assume the call dropped.
My plan wasn't specific enough. 
