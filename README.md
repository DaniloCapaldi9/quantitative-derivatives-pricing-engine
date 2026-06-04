# Quantitative Derivatives Pricing & Risk Analytics Engine

A Python-based quantitative finance framework designed for pricing, risk analysis, and valuation of derivative products across equity, interest rate, credit, and foreign exchange markets.

The project combines analytical pricing models, Monte Carlo simulation techniques, and QuantLib yield curve construction to provide a practical environment for derivative valuation and risk management.

---

## Overview

This framework was developed to explore how financial institutions price and manage risk across multiple asset classes.

The engine supports:

* Equity Derivatives
* Interest Rate Derivatives
* Credit Derivatives
* Foreign Exchange Derivatives
* Yield Curve Construction
* Risk Sensitivity Analysis (Greeks)

The implementation combines industry-standard methodologies such as:

* Black-Scholes-Merton Model
* Monte Carlo Simulation
* Yield Curve Bootstrapping
* Hazard Rate Credit Models
* Discounted Cash Flow Valuation

---

## Main Features

### Equity Derivatives

#### European Options

* European Call Options
* European Put Options
* Black-Scholes analytical valuation
* Monte Carlo pricing validation
* Full Greeks calculation:

  * Delta
  * Gamma
  * Vega
  * Theta
  * Rho

#### Barrier Options

Supports:

* Up-and-In
* Up-and-Out
* Down-and-In
* Down-and-Out

Priced using Monte Carlo simulation.

#### Asian Options

Arithmetic-average Asian options priced through path-dependent Monte Carlo simulation.

#### Digital Options

Cash-or-Nothing binary option pricing framework.

---

### Market Simulation Engine

The pricing engine is built on a Geometric Brownian Motion (GBM) process:

* Daily path generation
* Configurable number of simulations
* Configurable time discretization
* Stochastic scenario generation

---

### Risk Analytics Dashboard

For each option type the framework generates:

* Greeks profiles
* Monte Carlo path visualization
* Dynamic pricing curves
* Payoff diagrams

Risk sensitivities are calculated analytically for vanilla products and numerically for exotic derivatives.

---

### Yield Curve Construction

The framework includes a multi-curve bootstrapping module using QuantLib.

Supported currencies:

* USD
* EUR

Market data source:

* FRED (Federal Reserve Economic Data)

If live market data is unavailable, the system automatically switches to a structured fallback curve to maintain valuation continuity.

---

### Interest Rate Swap (IRS)

Plain Vanilla Interest Rate Swap valuation:

* Payer Swap
* Receiver Swap
* Fixed Leg NPV
* Floating Leg NPV
* Fair Swap Rate (Par Rate)

---

### Credit Default Swap (CDS)

Single-name CDS valuation using a continuous hazard-rate model.

Outputs:

* Fair CDS Spread
* Protection Leg Value
* Credit Risk Premium Estimation

---

### Cross Currency Swap (CCS)

Cross-currency valuation between EUR and USD.

Features:

* Dual-currency cash flow discounting
* FX conversion
* Currency-specific yield curves
* Cross-currency basis valuation

---

## Technologies

* Python
* NumPy
* Pandas
* SciPy
* Matplotlib
* QuantLib
* Pandas DataReader
* FRED Market Data

---

## Example Results

### European Call Option

| Metric              | Value       |
| ------------------- | ----------- |
| Black-Scholes Price | 10.4506 USD |
| Monte Carlo Price   | 10.5537 USD |
| Delta               | 0.6368      |
| Gamma               | 0.0188      |
| Vega                | 37.5240     |
| Theta               | -6.4140     |
| Rho                 | 53.2325     |

### Interest Rate Swap

| Metric         | Value          |
| -------------- | -------------- |
| Notional       | 10,000,000 USD |
| Fair Swap Rate | 4.6908%        |
| Swap NPV       | +83,230.68 USD |

### Credit Default Swap

| Metric          | Value         |
| --------------- | ------------- |
| Notional        | 5,000,000 USD |
| Hazard Rate     | 1.50%         |
| Fair CDS Spread | 90 bps        |

### Cross Currency Swap

| Metric        | Value           |
| ------------- | --------------- |
| EUR Notional  | 10,000,000 EUR  |
| USD Notional  | 10,850,000 USD  |
| Total CCS NPV | +167,215.75 EUR |

---

## Project Structure

```text
project/
│
├── MarketSimulator
│
├── Equity Derivatives
│   ├── EuropeanCallOption
│   ├── EuropeanPutOption
│   ├── BarrierOption
│   ├── AsianOption
│   └── DigitalOption
│
├── Yield Curves
│   └── QuantLibMultiCurve
│
├── Interest Rate Products
│   └── InterestRateSwap
│
├── Credit Products
│   └── CreditDefaultSwap
│
└── FX Products
    └── CrossCurrencySwap
```

---

## Future Improvements

Potential extensions include:

* SABR Volatility Models
* Heston Stochastic Volatility
* Hull-White Interest Rate Models
* Bermudan Swaptions
* CVA/DVA/XVA Framework
* Multi-factor Interest Rate Curves
* Calibration to Market Volatility Surfaces

---

## Author

Developed as a quantitative finance and derivatives pricing project focused on practical implementation of financial engineering techniques using Python and QuantLib.

## Disclaimer

This repository is provided for educational and demonstration purposes only.

While industry-standard methodologies such as Black-Scholes pricing, Monte Carlo simulation, yield curve bootstrapping, and QuantLib-based valuation are implemented, the framework is not intended for production use or financial decision-making.

No financial or investment advice is provided.
