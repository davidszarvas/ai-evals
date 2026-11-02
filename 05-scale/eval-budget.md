# Module 5 · Eval Budget · Ascend IQ

**Quarterly budget cap:** $200,000
**Online eval spend:** $85,000 (1 of at most 3 online evals)

## Budget

| Failure | Trust metric | Risk | Level | Cost |
| --- | --- | :---: | :---: | ---: |
| Data Fabrication | Hallucination Rate | P0 | Online eval | $85,000 |
| Context Specificity | Robustness | P1 | Periodic audit | $7,000 |
| Overconfident Tone | UX Trust | P1 | Periodic audit | $6,500 |
| Data Bias | Fairness | P2 | Code-based check | $2,750 |
| Slow Answers | Latency | P3 | Code-based check | $1,250 |

## Downgrades

### Periodic audit · Context Specificity (Robustness · P1)
- **Cheaper check:** Weekly audit review 100 answers manually
- **Why it’s enough:** Even though it can be annoying to not get the exact answer but users can still clarify their questions 

### Periodic audit · Overconfident Tone (UX Trust · P1)
- **Cheaper check:** Weekly LLM a judge against guidelines and golden dataset eval is sufficient 
- **Why it’s enough:** This won't cause a reputation damage, and we can catch the discrepancy with LLM as a judge

### Code-based check · Data Bias (Fairness · P2)
- **Cheaper check:** weekly check of % of US and APAC data and flag if a bias happens. Threshold is 5%
- **Why it’s enough:** This is a P2 gap, and it is not crucial unless the user specifically as for APAC data

### Code-based check · Slow Answers (Latency · P3)
- **Cheaper check:** Continuous alert on p95 and p99
- **Why it’s enough:** If it passes the p95 test than it is acceptable

