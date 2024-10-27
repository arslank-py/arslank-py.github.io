---
title: "Construction of Measures and Outer Measures"
topic: "Analysis"
chapter: "Measure Theory"
section: "construction"
layout: note
permalink: "/notes/analysis/measure/construction/"
order: 3

subtitle: 
date: 2024-10-11
keywords: analysis, measure theory
published: true
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed.; Folland, G. B. (1999). Real analysis: Modern techniques and their applications (2nd ed.)."
---

When constructing measures, the general intuition is to approximate the measure of a set from above or from below, where the measure is obtained if these approximations agree in the limit. This allows us to define measures on smaller collections, rather than a full $\sigma$-algebra, and sidestep some of the technicalities in defining specific measures. 

## Outer Measures

We develop one of the standard techniques for constructing measures. An outer measure allows us to approximate the measure of a set from "above" or from the "outside."  

<div class='definition' name='Outer measure'>
Let $X$ be a set, and let $\mathscr{P}(X)=2^X$ be the collection of all subsets of $X$. An outer measure on $X$ is a function $\mu^*:\mathscr{P}(X)\to[0,+\infty] $ such that
<ol type="a">
    <li>$\mu^*(\emptyset)=0$,</li>
    <li>if $E\subseteq G\subseteq X$, then $\mu^*(E)\leq \mu^*(G)$, and</li>
    <li>if $\{E_n\}$ is an infinte sequence of subsets of $X$, then
    \[
        \mu^*\left(\bigcup_{n=1}^\infty E_n\right)\leq\sum_{n=1}^\infty \mu^*(E_n).
    \] 
    </li>
</ol>
</div>

Thus an outer measure on $X$ is a monotone and countably subadditive function from $\mathscr{P}(X)$ to $[0,+\infty]$ whose value at $\emptyset$ is 0. Many important measure can be derived from outer measures by restricting $\mu^*$ to a special $\sigma$-algebra which we discuss later. 

#### Examples:

<ol>
    <li>Let $X$ be an arbitray set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(E)=0$ if $E$ is countable, and $\mu^*(E)=1$ if $E$ is uncountable. Then $\mu^*$ is an outer measure.
    </li>
    <li>Let $X$ be an infinite set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(E)=0$ if $E$ is finite, and $\mu^*(E)=1$ if $E$ is infinite. Then $\mu^*$ fails to be countably subadditive and so not an outer measure.</li>
</ol>

To define an outer measure, we often construct the outer measure on some "nice" sets (like rectangles or balls), followed by approximating arbitrary sets in our space from above using countable unions of these nice sets. That is, an outer measure of an arbirary set can be obtained by taking the smallest measure of the nice sets that cover it. We now make this intuition precise with the following proposition. 

<div class='proposition' name='Constructing an outer measure'>
Let $X$ be a set and suppose $\FF\subseteq \PP(X)$ is an arbitrary collection of subsets such that  $\emptyset,X\in\FF$. Let $\rho:\FF\to[0,+\infty]$ be such that $\rho(\emptyset)=0$. Then $\mu^*:\PP(X)\to[0,+\infty]$ for all $E\subseteq X$ is defined as
\[
    \mu^*(E)=\inf\left\{\sum_{i=1}^\infty \rho(F_i) : F_i\in\FF, \text{ }E\subseteq\bigcup_{i=1}^\infty F_i\right\}.
\]
Then $\mu^*$ is an outer measure on $X$. 
</div>

<details class='proof'>
<summary>Proof.</summary>
It is clear that $\mu^*(\emptyset)=0$  since any set trivially covers $\emptyset$. If $E\subseteq G$, then $\mu^*(E)\leq \mu^*(G)$  as a covering for $G$ induces a covering for $E$ and thus the set over which we are taking the infimum is smaller for $E$. 

