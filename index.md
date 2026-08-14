---
title: Home
description: Planned vs. actual spending, forecasting, and budget insights across major NYC agencies.
body_class: home-page
---

<section class="hero" id="home">
  <div class="hero-inner">
    <div class="hero-copy">
      <div class="eyebrow">NYC Government Analytics · Capstone Project</div>
      <h1>NYC Budget<br>Allocation Findings</h1>
      <p class="subtitle">Planned vs. actual spending, forecasting, and budget insights across major NYC agencies.</p>
      <p class="support">A data-driven analysis of New York City agency budgets, spending behavior, and future funding needs.</p>
      <div class="button-row">
        <a class="btn btn-primary" href="#dot">View DOT Analysis&nbsp; →</a>
        <a class="btn btn-secondary" href="#methodology">Explore Methodology</a>
      </div>
    </div>
  </div>
</section>

<section class="section alt" aria-labelledby="agencies-title">
  <div class="section-inner">
    <div class="section-heading">
      <div><div class="eyebrow">Agency portfolio</div><h2 id="agencies-title">One platform. Three city missions.</h2></div>
      <p>DOT analysis is live. Parks &amp; Recreation and Education are intentionally staged for future releases as the project grows into a multi-agency decision tool.</p>
    </div>
    <div class="agency-grid">
      <article class="agency-card active">
        <div class="agency-icon" aria-hidden="true">➜</div><span class="status active">Active analysis</span>
        <h3>Department of Transportation</h3><p>Operating budgets, spending persistence, utilization, and a leakage-safe FY2027 forecast.</p>
        <a class="btn btn-primary" href="#dot">View DOT Findings</a>
      </article>
      <article class="agency-card disabled" id="parks">
        <div class="agency-icon" aria-hidden="true">♧</div><span class="status">Coming soon</span>
        <h3>Department of Parks &amp; Recreation</h3><p>A dedicated agency analysis will be added when validation and findings are complete.</p>
        <span class="btn" aria-disabled="true">Analysis Coming Soon</span>
      </article>
      <article class="agency-card disabled" id="education">
        <div class="agency-icon" aria-hidden="true">▤</div><span class="status">Coming soon</span>
        <h3>Department of Education</h3><p>A dedicated agency analysis will be added when validation and findings are complete.</p>
        <span class="btn" aria-disabled="true">Analysis Coming Soon</span>
      </article>
    </div>
  </div>
</section>

<section class="section" id="dot" aria-labelledby="dot-title">
  <div class="section-inner">
    <div class="section-heading">
      <div><div class="eyebrow">Active agency · FY2011–FY2027</div><h2 id="dot-title">DOT Executive Summary</h2></div>
      <p>Completed operating-spending history through FY2026. FY2027 is treated as a forecast year because recorded actual spending is partial.</p>
    </div>
    <div class="metric-grid">
      <article class="metric-card"><span class="metric-label">FY2027 forecast</span><span class="metric-value">$1.522B</span></article>
      <article class="metric-card"><span class="metric-label">Model MAPE</span><span class="metric-value">3.44%</span></article>
      <article class="metric-card"><span class="metric-label">Out-of-sample R²</span><span class="metric-value">0.902</span></article>
      <article class="metric-card"><span class="metric-label">Average utilization</span><span class="metric-value">86.4%</span></article>
      <article class="metric-card model"><span class="metric-label">Best model</span><span class="metric-value">Lag-1 Actual Spending + Current Adopted Budget</span></article>
    </div>
  </div>
</section>

<section class="section alt" aria-labelledby="forecast-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Planning outlook</div><h2 id="forecast-title">DOT Forecast</h2></div></div>
    <div class="forecast-card">
      <div class="forecast-main"><span class="metric-label">FY2027 predicted operating spending</span><span class="forecast-number">$1.522B</span></div>
      <div class="forecast-range"><span class="metric-label">Approximate 95% forecast range</span><strong>$1.396B – $1.647B</strong><p>The model combines prior-year actual spending with the current adopted budget, capturing both historical spending persistence and current policy expectations.</p></div>
    </div>
    <div class="chart-panel" style="margin-top:1rem">
      <iframe class="embed" src="{{ '/assets/charts/forecast_chart.html' | relative_url }}" loading="lazy" title="Interactive FY2027 DOT operating-spending forecast"></iframe>
      <p class="chart-caption">Historical operating spending and FY2027 forecast. Hover for exact values; the shaded range communicates planning uncertainty.</p>
    </div>
  </div>
