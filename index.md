---
title: Home
description: Data-driven budget planning, forecasting, and decision support for New York City agencies.
body_class: home-page
---

<section class="hero" id="home">
  <div class="hero-inner">
    <div class="hero-copy">
      <div class="eyebrow">NYC Government Analytics · Decision Support</div>
      <h1>NYC Budget<br>Allocation</h1>
      <p class="subtitle">Data-Driven Budget Planning for New York City</p>
      <p class="support">Analyzing historical budgets, actual expenditures, economic drivers, and forecasting models to support more informed agency funding decisions.</p>
      <div class="tag-row" aria-label="Project scope">
        <span>FY2011–FY2029</span><span>Forecasting</span><span>Scenario Analysis</span><span>Decision Support</span>
      </div>
      <div class="button-row">
        <a class="btn btn-primary" href="#dot">Explore DOT Analysis&nbsp; →</a>
        <a class="btn btn-secondary" href="#methodology">View Methodology</a>
      </div>
    </div>
  </div>
</section>

<section class="section workflow-strip" aria-label="Analysis workflow">
  <div class="section-inner">
    <div class="workflow" role="list">
      <span role="listitem">Historical Analysis</span><i aria-hidden="true">→</i>
      <span role="listitem">EDA</span><i aria-hidden="true">→</i>
      <span role="listitem">Model Testing</span><i aria-hidden="true">→</i>
      <span role="listitem">Forecasting</span><i aria-hidden="true">→</i>
      <span role="listitem">Scenarios</span><i aria-hidden="true">→</i>
      <span role="listitem">Decision Support</span>
    </div>
  </div>
</section>

<section class="section alt" aria-labelledby="agencies-title">
  <div class="section-inner">
    <div class="section-heading">
      <div><div class="eyebrow">Agency portfolio</div><h2 id="agencies-title">A standardized framework for city agencies.</h2></div>
      <p>DOT is the first completed agency model. Education and Parks &amp; Recreation are visible as intentional next phases—without unpublished results.</p>
    </div>
    <div class="agency-grid">
      <article class="agency-card active">
        <div class="agency-icon" aria-hidden="true">➜</div><span class="status active">Active analysis</span>
        <h3>Department of Transportation</h3><p>Historical execution, economic drivers, chronological forecasting, and allocation scenarios.</p>
        <a class="btn btn-primary" href="#dot">View DOT Analysis</a>
      </article>
      <article class="agency-card disabled" id="education">
        <div class="agency-icon" aria-hidden="true">▤</div><span class="status">Analysis in progress</span>
        <h3>Department of Education</h3><p>The same validation framework will be applied when the agency analysis is complete.</p>
        <span class="btn" aria-disabled="true">Coming Soon</span>
      </article>
      <article class="agency-card disabled" id="parks">
        <div class="agency-icon" aria-hidden="true">♧</div><span class="status">Analysis in progress</span>
        <h3>Parks &amp; Recreation</h3><p>A dedicated agency model and evidence-based findings will follow in a future release.</p>
        <span class="btn" aria-disabled="true">Coming Soon</span>
      </article>
    </div>
  </div>
</section>

<section class="section" id="dot" aria-labelledby="dot-title">
  <div class="section-inner">
    <div class="section-heading">
      <div><div class="eyebrow">Featured agency · Operating spending</div><h2 id="dot-title">DOT — Executive Overview</h2></div>
      <p>FY2011–FY2026 are completed historical years. FY2027 is a near-term forecast; FY2028–FY2029 are longer-range projections with greater uncertainty.</p>
    </div>
    <div class="metric-grid executive-metrics">
      <article class="metric-card"><span class="metric-label">Historical analysis</span><span class="metric-value small">FY2011–FY2026</span></article>
      <article class="metric-card model"><span class="metric-label">Winning forecast model</span><span class="metric-value">Lag-1 Actual + Adopted Budget</span></article>
      <article class="metric-card"><span class="metric-label">Backtest MAPE</span><span class="metric-value">3.44%</span></article>
      <article class="metric-card"><span class="metric-label">Improvement vs naive</span><span class="metric-value">42.5%</span></article>
      <article class="metric-card"><span class="metric-label">FY2027 forecast</span><span class="metric-value">$1.522B</span></article>
      <article class="metric-card"><span class="metric-label">FY2028 projection</span><span class="metric-value">$1.593B</span></article>
      <article class="metric-card"><span class="metric-label">FY2029 projection</span><span class="metric-value">$1.668B</span></article>
    </div>
  </div>
