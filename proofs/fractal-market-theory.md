# 📈 Fractal Market Theory

**分形市场理论** — Applying fractal geometry and self-similarity to understand financial markets.

$$H \in (0, 1) \quad \text{Hurst Exponent}$$

## Introduction

Traditional finance assumes markets follow random walks (Brownian motion). Reality disagrees: markets exhibit crashes, bubbles, volatility clustering, and fat tails — all features of **fractal** processes. Fractal Market Theory, developed by Edgar Peters (1994), replaces the random walk with fractal geometry.

---

## Part 1: Why Markets Are Fractal

### Self-Similarity at All Time Scales

A price chart looks statistically similar whether you zoom in to 1-minute bars or zoom out to monthly data. There is no "characteristic time scale" — the hallmark of a fractal.

### Power-Law Distributions

Unlike the normal distribution assumed by Black-Scholes, market returns follow power laws:

$$P(|r| > x) \sim x^{-\alpha}$$

where α ≈ 3 (the "inverse cubic law") for stock returns, vs. α → ∞ for normal distributions.

### Volatility Clustering

Large changes tend to cluster together — calm periods alternate with turbulent ones. This is quantified by the Hurst exponent H > 0.5 (persistent behavior).

---

## Part 2: The Hurst Exponent

### Definition

The Hurst exponent H measures the long-term memory of a time series:

| H Value | Process Type | Market Behavior |
|---------|-------------|-----------------|
| H = 0.5 | Random walk | Efficient market (EMH) |
| 0.5 < H < 1 | Persistent | Trends continue (momentum) |
| 0 < H < 0.5 | Anti-persistent | Mean reversion |
| H ≈ 0.6-0.7 | Typical market | Real markets show persistence |

### Rescaled Range (R/S) Analysis

The classic method to estimate H:

1. Divide time series of length N into sub-periods
2. For each sub-period, compute:
   - Mean: m = (1/n)Σxᵢ
   - Deviations: yᵢ = Σⱼ₌₁ⁱ(xⱼ - m) for i = 1,...,n
   - Range: R = max(yᵢ) - min(yᵢ)
   - Standard deviation: S
3. Compute R/S ratio
4. The scaling law: (R/S) ~ c · n^H

### Empirical Results

| Market | H (Daily) | H (Weekly) | H (Monthly) |
|--------|-----------|------------|-------------|
| S&P 500 | 0.61 | 0.58 | 0.55 |
| USD/JPY | 0.64 | 0.60 | 0.56 |
| Gold | 0.58 | 0.55 | 0.52 |
| Bitcoin | 0.68 | 0.62 | 0.57 |

All markets show H > 0.5, indicating persistent (fractal) behavior.

---

## Part 3: Fractional Brownian Motion

### Definition

Fractional Brownian motion (fBm) with Hurst parameter H is a Gaussian process B_H(t) with:

$$\text{Cov}(B_H(s), B_H(t)) = \frac{1}{2}(|s|^{2H} + |t|^{2H} - |t-s|^{2H})$$

Key properties:
- H = 0.5: Standard Brownian motion (independent increments)
- H > 0.5: Positively correlated increments (trend-following)
- H < 0.5: Negatively correlated increments (mean-reverting)

### Market Implications

When H > 0.5 (persistent):
- Trends are more likely to continue than reverse
- Momentum strategies have positive expected value
- Risk is underestimated by normal-distribution models
- Crashes are more probable than Black-Scholes predicts

---

## Part 4: Multifractal Model of Asset Returns (MMAR)

### Mandelbrot's Framework

The MMAR (Mandelbrot, Fisher, Calvet 1997) combines:

1. **Compound process**: X(t) = B_H[θ(t)]
   - B_H = fractional Brownian motion (price changes)
   - θ(t) = multifractal trading time (deformation of clock time)

2. **Trading time** captures the fact that market time flows faster during volatile periods and slower during calm ones.

3. **Multifractal spectrum** f(α) describes the distribution of local Hölder exponents:
   - A single H → monofractal (simple self-similarity)
   - A range of H values → multifractal (rich self-similarity structure)

### Empirical Evidence

Real markets exhibit **multifractality** — the local regularity of price changes varies across time, with:
- Smooth periods (high H) during calm markets
- Rough periods (low H) during crises
- The spectrum f(α) is concave, confirming multifractal structure

---

## Part 5: Practical Applications

### Risk Management

| Model | Crash Probability | Reality |
|-------|------------------|---------|
| Normal (σ = 1%) | 1 in 10¹⁵⁷ days | Absurdly low |
| Fractal (α = 3) | 1 in 1000 days | Matches history |

### Trading Strategies

1. **Hurst-based allocation**: Increase equity allocation when H > 0.5 (trending), decrease when H < 0.5 (mean-reverting)
2. **Fractal dimension timing**: Use changing fractal dimension as regime indicator
3. **Multi-horizon diversification**: Since self-similarity exists across time scales, diversify across holding periods, not just assets

### Option Pricing

Replacing Black-Scholes with fractal models:
- Fatter tails → higher option prices for out-of-the-money options
- Volatility smile emerges naturally from the fractal structure
- No need for ad-hoc volatility surface fitting

---

## Part 6: Criticisms and Limitations

1. **Statistical uncertainty**: Hurst exponent estimates have wide confidence intervals
2. **Non-stationarity**: H changes over time; markets may transition between fractal and random
3. **Self-fulfilling prophecy**: If traders use fractal analysis, do they create or destroy fractal patterns?
4. **Data requirements**: Reliable H estimation needs 10,000+ observations
5. **Alternative explanations**: Behavioral finance and regime-switching models can also explain persistence

---

## Key References

- Mandelbrot, B. (1963). "The Variation of Certain Speculative Prices." *Journal of Business*
- Peters, E. (1994). *Fractal Market Analysis*
- Mandelbrot, B., Fisher, A., Calvet, L. (1997). "A Multifractal Model of Asset Returns." *Cowles Foundation Discussion Paper*
- Cont, R. (2001). "Empirical properties of asset returns." *Quantitative Finance*

---

*Markets are not random walks. They are fractal landscapes — self-similar across time scales, with memory that extends far beyond the present moment.*
