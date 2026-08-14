---
title: DOT Methodology & Diagnostics
description: Data preparation, chronological validation, external-variable testing, forecast design, and limitations for NYC DOT operating spending.
---

<div class="page-hero">
  <div class="section-inner">
    <div class="eyebrow">DOT technical report</div>
    <h1>Methodology, Validation &amp; Forecast Risk</h1>
    <p class="subtitle">The evidence behind the DOT spending outlook—from operating-scope controls to expanding-window backtesting.</p>
  </div>
</div>

<article class="prose" markdown="1">
<a class="back-link" href="{{ '/' | relative_url }}#dot">← Back to DOT findings</a>

## Data Sources & Operating Scope

The analysis combines annual NYC DOT adopted and modified operating budgets with actual operating expenditures. National CPI, NYC-area CPI, inflation, and gasoline-price series provide economic context and external-variable tests.

<a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_budget_vs_actual.png' | relative_url }}" data-lightbox aria-label="Open DOT historical budget chart"><img src="{{ '/assets/images/dot/dot_budget_vs_actual.png' | relative_url }}" alt="DOT adopted budget, modified budget, and actual operating spending over time"></a>

Spending is kept at a consistent operating scope. Capital and construction activity should not be mixed with recurring operating expenditures when training or evaluating the forecast.

## Data Preparation Controls

1. **Agency filtering.** Budget and spending records are consistently restricted to the Department of Transportation.
2. **Operating-spending filtering.** Spending is aligned to DOT operating-budget codes, with legitimate payroll records retained separately where historical formatting differs.
3. **Completed fiscal years.** FY2011–FY2026 form the completed annual actual-spending history.
4. **Partial FY2027 actual.** FY2027 recorded actual spending is incomplete. It is excluded from completed-year growth, utilization, relationship, and model-performance metrics.
5. **No automatic outlier deletion.** Unusual fiscal years remain visible and are treated as potential structural or policy events.

## Exploratory Analysis

EDA evaluates adopted-versus-modified budgets, actual execution, annual growth, utilization, budget variance, modification rates, and nominal-versus-real spending. Economic variables are interpreted cautiously: correlation does not establish causation.

Gas prices are strongly related to fuel-specific spending (**r = 0.866; R² = 0.750**) but weakly related to total DOT operating spending. That distinction prevents a narrow operating driver from being overstated as an agency-wide predictor.

## Forecasting Design

The primary beginning-of-year model is:

> **Actual Spending = Lag-1 Actual Spending + Current Adopted Budget**

The specification has a practical interpretation. Prior-year actual spending captures recurring payroll, contracts, maintenance, and operating persistence. The current adopted budget captures present policy expectations using information available at the start of the fiscal year.

The comparison set remains intentionally explainable:

- Naive prior-year persistence
- Linear time trend
- Lag-1 actual-spending regression
- Lag-1 plus current adopted budget
- Lag-1 plus modified budget, labeled **in-year only**
- Lag-1 plus adopted budget and one lagged external variable at a time
- Fixed low-order ARIMA benchmark

No random forest, boosted-tree, neural-network, or high-dimensional approach is used for this small annual sample.

## Chronological Backtesting

The main evaluation uses expanding-window one-step-ahead forecasts from FY2019 through FY2026. Each test year is predicted only from information that precedes it. A random train/test split is avoided because it would break the timing of the planning problem and could allow future years to influence earlier predictions.

<a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_backtest_actual_vs_predicted.png' | relative_url }}" data-lightbox aria-label="Open chronological DOT backtest chart"><img src="{{ '/assets/images/dot/dot_backtest_actual_vs_predicted.png' | relative_url }}" alt="DOT actual operating spending and expanding-window backtest predictions"></a>

The selected model achieves:

- **MAPE:** 3.44%
- **MAE:** approximately $41.8M
- **RMSE:** approximately $60.2M
- **Out-of-sample R²:** 0.902
- **MAPE improvement versus naive persistence:** 42.5%

MAPE is the primary selection metric. MAE communicates the typical dollar miss, RMSE emphasizes larger misses, and out-of-sample R² is supporting context—not a substitute for forecast error.

## External-Variable Testing

National CPI, NYC-area CPI, lagged inflation, and lagged gas prices were tested using the same chronological logic. The base Lag-1 + Adopted model produced **3.44% MAPE**, compared with **4.02%** after adding national CPI and **4.04%** after adding NYC CPI.

<a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_cpi_model_predictions.png' | relative_url }}" data-lightbox aria-label="Open base and NYC-CPI prediction comparison"><img src="{{ '/assets/images/dot/dot_cpi_model_predictions.png' | relative_url }}" alt="Actual DOT spending compared with base and NYC-CPI model predictions"></a>

Adding a predictor can improve in-sample fit while worsening out-of-sample performance. The economic variables remain valuable for context and real-dollar interpretation, but they are not forced into the final forecast.

## Near-Term Forecast & Long-Range Projections

The beginning-of-year Lag-1 + Adopted model forecasts **$1.522B** of FY2027 actual operating spending. FY2028 and FY2029 adopted-budget inputs are unavailable, so they are not invented. Instead, a separate, simple long-range time-series approach produces model-based actual-spending projections of **$1.593B** and **$1.668B**.

<a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_actual_forecast.png' | relative_url }}" data-lightbox aria-label="Open DOT spending outlook"><img src="{{ '/assets/images/dot/dot_actual_forecast.png' | relative_url }}" alt="Historical DOT actual spending and FY2027 through FY2029 forecasts with uncertainty"></a>

Modified Budget is forecast separately because it is an authorization measure, not actual expenditure. The modified-budget projections are **$1.706B for FY2028** and **$1.772B for FY2029**.

## Model-Selection Criteria

The final model is selected using:

1. Low chronological out-of-sample MAPE
2. Low MAE and RMSE
3. Stability across forecast years
4. Improvement over naive persistence
5. Information available at the forecast date
6. Business logic and explainability
7. Preference for simplicity when performance is approximately tied

## Limitations & Forecast Risk

- Only approximately **16 completed annual DOT observations** are available.
- Lagging reduces the effective modeling sample further.
- FY2027 actual spending is partial and excluded from completed-year training and evaluation.
- Unexpected policy, infrastructure, federal-funding, labor, weather, emergency, or economic shocks can alter spending.
- FY2028–FY2029 projections carry more uncertainty than the FY2027 near-term forecast.
- Historical relationships can change over time.
- Forecast intervals are planning ranges, not guarantees.
- Agency-total models can obscure category-specific relationships, such as fuel prices and fuel expenditure.

<div class="callout"><strong>Decision rule:</strong> treat the forecast as a decision-support tool, not a guaranteed budget outcome. Prefer the simplest model that performs well chronologically, beats persistence, uses timely information, and has defensible business logic.</div>

</article>
