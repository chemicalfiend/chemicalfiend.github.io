---
title: "Hacking Exact Diagonalisation"
date: 2026-08-30T10:07:00
draft: true
math: true
tags: ["quantum-dynamics", "numerics", "many-body", "exact-diagonalisation"]
categories: ["half-baked"]
series: ["quantum-dynamics"]
---

- Exact Diagonalisation

We all know what Exact Diagonalisation (ED) is: you diagonalise the Hamiltonian matrix for a many-body system and get whatever you want from it: ground-state, excited state, thermal state, real-time dynamics, whatever it is. Exact diagonalisation is normally limited to very small systems since memory requirements scale exponentially with system size. In this post, I want to explore a range of condensed matter models we can actually solve with ED, making some simple approximations of course. I like calling this Inexact Diagonalisation, but I don't think that name is going to stick. We are going to use this to extend ED to very exciting condensed matter problems: cavity-coupled excitons, correlated materials, systems with anharmonicity and even polarons.

- Conserved quantities: U(1), SU(2)

ED for the Tavis-Cummings model. ED for XXX model (compare with analytics).

- Krylov-subspace approximations for ED

ED for the Hubbard model.

- Discrete Variable Representation

ED for a Morse potential and for a periodic potential. Colbert-Miller, etc. 

- Variational ED (VED) or ED over a Variational Hilb Space (EDVHS)

ED for the Holstein-Peierls model

- Dynamical Quantum Typicality
