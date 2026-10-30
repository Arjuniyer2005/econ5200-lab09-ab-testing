# econ5200-lab09-ab-testing
# ECON 5200 — Lab 9: Diagnosing Experimental Failures in A/B Testing

## Project Overview

In this lab, I explored common problems in A/B testing and how they can lead to misleading results. I diagnosed errors in statistical analyses, examined how interference affects treatment effects, and compared Bayesian and frequentist approaches to experimentation.

## Methodology

- **CUPED:** Identified and corrected three bugs in a variance-reduction calculation.
- **Sample Ratio Mismatch:** Used chi-squared tests to detect imbalances between treatment and control groups.
- **SUTVA Violations:** Simulated a marketplace where buyers compete for limited inventory, creating interference between treatment and control groups.
- **Bayesian A/B Testing:** Used Beta-Binomial models to estimate conversion probabilities, expected losses, and shipping decisions.
- **Sequential Testing:** Simulated repeated significance testing to examine how checking results early increases false positives.

## Key Findings

- **CUPED:** Correcting the analysis reduced the standard error from 0.1539 to 0.0641, achieving an 82.7% variance reduction.
- **Sample Ratio Mismatch:** A 0.60 percentage-point imbalance among 100,000 users produced a chi-squared statistic of 14.40, while a much smaller 0.05-point imbalance among 20 million users produced a larger statistic of 20.00.
- **SUTVA:** Marketplace interference caused the naive treatment effect (0.1861) to overstate the global rollout effect (0.1428) by 23.3%.
- **Bayesian Testing:** The probability that variant B outperformed A was 88.66%, with an expected loss of 0.000473 from shipping B. However, the decision rule recommended against shipping B. The permutation test returned a p-value of 0.2302.
- **Sequential Testing:** Repeatedly checking significance increased the false-positive rate to 32.4%, compared with 5.3% when testing only at the end.

## Tools Used

Python, NumPy, Pandas, SciPy, Matplotlib, and Google Colab.
