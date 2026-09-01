---
title: "Day 4 of solving PhD qualifying exam problem(s)"
categories: [Undergraduate Maths, PhD Qual Streak]
tags: [algebra, abstract algebra, modules, linear maps]
math: true
---

# Day 4 of solving PhD qualifying exam problem(s): Purdue University Qualifying Exam MA 554 (August 2025) Q1 & Q3

Today, I was struggling a bit mentally, so couldn't solve much.

**Question 1.** Let $r, s, n$ be positive integers. Determine the number of distinct $\mathbb{Z}$-linear maps $\mathbb{Z}^r \to (\mathbb{Z}/\mathbb{Z}_n)^s$. (Justify your answer.)

**Answer.** A $\mathbb{Z}$-linear map is uniquely determined by where each standard basis of $\mathbb{Z}^r$ go. For each standard basis of $\mathbb{Z}^r$, we have $n^s$ choices of where they can be mapped in $(\mathbb{Z}/\mathbb{Z}_n)^s$. Therefore, number of distinct $\mathbb{Z}$-linear maps $\mathbb{Z}^r \to (\mathbb{Z}/\mathbb{Z}_n)^s$ is:

$$
n^{rs}.
$$

**Question 2.** Let $R$ be a principle ideal domain. $M$ an $R$-module, and $\varphi, \psi$ nonzero $R$-linear maps $M \to R$. Prove that $\mathrm{ker} \varphi = \mathrm{ker} \psi$ if and only if $a \cdot \varphi = b \cdot \psi$ for some nonzero elements $a, b$ of $R$.

**Answer.** Since the map is nonzero, take any $m \in M \smallsetminus \mathrm{ker} \varphi = \mathrm{ker} \psi$, and set 

$$
a := \psi(m) \quad \text{and} \quad b :=  \varphi(m).
$$

Now, for any $x \in M$,  $\psi(m) x - \psi(x) m \in \mathrm{ker} \ \psi = \mathrm{ker} \ \varphi$ because 

$$
\psi(\psi(m) x - \psi(x) m) = \psi(m) \psi(x) - \psi(x) \psi(m) = 0.
$$

Therefore, 

$$
\varphi(\psi(m) x - \psi(x) m) = \psi(m) \varphi(x) - \varphi(m) \psi(x) = a \varphi(x) - b \psi(x) = 0,
$$

proving 

$$
 a \varphi(x) = b \psi(x).
$$

Problem source: [https://www.math.purdue.edu/files/academic/grad/qualexams/MA55400/ma55400_2025_aug.pdf](https://www.math.purdue.edu/files/academic/grad/qualexams/MA55400/ma55400_2025_aug.pdf)

If you find any mistakes, please let me know. I will greatly appreciate it.
