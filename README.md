# Bergomi VIX Volatility Model

Pricing and calibration of VIX options under Bergomi forward variance models.

This project was developed as a Master's thesis in Quantitative Finance and focuses on the pricing of VIX derivatives using forward variance curve models introduced by Lorenzo Bergomi.

---

## Project Overview

The objective is to model, price and calibrate VIX options using:

- Bergomi One-Factor Model
- Exponential Mixture Bergomi Model
- Monte Carlo Simulation
- Implied Volatility Extraction
- Market Smile Calibration

The project investigates the ability of forward variance models to reproduce the observed positive skew of VIX implied volatility smiles.

---

## Mathematical Framework

The forward variance process is modeled as:

\[
d\xi_t^T = \xi_t^T \phi(T-t)dW_t
\]

with

\[
\phi(\tau)=\omega e^{-k\tau}
\]

for the classical Bergomi model.

The extension considered in this work introduces a mixture of exponentials:

\[
\xi_t^T =
\xi_0^T
\Big[
(1-\gamma)G_1
+
\gamma G_2
\Big]
\]

allowing the model to generate significantly steeper VIX volatility smiles.

---

## Main Features

### Market Data Processing

- VIX option market data import
- Bid/Ask filtering
- Mid-price computation
- Forward VIX extraction

### Monte Carlo Pricing

- Simulation of forward variance dynamics
- VIX futures pricing
- European call and put pricing

### Implied Volatility

- Black model implementation
- Implied volatility inversion
- Smile generation

### Calibration

- One maturity calibration
- Multi-maturity calibration
- Least-squares optimization

### Visualization

- Market vs model smiles
- Calibration diagnostics
- Parameter sensitivity analysis

---

## Repository Structure

```text
├── data/
│   ├── VIX market quotes
│   └── implied volatility datasets
│
├── models/
│   ├── bergomi_1f.py
│   ├── bergomi_mixture.py
│   └── black_model.py
│
├── calibration/
│   ├── objective_function.py
│   ├── optimizer.py
│   └── calibration_results.py
│
├── plots/
│   ├── smiles
│   ├── surfaces
│   └── calibration_figures
│
├── report/
│   └── thesis.pdf
│
└── README.md
```

---

## Results

The classical one-factor Bergomi model reproduces the overall level of VIX volatility but generates smiles that are too flat compared with market observations.

The exponential mixture extension significantly improves the fit by introducing multiple volatility scales and capturing the pronounced positive skew observed in VIX option markets.

---

## Technologies

- Python
- NumPy
- SciPy
- Pandas
- Matplotlib

---

## References

- Bergomi, L. (2005) *Smile Dynamics II*
- Bergomi, L. (2008) *Smile Dynamics III*
- Bergomi, L. (2016) *Stochastic Volatility Modeling*
- Gatheral & Jacquier (2014) *Arbitrage-Free SVI Volatility Surfaces*
- Horvath, Jacquier & Tankov (2018) *Volatility Options in Rough Volatility Models*

---

## Author

**Lucas Last**

Engineering Student in Quantitative Finance  
CY Tech (Mathematics, Modeling & Finance)

Future Master in Finance (MiF) — emlyon business school

Interested in:
- Quantitative Research
- Derivatives Pricing
- Volatility Modeling
- Trading & Structuring
- Asset Management