</section>

<section class="section alt" id="eda" aria-labelledby="eda-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">01 · Historical analysis</div><h2 id="eda-title">Exploratory Data Analysis</h2></div><p>Separate budget authorization from actual execution, then test whether operational drivers explain the annual pattern.</p></div>
    <article class="feature-story wide">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_budget_vs_actual.png' | relative_url }}" data-lightbox aria-label="Open historical DOT budget versus actual spending chart">
        <img src="{{ '/assets/images/dot/dot_budget_vs_actual.png' | relative_url }}" alt="DOT adopted budget, modified budget, and actual operating spending by fiscal year" loading="lazy">
      </a>
      <div class="story-copy"><span class="story-label">Primary EDA view</span><h3>Plans, revisions, and actual spending</h3><p>Historical analysis shows how adopted and modified budgets compared with actual DOT operating expenditures over time.</p><p class="note">Budget revisions provide operating context; they are not automatically evidence of efficiency or waste.</p></div>
    </article>
    <div class="story-grid">
      <article class="story-card">
        <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_gas_vs_fuel_spending.png' | relative_url }}" data-lightbox aria-label="Open gas price versus DOT fuel spending chart"><img src="{{ '/assets/images/dot/dot_gas_vs_fuel_spending.png' | relative_url }}" alt="Gas prices versus DOT fuel-specific spending with fitted relationship" loading="lazy"></a>
        <div class="story-body"><span class="story-stat">r = 0.866 · R² = 0.750</span><h3>Fuel-specific pressure</h3><p>Fuel prices show a strong relationship with DOT’s fuel-specific expenditures, though they are weak predictors of total operating spending.</p></div>
      </article>
      <article class="story-card">
        <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_nyc_inflation_vs_spending_growth.png' | relative_url }}" data-lightbox aria-label="Open NYC inflation versus DOT spending growth chart"><img src="{{ '/assets/images/dot/dot_nyc_inflation_vs_spending_growth.png' | relative_url }}" alt="NYC annual inflation versus DOT actual-spending annual growth" loading="lazy"></a>
        <div class="story-body"><h3>Levels are not changes</h3><p>NYC CPI levels strongly track spending levels, but annual inflation has a much weaker relationship with annual spending growth. Raw correlation alone is not enough for forecasting.</p></div>
      </article>
    </div>
  </div>
</section>

<section class="section" id="drivers" aria-labelledby="drivers-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">02 · External-variable testing</div><h2 id="drivers-title">Testing Economic Drivers</h2></div><p>National CPI, NYC-area CPI, inflation, and gas prices were tested one at a time using chronological validation.</p></div>
    <article class="feature-story reverse">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_cpi_model_predictions.png' | relative_url }}" data-lightbox aria-label="Open base versus NYC CPI forecast comparison"><img src="{{ '/assets/images/dot/dot_cpi_model_predictions.png' | relative_url }}" alt="Actual DOT spending compared with base-model and NYC-CPI-model backtest predictions" loading="lazy"></a>
      <div class="story-copy"><span class="story-label">Out-of-sample evidence</span><h3>More variables did not mean better forecasts</h3>
        <div class="compact-metrics"><span><b>3.44%</b> Base model</span><span><b>4.02%</b> + National CPI</span><span><b>4.04%</b> + NYC CPI</span></div>
        <p>Adding inflation variables marginally improved some in-sample statistical relationships but worsened chronological forecast accuracy. The simpler model was retained.</p>
      </div>
    </article>
  </div>
