# Convertible Securities Risk Analysis – Plethico Pharmaceuticals

**Type:** MSc dissertation (Investment Management, University of Surrey)  
**Focus:** Risk factors inherent in convertible bonds, illustrated through a distressed Indian pharmaceutical company

## Summary
This paper examines the risk profile of convertible securities through a detailed case study of Plethico Pharmaceuticals' 2010 FCCB issuance. It moves beyond textbook pricing models to analyze what actually happens when conversion rights, put options, and credit risk intersect in a stressed emerging-market context.

**Core risk dimensions examined:**
- **Conversion risk** – Equity downside renders the conversion option worthless
- **Credit risk** – Bondholder put options lose value if the issuer cannot pay
- **Liquidity risk** – Thin trading in both the bond and underlying stock
- **Structural risk** – Subordination, covenants, and cross-default provisions
- **Event risk** – Promoter pledges, regulatory investigations, and subsequent restructuring

## Key Takeaways
- Convertible bonds are not "equity with a floor" — the floor can collapse
- Standard valuation models (Black-Scholes, binomial) assume liquid markets and creditworthy issuers; both assumptions failed here
- Risk management requires scenario analysis, not just Greek-based hedging
- Post-2010, Indian FCCB structures tightened significantly — this case is part of why

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
- Sustainability-linked cape plans (2030 target: 35–40 MTPA capacity, significant CO₂ reduction)

## Key Takeaways
- Tata Steel's post-2018 deleveraging reflects Trade-Off Theory in practice
- WACC minimization requires sector-specific distress cost calibration
- Capital structure policy is not static — it responds to strategic inflection points

# Portfolio Risk Metrics: VaR and ES Implementation
**Type:** Quantitative risk project (Python)
**Focus:** Empirical comparison of historical simulation and parametric methods for Value at Risk and Expected Shortfall

## Summary
This project implements and compares two approaches to measuring portfolio risk—historical simulation and parametric VaR/ES—using real market data. It moves beyond black-box calculations to examine how distributional assumptions and time-scaling conventions affect risk estimates in practice.

Core risk dimensions examined:

- Historical simulation – Non-parametric estimation using empirical return distributions
- Parametric method – Normal distribution assumption with mean-variance framework
- Time scaling behavior – Why parametric ES does not scale exactly by √T (with mathematical explanation)
- Portfolio diversification – Covariance matrix construction and volatility reduction effects
- Model limitations – Impact of skewness and excess kurtosis on tail risk estimates

## Key Takeaways
- Historical VaR captures fat tails but is limited by data availability; parametric methods smooth estimates but underestimate tail risk under non-normal conditions
- Parametric ES grows faster than √T at high confidence levels due to the φ(z)/(1−α) term interacting with time scaling—a nuance often glossed over in standard treatments
- Portfolio diversification produced a 33% volatility reduction compared to average individual asset volatility, demonstrating the covariance structure's importance
- Simple return vs log return choices affect statistical properties; both are computed and compared

## Relevance
This project demonstrates:
- Ability to implement risk metrics from first principles
- Understanding of the gap between theoretical models and empirical reality
- Critical thinking about model assumptions and their practical implications
- Python proficiency with financial data (yfinance, pandas, numpy, scipy, matplotlib)
