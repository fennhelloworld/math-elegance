# 🌊 Riemann Zeta Function Visualization

**黎曼Zeta函数可视化** — Exploring the most important unsolved problem in mathematics through visual and computational exploration.

$$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$

## The Million-Dollar Question

The Riemann Hypothesis — that all non-trivial zeros of ζ(s) lie on the line Re(s) = 1/2 — is the most important unsolved problem in mathematics, with a $1,000,000 Millennium Prize.

This document provides a visual and mathematical exploration of this profound function.

---

## Part 1: The Zeta Function in the Complex Plane

### Domain Coloring

The zeta function maps the complex plane to the complex plane. Domain coloring represents:
- **Hue** → argument (angle) of ζ(s)
- **Brightness** → magnitude of ζ(s)
- **Zeros** → points where all colors converge (black holes in the color map)
- **Poles** → points where brightness goes to infinity (white points)

### Critical Strip

The region 0 < Re(s) < 1 is called the **critical strip**. The line Re(s) = 1/2 is the **critical line**.

All non-trivial zeros found so far lie exactly on the critical line:
- First zero: s = 1/2 + 14.134725...i
- Second zero: s = 1/2 + 21.022040...i
- Third zero: s = 1/2 + 25.010858...i
- Over 10¹³ zeros have been verified on the critical line

### The Functional Equation

$$\zeta(s) = 2^s \pi^{s-1} \sin\left(\frac{\pi s}{2}\right) \Gamma(1-s) \zeta(1-s)$$

This symmetry relates ζ(s) to ζ(1-s), making the critical line Re(s) = 1/2 the "mirror" of the function.

---

## Part 2: Visualizing the Zeros

### The First 10 Non-Trivial Zeros

| # | Re(s) | Im(s) (approx) |
|---|-------|-----------------|
| 1 | 1/2 | 14.134725 |
| 2 | 1/2 | 21.022040 |
| 3 | 1/2 | 25.010858 |
| 4 | 1/2 | 30.424876 |
| 5 | 1/2 | 32.935062 |
| 6 | 1/2 | 37.586178 |
| 7 | 1/2 | 40.918719 |
| 8 | 1/2 | 43.327073 |
| 9 | 1/2 | 48.005151 |
| 10 | 1/2 | 49.773832 |

All lie exactly on the critical line.

### Zero Spacing Distribution

The normalized spacings between consecutive zeros follow the **GUE distribution** (Gaussian Unitary Ensemble) from random matrix theory — the same distribution as eigenvalue spacings of large random Hermitian matrices.

This connection between number theory and random matrices is one of the deepest insights in modern mathematics.

---

## Part 3: Why It Matters

### Connection to Prime Numbers

The Euler product formula reveals that ζ(s) encodes the distribution of ALL prime numbers:

$$\zeta(s) = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$

The zeros of ζ(s) determine the error term in the prime counting function π(x):

$$\pi(x) = \text{Li}(x) - \sum_{\rho} \text{Li}(x^{\rho}) + \text{small terms}$$

where ρ runs over the non-trivial zeros of ζ(s).

**If the Riemann Hypothesis is true**, the error in estimating the number of primes below x is O(x^(1/2) ln(x)) — the best possible bound.

### Practical Implications

| Field | Connection |
|-------|-----------|
| Cryptography | RSA security depends on prime distribution |
| Physics | Zeta zeros ↔ quantum chaos eigenvalues |
| Quantum Mechanics | Hilbert-Pólya conjecture: zeros as eigenvalues |
| Statistics | GUE distribution connections |
| Engineering | Zeta regularization in quantum field theory |

---

## Part 4: Computational Exploration

### Approximating Zeta

```python
import numpy as np

def zeta_naive(s, N=100000):
    """Naive Dirichlet series approximation."""
    return sum(1/n**s for n in range(1, N+1))

def zeta_product(s, primes):
    """Euler product approximation."""
    return np.prod([1/(1 - p**(-s)) for p in primes])

# First 1000 primes for product approximation
primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, ...]
```

### Finding Zeros Numerically

```python
from mpmath import zeta, diff

def find_zero(t_start, t_end, step=0.1):
    """Find zeros of Z(t) = real part of ζ(1/2 + it)."""
    t = t_start
    while t < t_end:
        z1 = zeta(0.5 + t*1j).real
        z2 = zeta(0.5 + (t+step)*1j).real
        if z1 * z2 < 0:  # Sign change = zero crossing
            # Bisect to refine
            ...
        t += step
```

---

## Part 5: The Critical Line Visualization

Imagine the complex plane with:
- **Horizontal axis**: Re(s), from 0 to 1
- **Vertical axis**: Im(s), from 0 to 50

The ζ(s) function creates a landscape where:
- A **ridge** runs along Re(s) = 1 (the series converges absolutely here)
- **Valleys** (zeros) appear along Re(s) = 1/2 at regular intervals
- The **trivial zeros** appear at s = -2, -4, -6, ... (from the sin factor in the functional equation)

The visual structure is mesmerizing: a function that looks chaotic on the surface, but whose zeros align with impossible precision on a single vertical line.

---

## Open Questions

1. **Riemann Hypothesis**: Do ALL non-trivial zeros lie on Re(s) = 1/2?
2. **Zero multiplicity**: Are all zeros simple?
3. **GUE universality**: Does the zero spacing distribution hold to infinity?
4. **Hilbert-Pólya**: Is there a self-adjoint operator whose eigenvalues are the zeta zeros?

---

*"The zeta function knows things about primes that we cannot yet prove it knows."*