</section>

<section class="section alt" id="model-selection" aria-labelledby="selection-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">03 · Model testing</div><h2 id="selection-title">Forecast Model Selection</h2></div><p>The selected model balances accuracy, stability, timing, and business explainability.</p></div>
    <article class="feature-story">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_model_comparison.png' | relative_url }}" data-lightbox aria-label="Open DOT forecasting model comparison"><img src="{{ '/assets/images/dot/dot_model_comparison.png' | relative_url }}" alt="MAPE comparison across nine DOT forecasting methods" loading="lazy"></a>
      <div class="story-copy"><span class="story-stat">3.44% MAPE · 0.902 out-of-sample R²</span><h3>Lag-1 Actual + Adopted Budget</h3><ul class="check-list"><li>Best chronological forecast accuracy</li><li>Uses information available at the fiscal-year start</li><li>Appropriate for a small annual dataset</li><li>Explainable without unnecessary complexity</li><li>42.5% lower MAPE than naive persistence</li></ul></div>
    </article>
  </div>
</section>

<section class="section" id="validation" aria-labelledby="validation-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">04 · Transparent validation</div><h2 id="validation-title">Historical Backtesting</h2></div><p>Expanding-window testing evaluates repeated one-year-ahead decisions instead of relying on a random split.</p></div>
    <article class="feature-story reverse">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_backtest_actual_vs_predicted.png' | relative_url }}" data-lightbox aria-label="Open DOT actual versus backtest prediction chart"><img src="{{ '/assets/images/dot/dot_backtest_actual_vs_predicted.png' | relative_url }}" alt="Actual DOT spending versus expanding-window model predictions from FY2019 through FY2026" loading="lazy"></a>
      <div class="story-copy"><h3>Tested across FY2019–FY2026</h3><p>The model was evaluated through expanding-window chronological backtesting rather than a single random train/test split.</p><div class="range-cards"><span><small>Best year</small><b>FY2023</b><em>0.17% error</em></span><span><small>Weakest year</small><b>FY2024</b><em>10.81% error</em></span></div><p class="note">The weaker year remains visible to communicate forecast risk honestly.</p></div>
    </article>
  </div>
</section>

<section class="section alt" id="forecast" aria-labelledby="forecast-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">05 · Forecasting</div><h2 id="forecast-title">DOT Spending Outlook</h2></div><p>Near-term planning uses the adopted-budget model. Longer-range values use a separate time-series projection because future adopted budgets are unavailable.</p></div>
    <article class="feature-story wide">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_actual_forecast.png' | relative_url }}" data-lightbox aria-label="Open DOT actual-spending outlook"><img src="{{ '/assets/images/dot/dot_actual_forecast.png' | relative_url }}" alt="Historical DOT actual operating spending and FY2027 through FY2029 forecasts with uncertainty" loading="lazy"></a>
      <div class="story-copy"><h3>Actual operating-spending outlook</h3><div class="forecast-list"><span><small>FY2027 · Near-term forecast</small><b>$1.522B</b></span><span><small>FY2028 · Long-range projection</small><b>$1.593B</b></span><span><small>FY2029 · Long-range projection</small><b>$1.668B</b></span></div><p class="note">FY2028–FY2029 carry greater uncertainty and are model-based projections—not guaranteed outcomes.</p></div>
    </article>
    <article class="feature-story reverse compact-top">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_modified_budget_forecast.png' | relative_url }}" data-lightbox aria-label="Open modified-budget projection"><img src="{{ '/assets/images/dot/dot_modified_budget_forecast.png' | relative_url }}" alt="Historical DOT modified budget and FY2028 through FY2029 projections" loading="lazy"></a>
      <div class="story-copy"><h3>Authorized-budget outlook</h3><p>The modified-budget projection estimates how authorized funding may evolve after fiscal-year adjustments. It is a separate planning question from actual spending.</p></div>
    </article>
  </div>
</section>

