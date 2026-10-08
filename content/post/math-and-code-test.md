---
title: "Math and Code Test"
date: 2026-08-08T12:00:00-06:00
draft: true
math: true
tags: ["meta"]
categories: ["meta"]
---

Scratch post for verifying the toolchain. Delete once the site is live.

## Inline maths

The Boltzmann factor $e^{-\beta E}$ with $\beta = 1/k_B T$, a Greek letter $\alpha$,
a subscripted operator $\hat{H}_{\text{eff}}$, and a fraction $\tfrac{1}{2}$ mid-sentence.

Inequalities need care in passthrough: write $a \lt b$ rather than a bare `<`.

## Display maths

The time-dependent Schrödinger equation:

$$i\hbar \frac{\partial}{\partial t}\lvert \psi(t) \rangle = \hat{H} \lvert \psi(t) \rangle$$

A cumulant expansion, to check multi-line alignment:

$$
\ln \langle e^{tX} \rangle = \sum_{n=1}^{\infty} \kappa_n \frac{t^n}{n!}
= \kappa_1 t + \kappa_2 \frac{t^2}{2} + \kappa_3 \frac{t^3}{6} + \cdots
$$

An aligned environment:

$$
\begin{aligned}
\dot{\rho}(t) &= -\frac{i}{\hbar}[\hat{H}, \rho(t)] + \mathcal{L}[\rho(t)] \\
\mathcal{L}[\rho] &= \sum_k \gamma_k \left( L_k \rho L_k^\dagger
   \;-\; \tfrac{1}{2}\{ L_k^\dagger L_k, \rho \} \right)
\end{aligned}
$$

A matrix, and a wide expression that should scroll rather than overflow on mobile:

$$
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}
\qquad
\int_{-\infty}^{\infty} e^{-a x^2 + bx}\,\mathrm{d}x = \sqrt{\frac{\pi}{a}}\,e^{b^2/4a}
$$

## Code

```python
import numpy as np

def lanczos(H, v0, k):
    """Minimal Lanczos iteration for a Hermitian H."""
    Q = np.zeros((len(v0), k), dtype=complex)
    Q[:, 0] = v0 / np.linalg.norm(v0)
    alpha, beta = [], []
    for j in range(k - 1):
        w = H @ Q[:, j]
        alpha.append(np.vdot(Q[:, j], w).real)
        w -= alpha[j] * Q[:, j]
        beta.append(np.linalg.norm(w))
        Q[:, j + 1] = w / beta[j]
    return np.array(alpha), np.array(beta), Q
```

```julia
using LinearAlgebra
H = Hermitian(randn(ComplexF64, 8, 8))
vals, vecs = eigen(H)
```

Inline `code spans` and a blockquote:

> Everything should be made as simple as possible, but not simpler.

| Method | Scaling | Exact? |
|---|---|---|
| ED | $\mathcal{O}(4^N)$ | yes |
| Lanczos | $\mathcal{O}(N_{\text{iter}} d)$ | no |
