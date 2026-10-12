# Experiment Pitfalls: How A/B Tests Mislead You

A simulation study of three common ways experiments go wrong (underpowered designs, peeking at results early, and slicing into many segments), using one running example: a checkout-button redesign. **All data is simulated**, so the true effect is known and each method can be checked against it. This demonstrates method, not a real business result.

## What it covers
- Sample-size planning from a power calculation (baseline 10%, minimum detectable lift +1.5 pp)
- Sample ratio mismatch (SRM) check
- Two-proportion z-test, 95% confidence interval, relative lift, and Cohen's h
- Simulation check of the design: empirical power 79.3% (target 80%), false-positive rate 5.1% (target 5%)
- Peeking: stopping at the first significant of 10 looks raised false positives from 5% to 19.3%
- Multiple segments: with no true effect in any of 20 segments, 4 showed raw p < 0.05 in this run (about 1 expected); after Holm correction, 0 of 20. Chance of at least one false "win": 64%

## Key result
Observed lift +1.19 pp (95% CI +0.16 to +2.23 pp), against a true simulated lift of +1.5 pp. The interval covers the truth; the point estimate alone would have understated it. Simulation figures vary slightly between runs because of random draws.

## Limitations
Simulated data; assumes independent users, a fixed horizon, and a single pre-specified metric. A real test would also check novelty effects, run for whole weeks, and monitor guardrail metrics.

## Run it
```
pip install numpy pandas scipy matplotlib jupyter
jupyter notebook experiment_pitfalls.ipynb
```