<section class="section" id="gap" aria-labelledby="gap-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">06 · Planning outlook</div><h2 id="gap-title">Budget Cushion &amp; Utilization</h2></div><p>The difference is a planning buffer—not waste—and helps frame how tightly projected spending fits within projected authorization.</p></div>
    <article class="feature-story">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_forecast_gap.png' | relative_url }}" data-lightbox aria-label="Open projected DOT budget gap and utilization"><img src="{{ '/assets/images/dot/dot_forecast_gap.png' | relative_url }}" alt="FY2028 and FY2029 projected modified budget, actual spending, and utilization" loading="lazy"></a>
      <div class="story-copy"><div class="outlook-table" role="table" aria-label="Forecast budget outlook"><div role="row"><b>Fiscal year</b><b>FY2028</b><b>FY2029</b></div><div role="row"><span>Projected spending</span><span>$1.593B</span><span>$1.668B</span></div><div role="row"><span>Modified budget</span><span>$1.706B</span><span>$1.772B</span></div><div role="row"><span>Planning buffer</span><span>≈ $113M</span><span>≈ $103M</span></div><div role="row"><span>Utilization</span><span>93.4%</span><span>94.2%</span></div></div></div>
    </article>
  </div>
</section>

<section class="section scenario-section" id="scenarios" aria-labelledby="scenario-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">07 · Decision support</div><h2 id="scenario-title">What-If Budget Scenarios</h2></div><p>Allocation choices change the balance between funding pressure and planning flexibility. The analysis does not prescribe one objectively optimal budget.</p></div>
    <a class="visual-card hero-chart lightbox-link" href="{{ '/assets/images/dot/dot_budget_scenario.png' | relative_url }}" data-lightbox aria-label="Open FY2028 DOT allocation scenarios"><img src="{{ '/assets/images/dot/dot_budget_scenario.png' | relative_url }}" alt="FY2028 proposed DOT allocations with projected utilization and funding cushion" loading="lazy"></a>
    <div class="scenario-grid">
      <article><b>$1.60B</b><span>99.6% utilized</span><small>$6.7M cushion</small></article>
      <article><b>$1.65B</b><span>96.6% utilized</span><small>$56.7M cushion</small></article>
      <article><b>$1.70B</b><span>93.7% utilized</span><small>$106.7M cushion</small></article>
      <article><b>$1.75B</b><span>91.0% utilized</span><small>$156.7M cushion</small></article>
    </div>
    <div class="callout"><strong>Decision tradeoff:</strong> Lower allocations increase funding pressure, while larger allocations create additional planning flexibility.</div>
  </div>
</section>

<section class="section alt" id="inflation" aria-labelledby="inflation-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Purchasing-power risk</div><h2 id="inflation-title">Inflation &amp; Sensitivity</h2></div><p>Nominal funding growth does not necessarily preserve purchasing power.</p></div>
    <article class="feature-story reverse">
      <a class="visual-card lightbox-link" href="{{ '/assets/images/dot/dot_inflation_scenarios.png' | relative_url }}" data-lightbox aria-label="Open inflation purchasing-power scenarios"><img src="{{ '/assets/images/dot/dot_inflation_scenarios.png' | relative_url }}" alt="FY2029 real purchasing power under two, four, and six percent inflation assumptions" loading="lazy"></a>
      <div class="story-copy"><h3>2%, 4%, and 6% inflation scenarios</h3><p>At 6% inflation, projected FY2029 purchasing power falls by approximately:</p><div class="range-cards"><span><small>Actual spending</small><b>$94.4M</b><em>purchasing-power reduction</em></span><span><small>Modified budget</small><b>$100.3M</b><em>purchasing-power reduction</em></span></div></div>
    </article>
  </div>
</section>

