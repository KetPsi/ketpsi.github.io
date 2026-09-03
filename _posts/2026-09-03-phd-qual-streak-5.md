---
title: "Day 5 of solving PhD qualifying exam problem(s)"
date: 2026-09-03 20:00:00 +0600
categories: [Undergraduate Maths, PhD Qual Streak]
tags: [algebra, linear algebra, determinant]
math: true
---
# Day 5 of solving PhD qualifying exam problem(s): UCLA Qualifying Basic Exam (Fall 2020) Q1

**Question.** Let $M$ be an $n \times n$ matrix with rational entries, such that $M^2 = 2I$.

(a) Prove that $n$ is even.

(b) Give an example of such matrix $M$ for $n = 2$.

**Answer.** 

**(a)**

$$
\mathrm{det}(M^2) = \mathrm{det}(2I) = 2^n \implies \mathrm{det}(M)^2 = 2^n
$$

Therefore, $\mathrm{det}(M) = 2^{n/2}.$ 

Since entries of $M$ are rational, $\mathrm{det}(M) \in \mathbb{Q}$, $n/2$ must be an integer, implying $n$ is even.

**(b)**

$$
\begin{bmatrix}0 & 1\\2 & 0\end{bmatrix}.
$$
