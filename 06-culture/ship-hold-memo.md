# Ship-or-Hold Memo · Ascend IQ

> **Decision:** HOLD

## The Answer

The P0 Outdated failure happened in 8/20 answers, and the hard gate that should block it has no ship threshold, so nothing can pass it yet.

## The Arguments

### 1. Reliability gaps are costing enterprise trust:

Evidence: Robustness evals fail on 12% of edge cases.

### 2. Accuracy issues put key accounts at risk

Evidence: Three enterprise clients flagged made-up insights

## Next Step · Decision Needed

I recommend we hold the Ascend IQ Copilot release until the pricing check has a ship threshold, to protect customer trust and revenue.

1. Customer and revenue risk: Outdated pricing, our P0 failure, appeared in 8/20 answers. One answer quoted $49/user/month against the current $59.
2..Our release gate can’t stop it yet: The hard gate has no ship threshold, so its pass rate is not measured yet. The safety rule also caught 0 of 1 on the P0 row.
3. The fix is funded and ready: $85,000 of the $200,000 quarterly cap is already committed to the P0 online eval. The rule check caught the P0 row (1 of 1) with 0 false alarms.

Decision needed: Please approve (a) holding the release and (b) setting the hard-gate pass-rate threshold for outdated pricing.
