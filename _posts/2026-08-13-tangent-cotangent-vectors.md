---
title: Tangent & cotangent vectors
date: 2026-08-13 15:04:00 +0800
categories: [Undergraduate Maths, Lie Groups & Lie Algebras]
tags: [tangent vectors, cotangent vectors, differential geometry]
math: true
---

# Tangent & cotangent vectors

Let $M$ be a smooth manifold with dimension $n$. Unless stated otherwise, $(\phi, \mathcal U, \mathcal V)$ will be a chart centered around our concerned point (whatever it will be) for the rest of this post, i.e., if our concerned point is $p \in M$, then $\phi(p)=0$.

**Notation.** By $x^i$, we will sometimes denote the function 

$$
x^i: \mathbb{R^n} \to \mathbb{R}, (x_1, x_2, \ldots, x_n) \mapsto x_i,
$$

and sometimes the unit vector $x^i = (0, \ldots, 0, 1, 0, \ldots, 0) \in \mathbb{R}^n$ ($0$ in the $i$-th position). Moreover, $\phi^i := x^i \circ \phi$.

## Tangent vectors
Let $\mathcal U \subset M$ open. Then define 

$$
C^\infty(\mathcal U) := \{ f : f \text{ is smooth on } \mathcal U \}. 
$$ 

> **Definition (Stalk at point $p$).** The **stalk of $M$ at a point $p \in M$** is defined to be the set 
>
>$$
>C^\infty_p(M) := \left(\bigsqcup_{p \in \mathcal U \subset M \text{ open}} C^\infty(\mathcal U)\right) \bigg/ \sim,
>$$
>
>where the $\sim$ is defined as follows: $(f, \mathcal U) \sim (g, \mathcal V)$ iff there exists an open neighbourhood $\mathcal W \subseteq \mathcal U \cap \mathcal V$ of $p$ such that 
>
>$$
>f|_{\mathcal  W} = g|_{\mathcal W}.
>$$

**Abuse of notation.** We will denote an element $[(f, \mathcal U)]$ of $C^\infty_p(M)$ by its representative function $f$.

> **Definition (Tangent vector).** A **Tangent vector** at a point $p \in M$ is a linear map
>
>$$
>X_p: C^\infty_p(M) \to \mathbb{R}
>$$
>
>that satisfies the *Leibniz rule*
>
>$$
>X_p(fg) = X_p(f) g(p) + X_p(g) f(p).
>$$

The set of all tangent vectors at $p \in M$ forms an $\mathbb{R}$-vector space, which is called the **tangent space** at the point $p$, and denoted by $T_pM$.

> **Lemma 1.** Let $X_p \in T_pM$ a tangent vector. Then for a constant function $c \in C^\infty_p(M)$, $X_p(c) = 0$.

*Proof.* Since $X_p$ is a linear function, 

$$
X_p(c) = cX_p(1). 
$$

So it is enough to prove that, $X_p(1) = 0.$

Notice,

$$
X_p(1) = X_p(1 \cdot 1) = X_p(1) 1(p) + X_p(1) 1(p) = 2X_p(1)
$$

which implies $X_p(1) = 0$.

$$\tag*{$\blacksquare$}$$

**Example.** The maps 

$$
\partial_i: C^\infty_p(M) \to \mathbb R, f \mapsto {\frac{\partial}{\partial x^{i}}} (f \circ \phi^{-1})\bigg|_0
$$

where $1 \le i \le n$, are tangent vectors at $p$, by addition and product rule of partial differentiation in multi-variable calculus.

> **Lemma 2.** Let $f \in C^\infty_p(M)$. Then $f$ is equivalent to the following function
>
>$$
>g(x) = f(p) + \sum_{i=1}^n \phi^i \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0.
>$$

*Proof.* Recall Taylor's theorem with remainder: Let $f$ be a $C^\infty$ function on an open subset $\mathcal U$ of $R^n$ that is star-shaped with respect to a point $p \in \mathcal U$. Then

$$
f(x) = f(p) + \sum_{i=1}^n (x^i(x) - x^i(p)) \frac{\partial f}{\partial x^i}\bigg|_p
$$

Now choose a small enough neighbourhood $\mathcal U_{\phi(p)}$ of $\phi(p)$, which is star-shaped with respect to $\phi(p)$, and define $F = f \circ \phi^{-1}$ on $\mathcal  U_{\phi(p)}$. Apply Taylor's theorem with remainder on $F$, we get (notice, every point around $\phi(p)$ can be represented using $\phi(x)$ for some $x \in \phi^{-1}(\mathcal U)_{\phi(p)}$)

$$
\begin{align*}
& F(\phi(x)) = F(\phi(p)) + \sum_{i=1}^n (x^i(\phi(x)) - x^i(\phi(p))) \frac{\partial F}{\partial x^i}\bigg|_{\phi(p)}\\
\implies &f|_{\phi^{-1}(\mathcal U)}(x) = f(p) + \sum_{i=1}^n (\phi^i(x) - x^i(0)) \frac{\partial f \circ \phi^{-1}}{\partial x^i}\bigg|_0\\
\implies &f|_{\phi^{-1}(\mathcal U)}(x) = f(p) + \sum_{i=1}^n \phi^i(x) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0.
\end{align*}
$$

