---
title: Adjoint functors 
author: Mahmudul Hasan Turjoy
date: 2026-08-11 01:30:00 +0600
categories: [Undergraduate Maths, Categories for the idle mathematicians]
tags: [category theory, adjoint functors]
math: true
---

# Adjoint functors

**Definition:** An **adjunction** consists of a pair of functors $F:C \to D$ and $G: D \to C$ together with an isomorphism (in **Set** )

$$
\phi_{c,d}: \mathrm{Hom}_D(Fc, d) \to \mathrm{Hom}_C(c,Gd)
$$

for each $c \in C$ and $d \in D$, that is ''natural'', i.e., for morphisms $c_1 \to c_2$ in $C$ and $d_1 \to d_2$ in $D$, the following diagrams commute:
<div style="display: flex; justify-content: center;">
<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsNCxbMCwwLCJcXG1hdGhybXtIb219X0QoRmMsIGRfMSkiXSxbMSwwLCJcXG1hdGhybXtIb219X0QoRmMsIGRfMSkiXSxbMCwxLCJcXG1hdGhybXtIb219X0QoRmMsIGRfMikiXSxbMSwxLCJcXG1hdGhybXtIb219X0QoRmMsIGRfMikiXSxbMCwyXSxbMSwzXSxbMCwxLCJcXHBoaV97YyxkXzF9Il0sWzIsMywiXFxwaGlfe2MsZF8yfSIsMl1d&embed" width="560" height="304" style="border-radius: 8px; border: none;"></iframe>
</div>
<div style="display: flex; justify-content: center;">
<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsNCxbMCwwLCJcXG1hdGhybXtIb219X0QoRmNfMSwgZCkiXSxbMSwwLCJcXG1hdGhybXtIb219X0MoY18xLEdkKSJdLFswLDEsIlxcbWF0aHJte0hvbX1fRChGY18yLCBkKSJdLFsxLDEsIlxcbWF0aHJte0hvbX1fQyhjXzIsR2QpIl0sWzAsMSwiXFxwaGlfe2NfMSxkfSJdLFsyLDMsIlxccGhpX3tjXzIsZH0iXSxbMywxXSxbMiwwXV0=&embed" width="558" height="304" style="border-radius: 8px; border: none;"></iframe>
</div>

Here, $F$ is called **left adjoint (functor)** to $G$, and $G$ is called **right adjoint (functor)** to $F$. We write $F \dashv G$. 

**Remark:** What are the vertical arrows in these diagrams? These are just canonical maps, e.g., the arrow $\mathrm{Hom}_D(Fc, d1) \to \mathrm{Hom}_D(Fc,d_2)$ is given by

$$
(Fc \xrightarrow{f} d_1) \mapsto (Fc \xrightarrow{f} d_1 \to d_2).
$$

**Example:** Free group functor $F: \textbf{Set} \to \textbf{Grp}$ is left adjoint to the forgetful functor $U: \textbf{Grp} \to \textbf{Set}$.
