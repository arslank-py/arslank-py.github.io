---
title: "Construction of Measures and Outer Measures"
topic: "Analysis"
chapter: "Measure Theory"
section: "construction"
layout: note
permalink: "/notes/analysis/measure/construction/"

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
    <li>$\mu^*(\empty)=0$,</li>
    <li>if $A\subseteq B\subseteq X$, then $\mu^*(A)\leq \mu^*(B)$, and</li>
    <li>if $\{A_n\}$ is an infinte sequence of subsets of $X$, then
    \[
        \mu^*\left(\bigcup_{n=1}^\infty A_n\right)=\sum_{n=1}^\infty \mu^*(A_n).
    \] 
    </li>
</ol>

Thus an outer measure on $X$ is a monotone and countably subadditive function from $\mathscr{P}(X)$ to $[0,+\infty]$ whose value at $\empty$ is 0. Many important measure can be derived from outer measures by restricting $\mu^*$ to a special $\sigma$-algebra $\MM_{\mu^*}$, which we discuss later. 

#### Examples:

<ol>
    <li>Let $X$ be an arbitray set, and define $\mu^*$ on $\PP(X)$ by $\mu^*(A)=0$ if $A$ is countable, and $\mu^*(A)=1$ if $A$ is uncountable. Then $\mu^*$ is an outer measure.</li>
    <li>Lebesgue outer measure on $\R$, which we denote $\lambda^*$, is defined as follows. For each subset $A\subset \R$, let $\CC_A$ be the set of all infinite sequences $\{(a_i,b_i)\}$ of bounded open intervals such that $A\subseteq \bigcup_{i=1}^\infty (a_i,b_i)$. Then $\lambda^*: \PP(\R)\to[0,+\infty]$ is defined by
    \[
        \lambda^*(A)=\inf\left\{\sum_{i=1}^\infty (b_i-a_i) : \{(a_i,b_i)\}\in\CC_A\right\}.
    \] 
    </li>
</ol>