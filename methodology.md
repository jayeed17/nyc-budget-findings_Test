---
title: DOT Methodology & Diagnostics
description: Data preparation, validation, model comparison, and limitations for the NYC DOT operating-spending forecast.
---

<div class="page-hero">
  <div class="section-inner">
    <div class="eyebrow">DOT technical report</div>
    <h1>Methodology, Model Comparison &amp; Diagnostics</h1>
    <p class="subtitle">The evidence behind the FY2027 forecast—from scope corrections to chronological backtesting.</p>
  </div>
</div>

<article class="prose" markdown="1">
<a class="back-link" href="{{ '/' | relative_url }}#dot">← Back to DOT findings</a>

## Budget & Spending EDA

<img src="{{ '/assets/images/budget_eda.png' | relative_url }}" alt="DOT adopted, modified and actual spending, growth, and utilization charts">

The completed-year series separates budget plans from actual operating execution. FY2027 is retained as budget context but excluded from completed-year growth and utilization.

<img src="{{ '/assets/images/spending_eda.png' | relative_url }}" alt="DOT budget variance, modification rate, and nominal versus real spending charts">

Nominal and CPI-adjusted spending are shown together so price growth is not mistaken for expanded operating capacity.

## Data & Scope Corrections

1. **FY2022 multi-agency contamination.** The budget source contained roughly 150 other NYC agencies. Every year is consistently filtered to `Agency == "Department of Transportation"`.
2. **Operating-versus-capital mismatch.** Checkbook spending contains construction and other capital transactions while the budget series is operating expense. Spending is retained only when its budget-code prefix appears in DOT’s operating-budget data; `Payroll Summary` is retained separately because early legitimate payroll records use a different format.
3. **Partial FY2027.** Recorded actual spending is only **9.9%** of modified budget. It is excluded from every completed-year KPI, relationship, and model-performance statistic.

No unusual year is automatically discarded. Scope, timing, and known structural changes are explained instead.

## Forecasting Design

The main comparison uses an **expanding-window one-step-ahead backtest** from FY2019 through FY2026. A recent holdout trains through FY2023 and reports FY2024–FY2026 separately. A random train/test split is avoided because it would allow future years to inform earlier predictions.

The tested models are intentionally explainable:

- Naive prior-year persistence
- Linear fiscal-year trend
- Lag-1 actual-spending regression
- Lag-1 plus current adopted budget
- Lag-1 plus modified budget, labeled **in-year only**
- Lag-1 plus adopted budget and one lagged external variable at a time
- Fixed low-order ARIMA(1,1,0) benchmark

The selected Lag-1 + Adopted model achieves **3.44% MAPE**, **$41.8M MAE**, **$60.2M RMSE**, and **0.902 out-of-sample R²**. Its MAPE is **42.5% lower** than naive persistence.

<img src="{{ '/assets/images/validation_performance.png' | relative_url }}" alt="DOT model comparison using MAPE, RMSE, MAE, and out-of-sample R-squared">

MAPE is the primary metric. MAE communicates the typical dollar miss, RMSE emphasizes large misses, and out-of-sample R² is supporting context—not a substitute for chronological forecast accuracy.

## Why Lag-1 Makes Business Sense

DOT payroll, maintenance, contracts, and operations recur from year to year. Prior-year actual spending is therefore a practical baseline rather than an abstract statistical feature.

<img src="{{ '/assets/images/lag1_relationship.png' | relative_url }}" alt="Prior-year versus current-year DOT operating spending scatter plot">

The Lag-1 Pearson correlation is **0.980**, with a simple relationship R² of **0.961**. This is strong historical association, not proof of causation; the expanding-window test determines whether it forecasts well.

## Forecast Diagnostics

<img src="{{ '/assets/images/forecast_diagnostics.png' | relative_url }}" alt="DOT actual versus predicted, error, percentage error, and residual diagnostics">

Diagnostics show performance year by year rather than hiding variation inside one score. External-variable models remain visible even though lagged CPI, inflation, and gas prices did not improve the selected total-spending model.

<img src="{{ '/assets/images/final_forecast.png' | relative_url }}" alt="Historical DOT actual operating spending and FY2027 forecast with uncertainty interval">

The final model forecasts **$1.522B** for FY2027, with an approximate 95% planning range of **$1.396B–$1.647B**. FY2028–FY2029 are not forecast because future adopted-budget inputs are unavailable.

## Limitations

- The annual sample is small, especially after lagging; metrics should be interpreted as applied planning evidence, not universal proof.
- Correlation is not causation. CPI can proxy for time, while gas-price effects may exist only within the small fuel category.
- FY2011–FY2016 budget totals come from OMB summaries; FY2016 modified budget is unavailable.
- The interval is an empirical planning range based on historical errors, not a guarantee.
- Policy changes, emergencies, labor settlements, and new programs may produce outcomes outside the historical pattern.

<div class="callout"><strong>Decision rule:</strong> prefer the simplest model that performs well out of sample, beats persistence, uses information available at forecast time, and has defensible business logic.</div>

</article>
