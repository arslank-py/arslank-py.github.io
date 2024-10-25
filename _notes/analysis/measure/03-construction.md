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
Let $X$ be a set, and let $\mathscr{P}(X)=2^X$ be the collection of all subsets of $X$. An outer measure on $X$ is a function $\mu^*:\mathscr{P}(X)\to[0,+\infty] $ such that
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

Let $X$ be an arbitray set, and define $\mu^\*$ on $\PP(X)$ by $\mu^\*(A)=0$ if $A$ is countable, and $\mu^\*(A)=1$ if $A$ is uncountable. Then $\mu^\*$ is an outer measure.


Lebesgue outer measure on $\R^d$, which we denote $\lambda_d^*$, is defined as follows. A $d$-dimensional interval is a subset of $\R^d$ of the form $I_1\times \cdots\times I_d$, where $I_1,\cdots,I_d$ are subintervals of $\R$ and $I_1\times \cdots\times I_d$ is given by
\\[
    I_1\times \cdots\times I_d=\{(x_1,\dots,x_d) : x_i\in I_i \text{ for }i=1,\dots,d\}.
\\]
The volume of the $d$-dimensional interval $\text{vol}(I_1\times\cdots\times I_d)$ is the product of the lengths of the intervals $I_1,\cdots,I_d$