So, on $\phi^{-1}(\mathcal U_{\phi(p)})$, 

$$
f = f(p) + \sum_{i=1}^n (x^i \circ \phi) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0 =: g(x),
$$

proving the equivalence.

> **Theorem.** $T_pM$ is an $n$-dimensional $\mathbb{R}$-vector space.

*Proof.* We claim that the set $\\{\partial_i\\}_{i=1}^{n}$ ($\partial_i$ are defined as in the example above) forms a basis for $T_pM$.

First we will prove that $\partial_i$'s are linearly independent.

Let 

$$
\sum_{i=1}^n c_i \partial_i = 0, c_i \in \mathbb{R}.
$$

Then for the smooth function $x^j \circ \phi$,

$$
\begin{align*}
&\left(\sum_{i=1}^n c_i \partial_i\right) (x^j \circ \phi) = 0\\
\implies &\sum_{i=1}^n c_i \partial_i (x^j \circ \phi) = 0\\
\implies &\sum_{i=1}^n c_i {\frac{\partial}{\partial x^{i}}} (x^j \circ \phi \circ \phi^{-1})\bigg|_0 = 0\\
\implies &\sum_{i=1}^n c_i {\frac{\partial}{\partial x^{i}}} (x^j)\bigg|_0 = 0\\
\implies &\sum_{i=1}^n c_i \delta_{ij} = 0
\end{align*}
$$

which implies $c_i = 0$ for all $1 \le i \le n$. Hence, $\partial_i$'s are linearly independent.

Let $X_p : C^\infty_p(M) \to \mathbb{R}$ be a tangent vector. We claim

$$
X_p = \sum_{i=1}^n X_p(x^i \circ \phi) \partial_i
$$

Take 

$$
f \sim f(p) + \sum_{i=1}^n (x^i \circ \phi^i) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0 \in C^\infty_p(M).
$$

Then

$$
\begin{align*}
& \ X_p\left(f(p) + \sum_{i=1}^n (x^i \circ \phi) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0\right)\\
= & \ X_p(f(p)) + X_p\left(\sum_{i=1}^n (x^i \circ \phi) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0\right)\\
= & \ 0 + \sum_{i=1}^n X_p \left( (x^i \circ \phi) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0\right)\\
= & \ \sum_{i=1}^n X_p\left( \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0\right) (x^i \circ \phi)(p) + X_p(x^i \circ \phi) \frac{\partial}{\partial x^i} (f \circ \phi^{-1})\bigg|_0\\
= & \ \sum_{i=1}^n 0 +  X_p(x^i \circ \phi) \partial_i(f)\\
= & \ \left(\sum_{i=1}^n X_p(x^i \circ \phi) \partial_i\right)(f),
\end{align*},
$$

which implies $X_p = \sum_{i=1}^n X_p(x^i \circ \phi) \partial_i$.


Therefore, $\partial_i$'s span $T_pM$ as well, proving  $\partial_i$'s form a basis for $T_pM$. Hence, $T_pM$ is an  $n$-dimensional vector space.

$$\tag*{$\blacksquare$}$$

## Cotangent vectors

>**Definition (Cotangent vector).** The dual space $T_pM^\ast$ of the tangent space $T_pM$ is called the **cotangent space**, and its elements are called **cotangent vectors**.

>**Definition (Differential).** Let $\varphi: M \to N$ be a smooth map. Then for each $p \in M$, the **differential** of $\varphi$ is the linear map 
>
>$$
>d\varphi_p : T_pM \to T_{\varphi(p)}N, \ d\varphi_p(X_p)(f) = X_p(f \circ \varphi),
>$$
>
>for all $X_p \in T_pM$ and all  $f \in C^\infty(N)$.

Now, in the special case where $f: M \to \mathbb{R}$ is a smooth function, we have $T_{f(p)}N \cong \mathbb{R}$ (as vector spaces via the isomorphism $X_p \mapsto X_p(\mathrm{id}_\mathbb{R}$). Then we have a linear map

$$
df_p: T_pM \to T_{f(p)}\mathbb{R} \cong \mathbb{R}.
$$

Since $df_p$ is a linear functional on $T_pM$, therefore, $df_p$ is a cotangent vector, where

$$
df_pX_p = df_pX_p(\mathrm{id_\mathbb{R}}) = X_p(\mathrm{id}_\mathbb{R} \circ f) = X_p(f).
$$

Furthermore, dual basis of $\\{\partial_1, \ldots, \partial_n\\}$ in  $T_pM^\ast$ is  $\\{dx^1, \ldots, dx^n\\}$.

Indeed,

$$
dx^i(\partial_j) = \partial_j(x^i) = \delta_{ij}.
$$

Therefore, for any cotangent vector $w \in T_pM^*$, we have

$$
w = \sum_{i=1}^n w(\partial_i) dx^i.
$$

