---
title: "Day 1 of solving PhD qualifying question"
categories: [Undergraduate Maths, PhD Qual Streak]
tags: [analysis, cauchy sequence, ]
math: true
---

# Day 1 of solving PhD qualifying question: IU Bloomington Tier 1 Analysis Exam Q1

**Question 1.** A sequence $(x_n)_{n=0}^\infty$ of real numbers satisfies the inequalities

$$
2 \lvert x_{n+1} - x_n \rvert \le \lvert x_n - x_{n-1} \rvert
$$

for every $n \ge 1$. Show that $\lim_{n \to \infty} x_n$ exists and is finite.

**Answer.** We will prove that $(x_n)_{n=0}^\infty$ is Cauchy, i.e., for $\epsilon > 0$, there exists $N_0 \in \mathbb{N}$ such that

$$
\lvert x_m - x_n \rvert, \qquad \forall m > n > N_0.
$$

From the inequality given in the question we get

$$
\lvert x_{n+1} - x_n \rvert \le \frac{1}{2^n} \lvert x_1 - x_0 \rvert.
$$

For being geometric series

$$
\sum_{n=1}^\infty \frac{1}{2^n} = 1.
$$

Therefore, there exists large enough $N \in \mathbb{N}$ such that

$$
\sum_{n=1}^N \frac{1}{2^n} > 1 - \frac{\epsilon}{\lvert x_1 - x_0 \rvert}.
$$

Subtract the above inequality from the previous equality (which is absolutely convergent, so we can indeed subtract), we get

$$
\sum_{n=N+1}^\infty \frac{1}{2^n} < \frac{\epsilon}{\lvert x_1 - x_0 \rvert}.
$$

Set $N_0$ to be that large $N$.

Now for every $m > n > N_0$, we have

$$
\begin{aligned}
& \lvert x_m - x_n \rvert \\
= &\lvert (x_m - x_{m-1}) + (x_{m-1} - x_{m-2}) + \cdots + (x_{n-1} - x_n) \rvert \\
\le & \lvert x_m - x_{m-1} \rvert + \lvert x_{m-1} - x_{m-2} \rvert + \cdots + \lvert x_{n-1} - x_n \rvert \\
\le & \frac{1}{2^{m-1}} \lvert x_1 - x_0 \rvert + \frac{1}{2^{m-2}} \lvert x_1 - x_0 \rvert + \cdots + \frac{1}{2^n} \lvert x_1 - x_0 \rvert \\
\le & \bigg( \frac{1}{2^{m-1}} + \frac{1}{2^{m-2}} + \cdots + \frac{1}{2^n} \bigg) \lvert x_1 - x_0 \rvert \\
< & \bigg(\sum_{n = N+1}^\infty \frac{1}{2^n} \bigg) \lvert x_1 - x_0 \rvert \\
< & \frac{\epsilon}{\lvert x_1 - x_0 \rvert} \lvert x_1 - x_0 \rvert = \epsilon.
\end{aligned}
$$

Hence, the given sequence is Cauchy implying it has a limit and is finite.

Problem source: [https://math.indiana.edu/student-portal/graduate/phd/exams/tier-1-exams/2026-01-t1-analysis.pdf](https://math.indiana.edu/student-portal/graduate/phd/exams/tier-1-exams/2026-01-t1-analysis.pdf)

If you find any mistakes, please let me know. I will greatly appreciate it.
