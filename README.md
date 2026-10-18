# Dissertation-BitcoinVolatility
This Repository contains a copy of my 6000 word final year project of my BSc. The project is essentially systematic signal research. Drawing on high frequency bitcoin price data from Binance, and macroeconomic factor variables from Yfinance and FRED, I statistically analyse the time series data and present conclusions. The project analysis was fully conducted in python.
Section 3 and 4 are the quantitative methodology and intepretations, respectively.

# Research Question

How have Bitcoin's volatility dynamics evolved with increased integration within traditional markets? Does it behave more like a traditional financial asset and less like a speculative, narrative-driven one? 

# Data
- Bitcoin prices: 656,000+ 5-minute BTCUSDT Kline observations from the Binance REST API (Jan 2020 – Mar 2026), retrieved in sequential batches and filtered for coverage quality (≥80% of daily intervals)

- Macroeconomic factors: Six daily series, namely, VIX, DXY, 10Y–3M term spread, 10-year TIPS real yield, 5-year breakeven inflation, and US Economic Policy Uncertainty were sourced from Yahoo Finance and FRED

- Regime split: Pre-ETF (Jan 2020 – Jan 2024) vs. Post-ETF (Jan 2024 – Mar 2026), using the ETF approval date as a **thematically motivated boundary**

Daily realised variance was constructed from 5-minute log returns following the standard estimator used in the literature (Liu et al., 2015).

# Methodology
- Volatility modelling: Compared 8 HAR-family specifications (Corsi, 2009) including jump-augmented variants. Selected the HARQ-F-J model based on AIC/BIC and residual diagnostics

- Jump detection: Bipower variance and tripower quarticity (Barndorff-Nielsen & Shephard) with significance at α = 0.999

- Structural breaks: ICSS algorithm with Sansó κ₂ robustness check

- Macroeconomic factor regression: Asymmetric VIX decomposition tested via Wald statistics; all inference under Newey-West (HAC) standard errors

- Local projections (Jordà, 2005): Multi-horizon impulse responses for interest rate channels (TIPS yield, term spread) across 6 horizons

- Quantile Regression Averaging (Koenker & Bassett, 1978): Tail-conditional sensitivity of realised variance to market uncertainty shocks

# Key Findings
See results section of [Dissertation.pdf](Dissertation.pdf)
