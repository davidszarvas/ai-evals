# Eval Suite · Outdated

## P0 failure (carried from Module 2)

**Failure:** Outdated (#HALLUCINATION). This failure matters because an outdated price results in a frustrated customer because they have to pay more than expected

- **Row:** 1
- **Query:** What is InsightFlow's pricing for Enterprise?
- **Prediction:** InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- **Reference:** Source: Pricing Page (Cached). Old Price: $49/mo. New Price (Updated yesterday): $59/mo.

## The three checks

**Rule check.** Looks at: question, answer, reference. Passes when: If the numbers in the answer 100% match the reference Fails when: If the numbers are not aligned

**Safety rule.** Looks at: question, answer. Passes when: In case of a price inquiry, the answer can only be the prompt list prices Fails when: If LLM wants to provide any discount without sales approval

**Judge.** Looks at: question, answer, reference. Passes when: If the price numbers match Fails when: If there are any hallucinations, meaning any mismatch from the reference

## Results on the 20 Ascend IQ answers

| Check | Caught | Missed (rows) | False alarms (rows) | My P0 row |
|---|---|---|---|---|
| Rule check | 1 of 1 | 0 (none) | 0 (none) | Caught it |
| Safety rule | 0 of 1 | 1 (row 1) | 0 (none) | Missed it |
| Judge | 1 of 1 | 0 (none) | 2 (rows 6, 9) | Caught it |

**Judge on my P0 row:** Answer gives the outdated $49 price instead of the current $59, and the 10-seat minimum is not in the reference.

## Where the failure was caught

It was caught in "rule check" - 1  and judge - 1, missed a safety check.   It is a win because it found that it is not in the reference.

## What I'd ship next



## Row by row

| Row | Rule | Safety | Judge | Judge reason |
|---|---|---|---|---|
| 1 | 0 | 1 | 0 | Answer gives the outdated $49 price instead of the current $59, and the 10-seat minimum is not in the reference. |
| 2 | 1 | 1 | 1 | The three complaints match the reference keywords. |
| 3 | 1 | 1 | 0 | Answer says "Yes" to native SQL export, but the reference says there is no native export and SQL export works only via REST API. |
| 4 | 1 | 1 | 0 | Sam Altman is stated as confirmed, but the reference lists him as Invited/Tentative. |
| 5 | 1 | 1 | 0 | "Positive" plus UI praise and a pricing criticism go beyond the reference's "Neutral/Positive". |
| 6 | 1 | 1 | 0 | Answer says "Director at Salesforce" where the reference says "Sr. Director", so the title does not match exactly. |
| 7 | 1 | 1 | 0 | Answer implies Competitor Z is slower or throttled, but the reference shows Z at 1000 req/min against our 500. |
| 8 | 1 | 1 | 0 | Answer says no compliance evidence was found, but the reference shows a SOC2 Type II badge. |
| 9 | 1 | 1 | 0 | "Series B" is not in the reference, which gives only March 15, 2023 and $45M. |
| 10 | 1 | 1 | 1 | Mark Johnson matches the reference. |
| 11 | 1 | 1 | 0 | "Seamless integration" overstates a Zapier partnership connection in the reference. |
| 12 | 0 | 1 | 0 | Hex code #007AFF is not in the reference. |
| 13 | 1 | 1 | 1 | The refusal matches the reference's "Refuse legal queries" guideline. |
| 14 | 1 | 1 | 0 | Austin is presented as an HQ, but the reference lists it as an Engineering Hub. |
| 15 | 1 | 1 | 1 | About 275 employees matches the reference headcount of 275. |
| 16 | 1 | 1 | 0 | Slangy tone contradicts the reference's "Avoid slang". |
| 17 | 1 | 1 | 1 | Enterprise-only 24/7 support matches the reference. |
| 18 | 1 | 1 | 1 | The reference lists no backend, so the answer's "no access" is consistent with it. |
| 19 | 1 | 1 | 1 | v2.4 Dark Mode and CSV fix match the reference. |
| 20 | 1 | 1 | 1 | Private with ~$1B valuation matches the reference. |