<section class="section" id="recommendations" aria-labelledby="actions-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">From evidence to action</div><h2 id="actions-title">Decision Recommendations</h2></div></div>
    <div class="recommendation-grid">
      <article><span>01</span><h3>Anchor the baseline</h3><p>Start forecasts with the most recent completed actual spending.</p></article>
      <article><span>02</span><h3>Add current intent</h3><p>Combine prior-year actual spending with the current adopted budget.</p></article>
      <article><span>03</span><h3>Monitor execution</h3><p>Track utilization and major revisions throughout the fiscal year.</p></article>
      <article><span>04</span><h3>Validate every driver</h3><p>Use economic variables in forecasts only when chronological performance improves.</p></article>
    </div>
    <div class="callout"><strong>Scope matters:</strong> separate recurring operating expenditures from capital and one-time projects before using forecasts for allocation decisions.</div>
  </div>
</section>

<section class="section app-section" id="app" aria-labelledby="app-title">
  <div class="section-inner app-shell">
    <div class="app-copy"><span class="status active">Coming soon</span><div class="eyebrow">Interactive Budget Simulator</div><h2 id="app-title">From Analysis to Interactive Budget Planning</h2><p>The next phase will turn the forecasting and scenario-analysis framework into an interactive decision-support application.</p><div class="button-row"><span class="btn app-disabled" aria-disabled="true">Launch App — Coming Soon</span></div></div>
    <div class="app-preview" aria-label="Planned app capabilities">
      <div class="preview-bar"><span></span><span></span><span></span><b>NYC Budget Decision Support</b></div>
      <div class="preview-body"><div class="preview-control"><small>Agency</small><strong>Department of Transportation</strong></div><div class="preview-control"><small>Proposed allocation</small><strong>$1.70B</strong></div><div class="preview-output"><span><small>Projected utilization</small><b>93.7%</b></span><span><small>Planning cushion</small><b>$106.7M</b></span></div><div class="preview-watermark">IN DEVELOPMENT</div></div>
    </div>
    <div class="capability-grid"><span>Select NYC agency</span><span>View historical execution</span><span>Explore forecasts</span><span>Change proposed allocations</span><span>Test inflation assumptions</span><span>Compare decision metrics</span></div>
  </div>
</section>

<section class="section alt" id="roadmap" aria-labelledby="roadmap-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Multi-agency future</div><h2 id="roadmap-title">One Framework, More Agencies</h2></div><p>DOT is the first completed agency model. DOE and Parks &amp; Recreation will follow the same standardized analysis framework.</p></div>
    <div class="roadmap">
      <article class="complete"><span>Completed</span><h3>DOT</h3></article>
      <article><span>In progress</span><h3>DOE</h3></article>
      <article><span>In progress</span><h3>Parks &amp; Recreation</h3></article>
      <article><span>Next phase</span><h3>Cross-Agency Decision Support</h3></article>
      <article><span>Coming soon</span><h3>Interactive App</h3></article>
    </div>
  </div>
</section>

<section class="section" id="methodology" aria-labelledby="method-title">
  <div class="section-inner">
    <div class="section-heading"><div><div class="eyebrow">Transparent by design</div><h2 id="method-title">Methodology</h2></div><p>Operating-spending scope, partial-year treatment, chronological backtesting, and external-variable tests are documented for review.</p></div>
    <div class="method-grid">
      <article class="method-card"><span class="step">01 · PREPARE</span><h3>Scope &amp; validate</h3><p>Filter DOT operating records, align fiscal years, and flag incomplete actuals.</p></article>
      <article class="method-card"><span class="step">02 · UNDERSTAND</span><h3>EDA &amp; variance</h3><p>Compare budgets, actuals, utilization, growth, and real purchasing power.</p></article>
      <article class="method-card"><span class="step">03 · TEST</span><h3>Simple models</h3><p>Evaluate persistence, trend, lagged regression, ARIMA, and external drivers.</p></article>
      <article class="method-card"><span class="step">04 · VALIDATE</span><h3>Respect chronology</h3><p>Use expanding-window backtests with MAPE primary and MAE, RMSE, and R² supporting.</p></article>
    </div>
    <div class="button-row"><a class="btn btn-primary" href="{{ '/methodology.html' | relative_url }}">View Full Methodology&nbsp; →</a></div>
  </div>
</section>
