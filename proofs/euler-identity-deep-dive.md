# 🏛️ Euler's Identity: Eight Proofs and Deep Insights

**欧拉恒等式8种证明方式** — Exploring the most beautiful equation in mathematics from every angle.

$$e^{i\pi} + 1 = 0$$

## Introduction

Euler's identity connects the five most important constants in mathematics:
- **0** — The additive identity
- **1** — The multiplicative identity
- **π** — The ratio of a circle's circumference to its diameter
- **e** — The base of natural logarithms
- **i** — The imaginary unit

It also uses three fundamental operations exactly once each: addition, multiplication, and exponentiation.

> *"It is absolutely paradoxical; we cannot understand it, and we don't know what it means, but we have proved it, and therefore we know it must be the truth."* — Benjamin Peirce

---

## Proof 1: Taylor Series (The Classic)

The most common proof, using power series expansions.

**Maclaurin series for eˣ:**

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots$$

**Substitute x = iθ:**

$$e^{i\theta} = 1 + i\theta + \frac{(i\theta)^2}{2!} + \frac{(i\theta)^3}{3!} + \frac{(i\theta)^4}{4!} + \cdots$$

**Using i² = -1, i³ = -i, i⁴ = 1, i⁵ = i, ...**

$$e^{i\theta} = \left(1 - \frac{\theta^2}{2!} + \frac{\theta^4}{4!} - \cdots\right) + i\left(\theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} - \cdots\right)$$

**Recognize the series:**

$$e^{i\theta} = \cos\theta + i\sin\theta$$

**Set θ = π:**

$$e^{i\pi} = \cos\pi + i\sin\pi = -1 + 0i = -1$$

$$\boxed{e^{i\pi} + 1 = 0}$$

---

## Proof 2: Differential Equations

Consider the differential equation for simple harmonic motion:

$$y'' + y = 0$$

**Method 1 (real):** Solutions are sin(x) and cos(x). General solution: y = A·cos(x) + B·sin(x)

**Method 2 (exponential guess):** Try y = e^(rx). Then r² + 1 = 0, so r = ±i.

General solution: y = C·e^(ix) + D·e^(-ix)

Since both methods solve the same ODE with same initial conditions:

$$e^{ix} = \cos(x) + i\sin(x)$$

Setting x = π gives Euler's identity.

---

## Proof 3: Polar Coordinates & Rotation

Multiplication by e^(iθ) is a rotation by angle θ in the complex plane.

**Key insight:** The complex exponential is the unique smooth function f(θ) such that:
1. f(θ) has modulus 1 (|f(θ)| = 1 for all θ)
2. f(θ + φ) = f(θ)·f(φ) (functional equation)
3. f'(0) = i (derivative condition)

From properties 1-3, we can derive that f(θ) = e^(iθ) = cos(θ) + i·sin(θ).

A rotation by π radians (180°) maps any point to its negative:

$$e^{i\pi} \cdot 1 = -1 \implies e^{i\pi} = -1 \implies \boxed{e^{i\pi} + 1 = 0}$$

---

## Proof 4: Integration (Logarithmic Approach)

Define the natural logarithm as:

$$\ln(z) = \int_1^z \frac{dt}{t}$$

For z = -1, integrate along the upper semicircle in the complex plane from 1 to -1:

$$\ln(-1) = \int_1^{-1} \frac{dt}{t}$$

Parametrize: t = e^(iθ), dt = ie^(iθ)dθ, θ goes from 0 to π:

$$\ln(-1) = \int_0^{\pi} \frac{ie^{i\theta}}{e^{i\theta}} d\theta = \int_0^{\pi} i \, d\theta = i\pi$$

Since e^(ln(-1)) = -1:

$$e^{i\pi} = -1 \implies \boxed{e^{i\pi} + 1 = 0}$$

---

## Proof 5: Limit Definition

From the definition of e^x as a limit:

$$e^x = \lim_{n \to \infty} \left(1 + \frac{x}{n}\right)^n$$

Set x = iπ:

$$e^{i\pi} = \lim_{n \to \infty} \left(1 + \frac{i\pi}{n}\right)^n$$

Each factor (1 + iπ/n) is a vector in the complex plane with angle ≈ π/n from the real axis. Multiplying n such vectors rotates the total angle by ≈ π radians while maintaining modulus ≈ 1.

As n → ∞, the product converges to a unit vector rotated by exactly π radians: **-1**.

---

## Proof 6: Contour Integration

Evaluate the integral:

$$\oint_C \frac{dz}{z}$$

where C is the unit circle traversed counterclockwise.

**By parametrization** z = e^(iθ), dz = ie^(iθ)dθ:

$$\oint_C \frac{dz}{z} = \int_0^{2\pi} \frac{ie^{i\theta}}{e^{i\theta}} d\theta = \int_0^{2\pi} i \, d\theta = 2\pi i$$

**By the residue theorem:** The integrand has a simple pole at z = 0 with residue 1:

$$\oint_C \frac{dz}{z} = 2\pi i \cdot \text{Res}(f, 0) = 2\pi i$$

The fact that both methods agree depends on e^(2πi) = 1, which is Euler's formula at θ = 2π. The identity e^(iπ) = -1 is the halfway case.

---

## Proof 7: Group Theory

The unit circle in the complex plane forms a group under multiplication, isomorphic to the circle group U(1).

This group is the set {e^(iθ) : θ ∈ ℝ} with multiplication.

The map θ → e^(iθ) is a group homomorphism from (ℝ, +) to (U(1), ·) with kernel 2πℤ.

Since π is half the fundamental period, e^(iπ) must map to the unique element of order 2 in U(1), which is **-1**.

Therefore: **e^(iπ) = -1**

---

## Proof 8: Algebraic Topology

The fundamental group of the circle S¹ is π₁(S¹) = ℤ.

The universal cover of S¹ is ℝ, with covering map p: ℝ → S¹ given by p(t) = e^(2πit).

A loop in S¹ that winds once around corresponds to a path from 0 to 1 in ℝ (or from 0 to 2π in angular measure).

The halfway point of this lifting, t = 1/2 (or θ = π), maps to:

$$p(1/2) = e^{2\pi i \cdot 1/2} = e^{i\pi} = -1$$

This is the only non-trivial element of order 2 in the fundamental group, confirming e^(iπ) = -1.

---

## Philosophical Reflection

Eight proofs, one truth. Euler's identity is remarkable not because it's surprising — it follows inevitably from the definitions — but because it reveals a deep structural unity:

- **Algebra** (Taylor series, group theory) and **analysis** (ODEs, integration) arrive at the same destination
- **Geometry** (rotation, topology) and **arithmetic** (limits) converge on one point
- The imaginary and the real, the circular and the exponential, the discrete and the continuous — all are facets of a single mathematical reality

$$e^{i\pi} + 1 = 0$$

*It is not an equation. It is a poem written in the language of the universe.*
