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
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed."
---

## Outer Measures

We develop one of the standard techniques for constructing measures. 

<div class='definition' name='Outer measure'>
Let $X$ be a set, and let $\mathscr{P}(X)$ be the collection of all subsets of $X$. An outer measure on $X$ is a function $\mu^*:\mathscr{P}(X)\to[0,+\infty] $ such that
<ol type="a">
    <li>$\mu^*(\emptyset)=0$,</li>
    <li>if $A\subseteq B\subseteq X$, then $\mu^*(A)\leq \mu^*(B)$, and</li>
    <li>if $\{A_n\}$ is an infinte sequence of subsets of $X$, then
    \[
        \mu^*\left(\bigcup_{n=1}^\infty A_n\right)\leq\sum_{n=1}^\infty \mu^*(A_n).
    \] 
    </li>
</ol>
</div>

Thus an outer measure on $X$ is a monotone and countably subadditive function from $\mathscr{P}(X)$ to $[0,+\infty]$ whose value at $\emptyset$ is 0. Many important measure can be derived from outer measures by restricting $\mu^*$ to a special $\sigma$-algebra which we discuss later. 

#### Examples:

Let $X$ be an arbitray set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(A)=0$ if $A$ is countable, and $\mu^*(A)=1$ if $A$ is uncountable. Then $\mu^*$ is an outer measure.

<br><br>
Lebesgue outer measure on $\R$, which we denote $\lambda^*$, is defined as follows. For each subset $A\subset \R$, let $\CC_A$ be the set of all infinite sequences $\{(a_i,b_i)\}$ of bounded open intervals such that $A\subseteq \bigcup_{i=1}^\infty (a_i,b_i)$. Then $\lambda^*: \PP(\R)\to[0,+\infty]$ is defined by
\[
    \lambda^*(A)=\inf\left\{\sum_{i=1}^\infty (b_i-a_i) : \{(a_i,b_i)\}\in\CC_A\right\}.
\] 

We now confirm that $\lambda^*$ is in fact an outer measure. 

<div class='proposition' name='𝜆* is an outer measure'>
Lebesgue outer measure $\lambda^*$ on $\R$ is an outer measure, and it assigns to each subinterval of $\R$ its length. 
</div>

<details class='proof'>
<summary>Proof.</summary>
We first verify that $\lambda^*$ is an outer measure. The relation $\lambda^*(\emptyset)=0$ holds, since for each $\varepsilon>0$ there is a sequence $\{(a_i,b_i)\}$ of open intervals (whose union necessarily includes $\emptyset$) such that $\sum_{i=1}^\infty (b_i-a_i)<\varepsilon$. That is,
\[
\lambda^*(\emptyset)=\inf\left\{\sum_{i=1}^\infty (b_i-a_i) : \emptyset\subseteq\bigcup_{i=1}^\infty (a_i,b_i)\right\}=0,
\]
since any open interval trivially covers $\emptyset$ and taking the infimum of the sums of the length of all the candidate open sets is equivalent to requiring that $\sum_{i=1}^\infty (b_i-a_i)<\varepsilon$. For the monotonicity of $\lambda^*$, note that if $A\subseteq B$, then each sequence of open intervals that covers $B$ also covers $A$ and so $\lambda^*(A)\leq \lambda^*(B)$. Now consider the countable subadditivity of $\lambda^*$. Let $\{A_n\}_{n=1}^\infty$ be an arbitrary sequence of subsets of $\R$. If $\sum_{n=1}^\infty \lambda^*(A_n)=+\infty$, then $\lambda^*\left(\bigcup_{n=1}^\infty A_n\right)\leq \sum_{n=1}^\infty\lambda^*(A_n)$ certainly holds. So suppose that $\sum_{n=1}^\infty \lambda^*(A_n)<+\infty$ and let $\varepsilon>0$. For each $n$ choose a sequence $\{(a_{n,i},b_{n,i})\}_{i=1}^\infty$ that covers $A_n$ and satisfies
\[
 \sum_{i=1}^\infty (b_{n,i}-a_{n,i})<\lambda^*(A_n)+\frac{\varepsilon}{2^n}.
\]
If we now combine these sequences into one sequence $\{(a_i,a_j)\}$, then this combined sequence satisfies
\[
\bigcup_{n=1}^\infty A_n\subseteq \bigcup_{j=1}^\infty (a_j,b_j)
\]
and
\[
\sum_{j=1}^\infty (b_j-a_j)<\sum_{n=1}^\infty \left(\lambda^*(A_n)+\frac{\varepsilon}{2^n}\right)=\sum_{n=1}^\infty \lambda^*(A_n)+\varepsilon. 
\]
</details>