<br><br>
We now consider the countable subadditivity of $\mu^*$. Fix $\varepsilon>0$  and let $\{E_k\}_{k=1}^\infty$  be an arbitrary sequence of subsets of $X$. Then for any given $E_k\subseteq X$, there exists a sequence $\{F_j^k\}_{j=1}^\infty$  such that $F_j^k\in\FF$  and $E_k\subseteq \bigcup_{j=1}^\infty F_j^k$ . Moreover, we may choose this sequence so that
\[
    \sum_{j=1}^\infty \rho(F_j^k) < \mu^*(E_k)+\frac{\varepsilon}{2^k}.
\]
Then we have
\[
    \bigcup_{k=1}^\infty E_k\subseteq \bigcup_{j,k=1}^\infty F_j^k
\]
and
\[
    \mu^*\left(\bigcup_{k=1}^\infty E_k\right)\leq \sum_{j,k=1}^\infty \rho(F_j^k) < \sum_{k=1}^\infty \mu^*(E_k)+\varepsilon.
\]
Since $\varepsilon$ was arbitrary, we conclude that $\mu^*$ is an outer measure. 
</details>

Note that for any $E\subseteq X$ the set over which we are taking the infimum is nonempty since $X\in\FF$. 

<br><br>
As briefly referenced above, Lebesgue's notion of a measurable set was defined using inner and outer measures $(\lambda^\*(E)=\lambda_{\*}(E))$ . While Lebesgue's formulation relies on certain topological properties of $\R$ (e.g., completeness, separability, regularity of $\lambda$), Carath&eacute;odory’s criterion generalizes the characterization of measurability to abstract spaces. See a nice counterexample to Lebesgue's formulation in <a href="https://math.stackexchange.com/questions/4381477/understanding-when-a-set-is-outer-measurable">this link</a>. 

<div class='definition' name='Carath&eacute;odory’s criterion for μ*-measurability'>
Let $X$ be a set and let $\mu^*$ be an outer measure on $X$. A subset $F\subseteq X$ is $\mu^*$-measurable (or measurable with respect to $\mu^*$) if
\[
    \mu^*(E)=\mu^*(E\cap F)+\mu^*(E\cap F^c)
\]
holds for every subset $E\subseteq X$. 
</div>

Intuitively, a $\mu^\*$-measurable subset of $X$ is one that divides each subset of $X$ in such a way that the sizes (as measured by $\mu^\*$) of the pieces add properly. 

<br><br>
Note that the subadditivity of the outer measure $\mu^\*$ implies that
\\[
    \mu^\*(E)=\mu^*((E\cap F)\cup(E\cap F^c))\leq \mu^\*(E\cap F)+\mu^\*(E\cap F^c)
\\]
holds for all subsets $E,F\subseteq X$. Thus it suffices to check the reverse inequality. Moreover, if $\mu^\*(E)=+\infty$ , this is trivially satisfied, so we have the following lemma.

<div class='lemma'>
Let $\mu^*$ be an outer measure on $X$. A set $F\subseteq X$ is $\mu^*$-measurable if and only if
\[
    \mu^*(E)\geq \mu^*(E\cap F)+\mu^*(E\cap F^c)
\]
holds for each subset $E\subseteq X$ , where $\mu^*(E)<+\infty$ . 
</div>

## Extension Theorems

We now arrive at two fundamental theorems, allowing us to obtain genuine measures from outer measures. This is done by taking an outer measure and restricting ourselves to the $\mu^\*$-measurable sets. We first prove a quick result proceeding from Carath&eacute;odory’s criterion and Lemma 1. This proposition will aid us in our proof of Carath&eacute;odory theorem below and implies the restriction of $\mu^\*$ to $\MM_{\mu^\*}$ is complete (which we define later down the road). 

<div class='proposition'>
Let $\mu^*$ be an outer measure on $X$. Then each subset $F\subseteq X$ that satisfies $\mu^*(F)=0$  or that satisfies $\mu^*(F^c)=0$  is $\mu^*$-measurable . 
</div>

<details class='proof'>
<summary>Proof.</summary>
Assume that $\mu^*(F)=0$  or that $\mu^*(F^c)=0$ . According to Lemma 1, we need only check that each subset $E\subseteq X$ satisfies
\[
    \mu^*(E)\geq \mu^*(E\cap F)+\mu^*(E\cap F^c).
\]
However our assumption about $F$ and the monotonicity of $\mu^*$ imply that one of the terms on the right-hand side of this inequality vanishes and that the other is at most $\mu^*(E)$ ; thus the required inequality follows. 
</details>

It follows that the sets $\emptyset$ and $X$ are measurable for every outer measure on $X$. 