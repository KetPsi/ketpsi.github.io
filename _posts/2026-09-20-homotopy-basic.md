---
title: "Homotopic maps & homotopic spaces"
date: 2026-09-23 19:23:00 +0600
categories: [Undergraduate Maths, Algebraic topology]
tags: [homotopy, algebraic topology, homotopic spaces, homotopic maps]
math: true
---
# Homotopic maps & homotopic spaces

This blog closely follows this [YouTube video](https://youtu.be/42MLs58xh1E?si=dDLcfI68fQT8r1XG).

## Homotopy

> **Definition (Homeomorphism)** Let $X, Y$ be topological spaces. We say $X$ and $Y$ are **homeomorhpic** to each other, and denote it by $X \cong Y$, if there exists continuous maps
> 
> $$
> f: X \to Y, \qquad g: Y \to X
> $$
>
> such that 
> 
> $$
> f \circ g = \mathrm{id}_Y, \qquad g \circ f = \mathrm{id}_X.
> $$
{: .definition}

Homeomorphism is a very strong requirement, and in practice it is often difficult to prove/disprove whether two spaces are homeomorphic. Therefore, we need some weaker conditions that remain invariant under homeomorphism, so that we can at least disprove homeomorphism in many cases. Such a weaker condition is: **Homotopy**, which is the subject of this blog. 

> **Definition (Homotopic maps):** Let $X$ and  $Y$ be two spaces. We say two continuous maps  $f, g: X \to Y$ are **homotopic**, and denote it by $f \simeq g$, if there exists a continuous map 
> 
> $$
> h: X \times [0,1] \to Y
> $$
> 
> so that 
> 
> $$
> h(x, 0) = f(x), \qquad h(x, 1) = g(x).
> $$
{: .definition}

Intuitively, the homotopy map $h$ continuously changes the function from $f$ to $g$. 

> **Definition (Homotopic spaces):** Let $X$ and $Y$ be two topological spaces. We say that $X$ and $Y$ are **homotopic spaces**, and denote it by $X \simeq Y$ if we can find two continuous maps 
> 
> $$
> f: X \to Y, \qquad g: Y \to X
> $$
> 
> such that 
>
> $$
> f \circ g \simeq \mathrm{id}_Y, \qquad g \circ f \simeq \mathrm{id}_X.
> $$
{: .definition}

**Examples 1.**

$X := \mathbb{C}^\times$ (the punctured plane with standard topology), and $Y = S^1$ (the unit circle with standard topology) are homotopic spaces. 

Let's prove it rigorously. Define 

$$
f: \mathbb{C}^\times \to S^1, x \mapsto \frac{x}{\lVert x \rVert}
$$

and

$$
g: S^1 \to \mathbb{C}^\times, x \mapsto x.
$$

$f$ is continuous because  $f$ is quotient of two continuous maps, namely,  $\mathrm{id}_{\mathbb{C}^\times}$ and $\lVert . \rVert$, where denominator function $\lVert . \rVert$ is non-zero because norm of a non-zero complex number is zero. And $g$ is continuous because it is just inclusion map.

Now we will prove that 

$$
f \circ g \simeq \mathrm{id}_{S^1} \qquad \text{and} \qquad g \circ f \simeq \mathrm{id}_{\mathbb{C}^\times}.
$$

To prove $f \circ g \simeq \mathrm{id}_{S^1}$, define 

$$
H: S^1 \times I \to S^1
$$

by

$$
H(x,t) = (1 - t) (f \circ g)(x) + t\mathrm{id}_{S^1}(x).
$$

By construction, $H$ is continuous, and a homotopy between  $f \circ g$ and  $\mathrm{id}_{S^1}$ once we check the well-definedness of $H$:

Let $(x,t) \in S^1 \times I$. Then $\lVert x \rVert = 1$.

And 

$$
\begin{align*}
H(x,t) &= (1-t)(f \circ g)(x) + t\mathrm{id}_{S^1}(x)\\
&= (1-t) f(g(x))+ tx\\
&= (1-t)f(x) + tx\\
&= (1-t) \frac{x}{\lVert x \rVert}+ tx\\
&= (1-t)x + tx\\
&= x - tx + tx\\
&= x.
\end{align*}
$$

Therefore, $\lVert H(x,t) \rVert = \lVert x \rVert = 1 \implies H(x,t) \in S^1$. Hence,

$$
f \circ g \simeq \mathrm{id}_{S^1}.
$$

To prove $g \circ f \simeq \mathrm{id}_{\mathbb{C}^\times}$, define

$$
J: \mathbb{C}^\times \times I \to \mathbb{C}^\times
$$

by

$$
J(x,t) = (1-t)(g \circ f)(x) + t\mathrm{id}_{\mathbb{C}^\times}(x).
$$

By construction, $J$ is continuous, and a homotopy between  $g \circ f$ and  $\mathrm{id}_{\mathbb{C}^\times}$ once we prove the well-definedness of $J$:

Let $(x,t) \in \mathbb{C}^\times \times I$. Then $\lVert x \rVert > 0$.

For $t = 0,1$, it is immediate that $H(x,t) \in \mathbb{C}^\times$. When $t \neq 0, 1$

$$
\begin{align*}
&\frac{1}{t} > 1\\
\implies &\frac{1}{t} + \lVert x \rVert > 1\\
\implies &1 + \lVert x \rVert t > t\\
\implies &1 - t + \lVert x \rVert t > 0\\
\implies &x(1 - t + \lVert x \rVert t) \neq 0\\
\implies &\frac{x(1 - t + \lVert x \rVert t)}{\lVert x \rVert} \neq 0\\ 
\implies & \frac{x}{\lVert x \rVert}(1 - t) + x t \neq 0\\
\implies & (g \circ f)(x) (1-t) + \mathrm{id}_{\mathbb{C}^\times}(x) t \neq 0\\
\implies &H(x,t) \neq 0.
\end{align*}
$$

Therefore, $H(x,t) \in \mathbb{C}^\times$ for all $(x, t) \in \mathbb{C}^\times \times I$. Hence,

$$
g \circ f \simeq \mathrm{id}_{\mathbb{C}^\times}, 
$$

proving

$$
\mathbb{C}^\times \simeq S^1.
$$

**Example 2.** Let $X \subseteq \mathbb{R}^n$ be convex subset, that is, for any $x, y \in X$, the line 

$$
[x,y] := \{(1-t)x + ty\},
$$

joining $x$ to $y$ lies in $X$ (i.e., $[x,y] \subseteq X$). If $p \in X$, then $X \simeq \{p\} =: Y$.

Let us prove it rigorously. Define 

$$
f: X \to Y, x \mapsto p
$$

and 

$$
g: Y \to X, p \mapsto p.
$$

$f, g$ are immediately seen to be continuous. Now we want to show that 

$$
f \circ g \simeq \mathrm{id}_Y \qquad \text{and} \qquad g \circ f \simeq \mathrm{id}_X.
$$

Since $f \circ g = \mathrm{id}_Y$, we get  $f \circ g \simeq \mathrm{id}_Y$ for free.

To prove  $g \circ f \simeq \mathrm{id}_X$, define 

$$
H : X \times I \to X
$$

by

$$
H(x,t) = (1-t) (g\circ f)(x) + t \mathrm{id}_X(x).
$$

By construction, $H$ is continuous, and is homotopy between  $g \circ f$ and  $\mathrm{id}_X$ once we prove  $H$ is well-defined: 

Let  $(x,t) \in X \times I$. Then 

$$
\begin{align*}
H(x,t) &= (1-t)(g\circ f)(x) + t \mathrm{id}_X(x)\\
&= (1-t)g(f(x)) + tx\\
&= (1-t)g(p) + tx\\
&= (1-t)p + tx.
\end{align*}
$$

So $H(x,t) = (1-t)p + tx \in X$ for all  $x \in X$ and  $t \in [0,1]$, by the convexity of  $X$. 

Hence,  $H$ is a well-defined homotopy between  $g \circ f$ and  $\mathrm{id}_X$, proving 

$$
g \circ f \simeq \mathrm{id}_X
$$

as well. Hence, $X \simeq \\{p\\}$.
