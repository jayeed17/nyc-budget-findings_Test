---
title: Methodology & Diagnostics — NYC DOT Budget Analysis
---

# Methodology, Model Comparison & Diagnostics

[← Back to findings](index.html)

Full detail behind the headline numbers on the [findings page](index.html): the exploratory charts, the two data corrections, every candidate forecasting model, and the limitations of each result.

## Budget & Spending EDA

<img src="assets/images/budget_eda.png" alt="Adopted vs modified vs actual spending, year-over-year growth, and budget utilization">

*Adopted/modified/actual spending, year-over-year growth, and modified-budget utilization, FY2011–2027.*

<img src="assets/images/spending_eda.png" alt="Budget variance, revision rate, and nominal vs CPI-adjusted actual spending">

*Budget variance against adopted and modified plans, the in-year revision rate, and nominal vs. CPI-adjusted ("real") spending — the evidence behind the inflation finding.*

## The Data & Corrections

Two scope errors in the raw source files were found and corrected before any aggregation:

1. **FY2022 multi-agency contamination.** Every fiscal year's budget source file was pre-filtered to DOT rows only — except FY2022, which shipped with **~150 other NYC agencies' rows mixed in** (Health, Education, Police, pension and reserve funds, and more), inflating FY2022 Adopted from a plausible ~$1.3B to an implausible ~$100.6B. **Fix:** every budget row is filtered to `Agency == "Department of Transportation"`, applied uniformly across all years so the correction is consistent rather than a one-off patch.
2. **Expense-vs-capital scope mismatch.** The raw spending (Checkbook) file mixes operating-expense and capital transactions (construction, bridge hazard-mitigation project codes, etc.), while the budget file is expense-only. **Fix:** spending rows are kept only when their Budget Code matches a code that actually appears in DOT's own operating budget file (`Payroll Summary` is retained separately since its early records don't share that code format but are legitimate operating expense).

FY2027 — barely underway at analysis time (actual = **9.9%** of modified budget) — is retained for context but excluded from every completed-year KPI, correlation, and validation result.

## Forecasting Approach

Models are evaluated strictly out of sample: an **expanding-window backtest** starting FY2019 and rolling one year at a time through FY2026, plus a simple holdout (train through FY2023, test FY2024–FY2026). No random splits — every test respects fiscal-year chronology, using only information available at the start of a forecast year.

Nine candidate specifications were compared: a plain year trend, naive prior-year persistence, combinations of lagged actual spending with the adopted or modified budget, lagged CPI/inflation/gas price, and a fixed ARIMA(1,1,0) benchmark.

<img src="assets/images/validation_performance.png" alt="Bar charts comparing MAPE, RMSE, MAE, and out-of-sample R-squared across candidate forecasting models">

*Out-of-sample MAPE, RMSE, MAE, and R² across all nine candidate models — **Lag-1 + Adopted** wins on every metric; none of the lagged external variables (CPI, inflation, gas) improve on it.*

The selected model — prior-year actual combined with the current adopted budget — achieves **3.44% MAPE**, **$41.8M MAE**, **$60.2M RMSE**, and **0.902 out-of-sample R²**, a **42.5%** MAPE improvement over naive persistence (repeating last year's actual unchanged). That comparison against the naive baseline is the honest test, not the raw accuracy score alone.

<img src="assets/images/lag1_relationship.png" alt="Scatter plot of prior-year actual spending vs current-year actual spending">

*Prior-year actual vs. current-year actual, FY2012–FY2026 (r = 0.980) — the persistence relationship the winning model leans on.*

<img src="assets/images/forecast_diagnostics.png" alt="Backtest diagnostics: actual vs predicted spending, prediction error by year, absolute percentage error, and residual plot">

*Backtest diagnostics for the selected model — errors are small, don't trend over time, and show no strong residual pattern.*

## Limitations

- **Correlation is descriptive, not causal** — including the gas-price/fuel-spending relationship. Fuel spending reflects price *and* quantity purchased (fleet size, miles driven, snow-plowing intensity); gallons data isn't available to separate the two.
- **Small annual sample.** Validation uses well under twenty annual observations (fewer once lagged), split chronologically rather than randomly. Treat p-values and R² as supporting evidence, not proof.
- **FY2028–FY2029 are not forecast.** No adopted-budget input exists yet for those years, and this analysis deliberately avoids inventing scenario assumptions to fill that gap.
- **Both data corrections are applied uniformly across all fiscal years**, not as one-off patches to the years where they were first noticed.

---

*Source notebook: [`DOT_Final_Capstone_Analysis.ipynb`](https://github.com/lindali-huishan/NYC_Budget_Allocation/blob/vmax/DOT/DOT_Final_Capstone_Analysis.ipynb). Interactive charts are regenerated from raw data via [`DOT/build_interactive_charts.py`](https://github.com/lindali-huishan/NYC_Budget_Allocation/blob/vmax/DOT/build_interactive_charts.py).*
