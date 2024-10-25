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

<ol>
    <li>Let $X$ be an arbitray set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(A)=0$ if $A$ is countable, and $\mu^*(A)=1$ if $A$ is uncountable. Then $\mu^*$ is an outer measure.
    </li>
    <li>Let $X$ be an infinite set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(A)=0$ if $A$ is finite, and $\mu^*(A)=1$ if $A$ is infinite. Then $\mu^*$ fails to be countably subadditive and so not an outer measure.</li>
</ol>

To define an outer measure, we often construct the outer measure on some "nice" sets (like rectangles or balls), followed by approximating arbitrary sets in our space from above using countable unions of these nice sets. That is, an outer measure of an arbirary set can be obtained by taking the smallest measure of the nice sets that cover it. We now make this intuition precise with the following proposition. 

<div class='proposition' name='Constructing an outer measure'>
Let $X$ be a set and suppose $\FF\subseteq \PP(X)$ is an arbitrary collection of subsets such that $ \emptyset,X\in\FF$. Let $\rho:\FF\to[0,+\infty]$ be such that $\rho(\emptyset)=0$. Then $\mu^*:\PP(X)\to[0,+\infty]$ for all $E\subseteq X$ is defined as
\[
    \mu^*(A)=\inf\left\{\sum_{i=1}^\infty \rho(F_i) : F_i\in\FF, \text{ }E\subseteq\bigcup_{i=1}^\infty F_i\right\}.
\]
Then $\mu^*$ is an outer measure on $X$. 
</div>
