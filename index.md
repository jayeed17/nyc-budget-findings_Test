---
title: NYC DOT Budget Analysis
---

# NYC DOT Budget Analysis, FY2011–2027

Interactive look at how NYC DOT's operating budget was planned, revised, and spent — and whether next year's spending can be forecast from what's already known.

## Key Findings

- DOT spends **83–93%** of its modified budget every completed year — high, consistent execution, but never total.
- Between FY2017 and FY2026, DOT's budget grew about 62% on paper — but after adjusting for inflation, real growth was closer to 20%. Roughly half to sixty percent of the headline growth was inflation, not expanded capacity — the exact share depends on whether national or New York-metro CPI is used. In three years the budget actually shrank in real terms while rising in nominal dollars.
- Gasoline prices show no meaningful relationship with DOT's total budget. But at the line-item level, they track motor-vehicle-fuel spending closely — a correlation of about +0.90 on year-over-year changes (it survives detrending, which rules out the two simply drifting upward together). Fuel is under 2% of the budget, which is why a real effect at the category level disappears in the agency total. External cost drivers act on specific line items and are masked by aggregation.
- Actual spending is **persistence-driven**: prior-year actual (r = 0.98) beats a trend line as a forecast baseline.

<iframe src="assets/charts/budget_chart.html" width="100%" height="500" style="border:none;" loading="lazy" title="Adopted vs modified vs actual DOT budget, interactive"></iframe>

*Adopted, modified, and actual DOT operating spending, FY2011–2027 — hover for exact values, click a button to isolate one series.*

<iframe src="assets/charts/fuel_gas_chart.html" width="100%" height="500" style="border:none;" loading="lazy" title="Gas price vs DOT fuel spending, interactive"></iframe>

*Gas price vs. `MOTOR VEHICLE FUEL` spending — the relationship gets stronger after detrending, the opposite of a spurious pattern.*

<iframe src="assets/charts/forecast_chart.html" width="100%" height="500" style="border:none;" loading="lazy" title="FY2027 DOT spending forecast, interactive"></iframe>

*The best model predicts actual spending within 3.4% on held-out years (R² = 0.90), forecasting FY2027 at $1.52B. It earns that accuracy by combining the prior year's spending with the known adopted budget — and it beats a naive 'same as last year' baseline, which on this series is genuinely hard to beat. FY2028–29 are deliberately not forecast: doing so would require future adopted budgets that don't yet exist, and inventing them would undermine the result.*

## Recommendations

- **Anchor budget estimates in the latest actual spending**, combined with the current adopted budget.
- **Report nominal and real (CPI-adjusted) trends together** — about half of headline growth is inflation.
- **Use CPI, inflation, and gas price only where they earn it** — none improved the total-budget forecast here; model gas at the fuel-category level instead.

<details>
<summary><strong>Data corrections applied</strong> (click to expand)</summary>

- **FY2022 contamination:** that year's budget source file had ~150 other NYC agencies' rows mixed in, inflating Adopted from a plausible ~$1.3B to an implausible ~$100.6B. Fixed by filtering every year to `Agency == "Department of Transportation"`.
- **Capital-vs-expense scope mismatch:** the raw spending file mixes operating and capital transactions. Fixed by keeping only spending rows whose Budget Code matches DOT's own operating-budget codes.
- **FY2027 is a partial year** (actual = 9.9% of modified budget) and is excluded from every completed-year KPI, correlation, and validation result.

</details>

📄 **[Full methodology, model comparison & diagnostics →](methodology.html)**

---

*Part of the [NYC Budget Allocation](https://github.com/lindali-huishan/NYC_Budget_Allocation) project. Source notebooks and data live in the repo's `DOT/` directory.*
