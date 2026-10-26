# Eval Spec · Ascend IQ

Paste the reply from the Module 3 Lab Guide (Activity 2) over this file once you've edited the messages, then commit.

| Part | Spec |
|---|---|
| Target risk |Outdated (#HALLUCINATION), an output risk |
| Evaluator |The rule check from Lab 1 |
| Threshold |The exact number required to ship (the spec sets no figure yet). Supported by: the rule check caught 1 of 1, the safety rule caught 0 of 1, the judge caught 1 of 1. |
| Business stakes |Annoyed customer, lost deal, and potential revenue loss |
| Owner |Product and pricing manager |

## Messages

**Engineering · acceptance criteria:** For each answer, compare every number in it to the verified reference. Return 1 (pass) only if all numbers match the reference exactly, and return 0 (fail) if any number differs, is outdated, or is missing from the reference; block every answer that scores 0, and ship only when the pass rate meets the threshold, which the spec has not yet set.

**Design · what the user sees:** When the check blocks an answer, the user sees no price, only a short note that the current price could not be confirmed and that the Product and pricing manager will follow up. The note must never show the blocked number.

**Leadership · risk and return:** This check stops the agent from quoting an outdated price, which leads to an annoyed customer, a lost deal and potentially lost revenue. It is worth the cost because the rule check caught 1 of 1 real cases, while the safety rule caught 0 of 1, so it is the one check we can rely on for this risk.
