# Convertible Securities Risk Analysis: Plethico Pharmaceuticals

**Type:** MSc dissertation (Investment Management, University of Surrey)  
**Focus:** Risk factors inherent in convertible bonds, illustrated through a distressed Indian pharmaceutical company

## Summary
This paper examines the risk profile of convertible securities through a detailed case study of Plethico Pharmaceuticals' 2010 FCCB issuance. It moves beyond textbook pricing models to analyze what actually happens when conversion rights, put options, and credit risk intersect in a stressed emerging-market context.

**Core risk dimensions examined:**
- **Conversion risk:** Equity downside renders the conversion option worthless
- **Credit risk:** Bondholder put options lose value if the issuer cannot pay
- **Liquidity risk:** Thin trading in both the bond and underlying stock
- **Structural risk:** Subordination, covenants, and cross-default provisions
- **Event risk:** Promoter pledges, regulatory investigations, and subsequent restructuring

## Key Takeaways
- Convertible bonds are not "equity with a floor": the floor can collapse
- Standard valuation models (Black-Scholes, binomial) assume liquid markets and creditworthy issuers; both assumptions failed here
- Risk management requires scenario analysis, not just Greek-based hedging
- Post-2010, Indian FCCB structures tightened significantly

## Relevance
This paper demonstrates:
- Ability to deconstruct complex financial instruments
- Understanding of the gap between pricing models and real-world risk
- Familiarity with emerging-market corporate distress patterns

# Tata Steel Capital Structure Decision

**Type:** MSc dissertation (Investment Management, University of Surrey)  
**Focus:** Capital structure optimisation in a capital-intensive, cyclical emerging-market firm

## Summary
This paper applies the Modigliani-Miller Theorem, Trade-Off Theory, Pecking Order Theory, and Agency Cost Theory to Tata Steel's historical financing decisions. It evaluates how the company balances interest tax shields against financial distress risk, particularly in the context of:

- Post-acquisition debt consolidation
- COVID-19 liquidity pressures
- Sustainability-linked cape plans (2030 target: 35-40 MTPA capacity, significant CO₂ reduction)

## Key Takeaways
- Tata Steel's post-2018 deleveraging reflects Trade-Off Theory in practice
- WACC minimization requires sector-specific distress cost calibration
- Capital structure policy is not static; it responds to strategic inflection points

# Portfolio Risk Metrics: VaR and ES Implementation
**Type:** Quantitative risk project (Python)  
**Focus:** Empirical comparison of historical simulation and parametric methods for Value at Risk and Expected Shortfall<br>
**Please Note:** This notebook documents my process of building, validating, and stress-testing market risk models from first principles. It prioritises transparency of reasoning over code minimalism

## Summary
This project implements and compares two approaches to measuring portfolio risk, historical simulation and parametric VaR/ES, using real market data. It moves beyond black-box calculations to examine how distributional assumptions and time-scaling conventions affect risk estimates in practice.

Core risk dimensions examined:

- Historical simulation: Non-parametric estimation using empirical return distributions
- Parametric method: Normal distribution assumption with mean-variance framework
- Time scaling behavior: Why parametric ES does not scale exactly by √T (with mathematical explanation)
- Portfolio diversification: Covariance matrix construction and volatility reduction effects
- Model limitations: Impact of skewness and excess kurtosis on tail risk estimates

## Key Takeaways
- Historical VaR captures fat tails but is limited by data availability; parametric methods smooth estimates but underestimate tail risk under non-normal conditions
- Parametric ES grows faster than √T at high confidence levels due to the φ(z)/(1−α) term interacting with time scaling, a nuance often glossed over in standard treatments
- Portfolio diversification produced a 33% volatility reduction compared to average individual asset volatility, demonstrating the covariance structure's importance
- Simple return vs log return choices affect statistical properties; both are computed and compared

## Relevance
This project demonstrates:
- Ability to implement risk metrics from first principles
- Understanding of the gap between theoretical models and empirical reality
- Critical thinking about model assumptions and their practical implications
- Python proficiency with financial data (yfinance, pandas, numpy, scipy, matplotlib)
- Model validation skills – implementing statistical backtests and interpreting results in a regulatory context

## Updates
- Backtesting validation – Kupiec POF test, Christoffersen conditional coverage test, and Basel Traffic Light framework
- Backtesting results: Historical VaR passes all three tests (Kupiec p=0.985, Christoffersen p=0.502, Green zone). Parametric VaR fails Kupiec (p=0.005) and Christoffersen (p=0.002), landing in Yellow zone—confirming that normal assumptions systematically underestimate tail risk and produce clustered exceptions.

# Portfolio Risk Metrics with Backtesting (Update)
**Please Note:** This notebook documents my process of building, validating, and stress-testing market risk models from first principles. It prioritises transparency of reasoning over code minimalism

A comprehensive Python implementation of portfolio risk metrics including VaR, Expected Shortfall, and regulatory backtesting frameworks.

## Features

- **Data Collection**: Downloads historical data from yfinance for 5 stocks (AAPL, MSFT, SAIL.NS, RELIANCE.NS, SPY)
- **Descriptive Statistics**: Annualized returns, volatility, skewness, excess kurtosis
- **Correlation & Covariance**: Asset correlation matrices and annualized covariance
- **Portfolio Construction**: Equal-weighted portfolio with volatility analysis
- **Risk Metrics**:
  - Historical VaR/ES (99%/97.5%)
  - Parametric (Delta-Normal) VaR/ES
  - Historical Monte Carlo VaR/ES
- **Backtesting Frameworks**:
  - Kupiec's Proportion of Failures (POF) test
  - Christoffersen's conditional coverage test
  - Basel Traffic Light test
- **Out-of-Sample Validation**: Train/test split (2016–2021 / 2022–2026)
- **Visualizations**: Rolling risk metrics, return distributions, model comparisons

## Results

| Model | In-sample failures | Out-of-sample failures | In-sample p-value | Out-of-sample p-value | Verdict |
|-------|-------------------|------------------------|-------------------|------------------------|---------|
| Historical VaR | 24 | 3 | 0.9853 | 0.0 | ✅ Pass (in-sample) ❌ Fail (out-of-sample) |
| Parametric VaR | 39 | 13 | 0.0045 | 0.0 | ❌ Fail |
| Monte Carlo VaR | N/A | 3 | N/A | 0.0 | ❌ Fail |

### Key Findings

1. **Historical VaR** passed all in-sample tests but failed out-of-sample (too conservative) — classic overfitting.
2. **Parametric VaR** failed everywhere — normality assumption breaks down with fat-tailed returns.
3. **Monte Carlo VaR** inherited historical overfitting — garbage in, garbage out.
4. **Non-stationarity**: Risk profiles changed significantly between training and test periods.

## Next Steps

- GARCH models for time-varying volatility
- Filtered Historical Simulation (FHS)
- Stress testing and scenario analysis
- Regime-switching models

## Dependencies

- pandas, numpy, scipy, matplotlib
- yfinance
- warnings (filtered)

## Usage

Run the notebook sequentially. All data is fetched live from yfinance.
