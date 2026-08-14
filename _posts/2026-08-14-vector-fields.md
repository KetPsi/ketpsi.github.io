---
title: Vector fields 
date: 2026-08-14 21:02:23 +0600
categories: [Undergraduate Maths, Lie Groups & Lie Algebras]
tags: [tangent bundle, cotangent bundle, vector fields, differential geometry]
math: true
---

# Vector fields 

## Tangent & cotangent bundle

Let $M$ be a smooth manifold.

**Definition (Tangent bundle---incomplete).** The **tangent bundle** of $M$ is defined to be the set

$$
TM = \bigsqcup_{p \in M} T_pM
$$

with a topological and smooth structure.

There is a natural projection map

$$
\pi : TM \to M, (p, T_pM) \mapsto p.
$$


Similarly, one can define **cotangent bundle** to be a certain manifold with 

$$
T^\ast M = \bigsqcup_{p \in M} T^\ast_pM
$$ 

as underlying set.

## Vector field 

**Definition (Vector field).** A vector field on $M$ is a section of the tangent bundle $TM$, i.e., a map $X : M \to TM$ such that $\pi \circ X = \mathrm{id}_M$. Denote $X(p) =: X_p$, which is a tangent vector at $p$.

A vector field $X$ is called **smooth** if the function for any $f \in C^\infty_p(M)$

$$
Xf: M \to \mathbb{R}, p \mapsto X_p(f).
$$

is smooth.

*To be written...*