</section>

<section class="section" aria-labelledby="performance-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Chronological backtesting</div><h2 id="performance-title">Model Performance</h2></div><p>Lower MAPE is better. These are forecasting errors—not classification accuracy—and every model is evaluated using time-ordered data.</p></div>
    <div class="model-list" aria-label="Model MAPE comparison">
      <div class="model-row winner"><span class="model-name">Lag-1 + Adopted Budget</span><span class="model-track"><span class="model-bar" style="--score:48.5%"></span></span><span class="model-score">3.44%</span></div>
      <div class="model-row"><span class="model-name">Lag-1 + Adopted + Gas Lag-1</span><span class="model-track"><span class="model-bar" style="--score:53.9%"></span></span><span class="model-score">3.83%</span></div>
      <div class="model-row"><span class="model-name">Lag-1 + Adopted + CPI Lag-1</span><span class="model-track"><span class="model-bar" style="--score:56.6%"></span></span><span class="model-score">4.02%</span></div>
      <div class="model-row"><span class="model-name">Lag-1 + Adopted + Inflation Lag-1</span><span class="model-track"><span class="model-bar" style="--score:58.3%"></span></span><span class="model-score">4.14%</span></div>
      <div class="model-row"><span class="model-name">Lag-1 + Modified — in-year</span><span class="model-track"><span class="model-bar" style="--score:68.5%"></span></span><span class="model-score">4.86%</span></div>
      <div class="model-row"><span class="model-name">ARIMA(1,1,0)</span><span class="model-track"><span class="model-bar" style="--score:69.2%"></span></span><span class="model-score">4.91%</span></div>
      <div class="model-row"><span class="model-name">Lag-1 Regression</span><span class="model-track"><span class="model-bar" style="--score:77.9%"></span></span><span class="model-score">5.53%</span></div>
      <div class="model-row"><span class="model-name">Naive Persistence</span><span class="model-track"><span class="model-bar" style="--score:84.2%"></span></span><span class="model-score">5.98%</span></div>
      <div class="model-row"><span class="model-name">Linear Trend</span><span class="model-track"><span class="model-bar" style="--score:99.3%"></span></span><span class="model-score">7.05%</span></div>
    </div>
    <div class="callout"><strong>42.5% lower MAPE than naive persistence.</strong> The selected model adds current adopted-budget expectations to a strong prior-year spending baseline.</div>
    <div class="chart-panel" style="margin-top:2rem"><img src="{{ '/assets/images/validation_performance.png' | relative_url }}" alt="MAPE, RMSE, MAE and out-of-sample R-squared comparison for nine DOT forecasting models"><p class="chart-caption">Supporting metrics confirm the selected model’s performance; R² is reported as context, not used alone.</p></div>
  </div>
</section>

<section class="section alt" aria-labelledby="insights-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Evidence, not assumptions</div><h2 id="insights-title">Key DOT Insights</h2></div></div>
    <div class="insight-grid">
      <article class="insight-card"><div class="insight-number">4.6%</div><h3>Nominal annual growth</h3><p>DOT operating spending grew approximately 4.6% annually over the analyzed period.</p></article>
      <article class="insight-card"><div class="insight-number">1.9%</div><h3>Real annual growth</h3><p>After CPI adjustment, annual purchasing-power growth was substantially lower.</p></article>
      <article class="insight-card"><div class="insight-number">0.980</div><h3>Lag-1 correlation</h3><p>Prior-year and current-year operating spending have a very strong relationship; correlation does not prove causation.</p></article>
      <article class="insight-card"><div class="insight-number">0.961</div><h3>Lag relationship R²</h3><p>The simple Lag-1 relationship explains substantial historical variation, supporting persistence as a baseline.</p></article>
      <article class="insight-card"><div class="insight-number">Closer</div><h3>Adopted vs. modified</h3><p>Adopted budgets were closer to actual spending on average in the analyzed operating data.</p></article>
      <article class="insight-card"><div class="insight-number">No gain</div><h3>External predictors</h3><p>Lagged CPI, inflation, and gas prices did not improve the final total-spending forecast.</p></article>
      <article class="insight-card"><div class="insight-number">Partial</div><h3>FY2027 actual</h3><p>FY2027 actual spending is incomplete and is excluded from utilization, growth, and validation conclusions.</p></article>
    </div>
  </div>
