# Cost-Effectiveness of Continuous Glucose Monitoring vs. Blood Glucose Monitoring in Non-Insulin-Treated Type 2 Diabetes

A reproducible Markov cost-effectiveness model in R/Quarto, with the treatment effect derived from an independent meta-analysis and scaled to clinical risk using a published dose-response relationship (UKPDS 35).

## Summary

CGM's effect on HbA1c (MD −0.42%, from [companion meta-analysis](https://github.com/said-adjao/cgm-meta-analysis)) was translated into a 17.6% relative risk reduction in microvascular complications using UKPDS 35's dose-response relationship (37% RRR per 1% HbA1c). Base-case ICER: **$446,000/QALY** — above US thresholds, and less favorable than a comparable direct-acting therapy (see [SGLT2i cost-effectiveness model](https://github.com/said-adjao/sglt2-cost-effectiveness)). Robust to effectiveness uncertainty (PSA: ~1.5% probability cost-effective at $150k/QALY); driven by price and the indirectness of the surrogate-outcome pathway.

## Methods
- Three-state Markov model (Stable/Complication/Dead), 20-year horizon, 3% discounting
- Treatment effect: meta-analysis MD → UKPDS 35 scaling (exponential dose-response)
- One-way SA (UKPDS relationship, CGM price) + PSA (5,000 simulations, Beta/Gamma/Normal distributions)

## Files
- `cgm_cea_report.qmd` / `.html` — full reproducible analysis

## Key methodological note
This model demonstrates translating a **surrogate outcome** into health economic states via a published risk equation — a more advanced technique than applying a directly-reported trial hazard ratio.

---
*Author: Said Adjao*
