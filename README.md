# Bergomi VIX Volatility Model

Pricing and calibration of VIX options under Bergomi forward variance models.

## Project Overview

This project investigates the pricing and calibration of VIX options using forward variance models introduced by Lorenzo Bergomi.

The objective is to:

- Simulate forward variance dynamics
- Price VIX futures and options
- Compute implied volatilities
- Reproduce VIX volatility smiles
- Calibrate model parameters to market data

---

## Mathematical Framework

### Bergomi One-Factor Model

The forward variance follows:

dξ(t,T) = ξ(t,T) × φ(T−t) × dW(t)

where

φ(τ) = ω × exp(−kτ)

Parameters:

- ω : volatility of variance
- k : mean reversion speed
- 1/k : characteristic time scale

---

### Exponential Mixture Extension

To better reproduce observed VIX smiles, the model is extended using a mixture of exponentials:

ξ(t,T) = ξ(0,T) × [(1−γ)G₁ + γG₂]

where:

- G₁ and G₂ are lognormal factors
- γ controls the weight of each factor
- ω₁ and ω₂ represent two different volatility scales

This extension generates significantly steeper positive skew, closer to market observations.

---

## Main Features

### Market Data Processing

- VIX option data import
- Bid/Ask filtering
- Mid-price computation
- VIX forward extraction

### Monte Carlo Pricing

- Forward variance simulation
- VIX futures pricing
- European Call pricing
- European Put pricing

### Implied Volatility

- Black model implementation
- Implied volatility inversion
- Smile generation

### Calibration

- Single maturity calibration
- Multi-maturity calibration
- Least-squares optimization

### Visualization

- Market vs Model smiles
- Calibration diagnostics
- Parameter sensitivity analysis

---

## Results

### One-Factor Bergomi

Advantages:

- Simple implementation
- Fast simulation
- Consistent forward variance dynamics

Limitations:

- Produces VIX smiles that are too flat

### Exponential Mixture Model

Advantages:

- Better fit to market smiles
- Captures positive skew
- More realistic volatility dynamics

---

## Technologies

- Python
- NumPy
- SciPy
- Pandas
- Matplotlib

---

## References

- Bergomi (2005) — Smile Dynamics II
- Bergomi (2008) — Smile Dynamics III
- Bergomi (2016) — Stochastic Volatility Modeling
- Gatheral & Jacquier (2014) — Arbitrage-Free SVI Volatility Surfaces

---

## Author

**Lucas Last**

Engineering Student in Quantitative Finance — CY Tech

Future Master in Finance (MiF) — emlyon business school

Interests:

- Quantitative Research
- Derivatives Pricing
- Volatility Modeling
- Trading
- Structuring
- Asset Management