</section>

<section class="section" id="recommendations" aria-labelledby="actions-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">From analysis to action</div><h2 id="actions-title">Recommended Actions for NYC Budget Planning</h2></div></div>
    <div class="action-list">
      <div class="action"><div><strong>Start with completed actual spending.</strong><span>Use the latest full fiscal year as the operational baseline for the next allocation cycle.</span></div></div>
      <div class="action"><div><strong>Add current policy expectations.</strong><span>Combine prior-year spending with the current adopted budget rather than relying on a trend alone.</span></div></div>
      <div class="action"><div><strong>Monitor execution throughout the year.</strong><span>Track utilization, major revisions, and variance at consistent fiscal-year cutoffs.</span></div></div>
      <div class="action"><div><strong>Show nominal and real dollars together.</strong><span>Separate price growth from changes in the services DOT can actually purchase.</span></div></div>
      <div class="action"><div><strong>Make external data earn inclusion.</strong><span>Use CPI, inflation, or gas only when chronological forecast performance improves.</span></div></div>
      <div class="action"><div><strong>Protect the operating scope.</strong><span>Separate one-time capital and project spending from recurring operating expenses.</span></div></div>
    </div>
  </div>
</section>

<section class="section alt" id="methodology" aria-labelledby="method-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Transparent by design</div><h2 id="method-title">Methodology</h2></div><p>NYC budget and spending records are cleaned to a consistent operating scope, summarized by fiscal year, and evaluated in the order events occurred.</p></div>
    <div class="method-grid">
      <article class="method-card"><span class="step">01 · PREPARE</span><h3>Scope &amp; validate</h3><p>Correct agency contamination, separate operating from capital spending, and flag partial years.</p></article>
      <article class="method-card"><span class="step">02 · UNDERSTAND</span><h3>EDA &amp; variance</h3><p>Analyze budget changes, utilization, growth, and inflation-adjusted spending.</p></article>
      <article class="method-card"><span class="step">03 · MODEL</span><h3>Simple benchmarks</h3><p>Compare persistence, trend, lagged regression, budget inputs, external variables, and ARIMA.</p></article>
      <article class="method-card"><span class="step">04 · VALIDATE</span><h3>Respect chronology</h3><p>Use expanding-window backtests—not a random split—with MAPE primary and MAE, RMSE, and out-of-sample R² supporting.</p></article>
    </div>
    <div class="button-row"><a class="btn btn-primary" href="{{ '/methodology.html' | relative_url }}">View Full Methodology&nbsp; →</a></div>
  </div>
</section>

<section class="section" aria-labelledby="future-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Future platform</div><h2 id="future-title">Building Toward a Multi-Agency Budget Recommendation System</h2></div><p>The long-term platform will compare DOT, Parks &amp; Recreation, and DOE. The capabilities below are planned—not yet complete.</p></div>
    <div class="future-grid">
      <article class="future-card"><span>Planned</span><h3>Agency-level forecasts</h3><p>Validated forecasts designed around each agency’s operating drivers.</p></article>
      <article class="future-card"><span>Planned</span><h3>Utilization comparison</h3><p>Comparable planned-versus-actual and budget-execution metrics.</p></article>
      <article class="future-card"><span>Planned</span><h3>Funding priorities</h3><p>Transparent decision-support metrics—not automated policy decisions.</p></article>
      <article class="future-card"><span>Planned</span><h3>Variance monitoring</h3><p>Earlier signals when adopted plans and actual spending diverge.</p></article>
      <article class="future-card"><span>Planned</span><h3>What-if allocations</h3><p>Scenario analysis for constrained multi-agency budget choices.</p></article>
      <article class="future-card"><span>Planned</span><h3>Executive dashboard</h3><p>A unified view of forecast confidence, utilization, and allocation context.</p></article>
    </div>
  </div>
</section>
