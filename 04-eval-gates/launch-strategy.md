# Module 4 · Launch Strategy · Ascend IQ Copilot

## 4.0 Release Criteria

| Gate | Failure | Metric | Threshold | Dataset | Method | Runs at |
|---|---|---|---|---|---|---|
| Hard | Outdated (#HALLUCINATION) | % of answers that ask about the pricing and the answer an | The exact number required to ship | Ascend IQ golden set | Code-based check | Staging |
| Soft | Row 5 · Hallucination: lists an unconfirmed speaker as confirmed | % of answers that contradicts the information | 90% | Ascend IQ golden set | LLM judge | Staging |
| Advisory | Row 17 · Tone: slang detected | Nr of slang, inappropriate words | 0% since out rand voice states: confident, professional, expert. Avoid slang.states | Ascend IQ golden set | Human review | Staging |

## CI Gate Request for Engineering

- **Hard gate · Outdated (#HALLUCINATION).** Check: the code-based check, run on the Ascend IQ golden set at Staging. Measures: % of answers that ask about the pricing and the answer an. Passes when: The exact number required to ship. On a fail: block the merge.
- **Soft gate · Row 5 · Hallucination: lists an unconfirmed speaker as confirmed.** Check: the LLM judge, run on the Ascend IQ golden set at Staging. Measures: % of answers that contradicts the information. Passes when: 90%. On a fail: pause the release until the PM signs off on an override.
- **Advisory gate · Row 17 · Tone: slang detected.** Check: the human review, run on the Ascend IQ golden set at Staging. Measures: Nr of slang, inappropriate words. Passes when: 0% since out rand voice states: confident, professional, expert. Avoid slang.states. On a fail: post a warning, and don't block.

## Mitigation Plan · Soft Gate

If our Soft gate fails, do Beta Label and test it and validate that it can maintain the above 90% accuracy before removing the label.
