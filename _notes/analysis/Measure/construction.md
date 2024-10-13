---
title: "Construction of Measures"
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

## Measures

<div class='definition' name='Countably additive'>
Let $X$ be a set, and let $\AA$ be a $\sigma$-algebra on $X$. A function $\mu:\AA\to [0,+\infty]$ is said to be countably additive if it satisfies
$$
    \mu\left(\bigcup_{i=1}^\infty A_i\right)=\sum_{i=1}^\infty \mu(A_i)
$$
for each infinite sequence $\{A_i\}$ of disjoint sets that belong to $\AA$. 
</div>

<div class='definition' name='Measure'>
A measure (or countably additive measure) on $\AA$ is a function $\mu:\AA\to[0,+\infty]$ that satisfies
<ol type="a">
    <li>$\mu(\emptyset)=0$,</li>
    <li>countably additive.</li>
</ol>
</div>

The finite analogue of both definitions hold, where $\AA$ is an algebra and $\mu:\AA\to[0,+\infty]$ is finitely additive and satsfies $\mu(\emptyset)=0$. In fact, every countably additive measure is finitely additive (let $A_i=\emptyset$ if $i>n$). 

<br><br>
We are now ready to define the main objects of interest in Measure Theory. 

<div class='definition' name='Measure space'>
If $X$ is a set, $\AA$ a $\sigma$-algebra on $X$, and $\mu$ a measure on $\AA$, then the triplet $(X,\AA,\mu)$ is called a measure space. Likewise, if $X$ is a set and $\AA$ is a $\sigma$-algebra on $X$, then the pair $(X,\AA)$ is called a measurable space. If $(X,\AA,\mu)$ is a measure space, then we say $\mu$ is a measure on $(X,\AA)$. 
</div>

#### Examples

<ol>
    <li>Let $X$ be an arbitray set, and let $\AA$ be a $\sigma$-algebra on $X$. Define a function $\mu:\AA\to[0,+\infty]$ by letting $\mu(A)=n$ if $A$ is a finite set with $n$ elements and letting $\mu(A)=+\infty$ if $A$ is an infinite set. Then $\mu$ is a measure; referred to as the counting measure on $(X,\AA)$.</li>
    <li>Let $X$ be a nonempty set, and let $\AA$ be a $\sigma$-algebra on $X$. Let $x\in X$ and define a function $\delta_x:\AA\to[0,+\infty]$ by letting $\delta_x(A)=1$ if $x\in A$ and letting $\delta_x(A)=0$ if $x\notin A$. Then $\delta_x$ is a measure; referred to as a point mass or dirac measure concentrated at $x$.</li>
</ol>

<div class='proposition' name='Monotonicity of measures'>
Let $(X,\AA,\mu)$ be a measure space and let $A$ and $B$ be subsets of $X$ such that $A,B\in\AA$ and satisfy $A\subseteq B$. Then $\mu(A)\leq \mu(B)$. If in addition $A$ satisfies $\mu(A)<+\infty$, then $\mu(B-A)=\mu(B)-\mu(A)$. 
</div>

<details class='proof'>
<summary>Proof.</summary>
The sets $A$ and $B-A$ are disjoint and satisfy $B=A\cup (B-A)$; thus the additivity of $\mu$ implies that
$$
    \mu(B)=\mu(A)+\mu(B-A).
$$
Since $\mu(B-A)\geq 0$, it follows that $\mu(A)\leq \mu(B)$. If $\mu(A)<+\infty$, the relation $\mu(B-A)=\mu(B)-\mu(A)$ also follows. 
</details>