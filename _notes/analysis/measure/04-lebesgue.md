---
title: "Lebesgue Measure"
topic: "Analysis"
chapter: "Measure Theory"
section: "lebesgue"
layout: note
permalink: "/notes/analysis/measure/lebesgue/"
order: 4

subtitle: 
date: 2024-10-11
keywords: analysis, measure theory
published: true
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed."
---

## Lebesgue Outer Measure

<div class='definition' name='Lebesgue outer measure'>
Lebesgue outer measure on $\R$, which we denote $\lambda^*$, is defined as follows. For each subset $A\subset \R$, let $\CC_A$ be the set of all infinite sequences $\{(a_i,b_i)\} $ of bounded open intervals such that $A\subseteq \bigcup_{i=1}^\infty (a_i,b_i) $. Then $\lambda^*: \PP(\R)\to [0,+\infty] $  is defined by
\[
\lambda^*(A)=\inf\left\{\sum_{i=1}^\infty (b_i-a_i) : \{(a_i,b_i)\}\in\CC_A\right\}.
\] 
</div>

We now confirm that $\lambda^\*$ is in fact an outer measure. 

<div class='proposition' name='𝜆* is an outer measure'>
Lebesgue outer measure $\lambda^{*}$ on $\R$ is an outer measure, and it assigns to each subinterval of $\R$ its length. 
</div>

<details class='proof'>
<summary>Proof.</summary>
We first verify that $\lambda^*$ is an outer measure. The relation $\lambda^*(\emptyset)=0$ holds, since for each $\varepsilon>0$ there is a sequence $\{(a_i,b_i)\}$ of open intervals (whose union necessarily includes $\emptyset$) such that $\sum_{i=1}^\infty (b_i-a_i)<\varepsilon$. That is,
\[
\lambda^*(\emptyset)=\inf\left\{\sum_{i=1}^\infty (b_i-a_i) : \emptyset\subseteq\bigcup_{i=1}^\infty (a_i,b_i)\right\}=0,
\]
since any open interval trivially covers $\emptyset$ and taking the infimum of the sums of the length of all the candidate open sets is equivalent to requiring that $\sum_{i=1}^\infty (b_i-a_i)<\varepsilon$. For the monotonicity of $\lambda^*$, note that if $A\subseteq B$, then each sequence of open intervals that covers $B$ also covers $A$ and so $\lambda^*(A)\leq \lambda^*(B)$. Now consider the countable subadditivity of $\lambda^*$. Let $\{A_n\}_{n=1}^\infty$ be an arbitrary sequence of subsets of $\R$. If $\sum_{n=1}^\infty \lambda^*(A_n)=+\infty$, then $\lambda^*\left(\bigcup_{n=1}^\infty A_n\right)\leq \sum_{n=1}^\infty\lambda^*(A_n)$ certainly holds. Then suppose that $\sum_{n=1}^\infty \lambda^*(A_n)<+\infty$ and let $\varepsilon>0$. For each $n$, choose a sequence $\{(a_{n,i},b_{n,i})\}_{i=1}^\infty$ that covers $A_n$ and satisfies
\[
 \sum_{i=1}^\infty (b_{n,i}-a_{n,i})<\lambda^*(A_n)+\frac{\varepsilon}{2^n}.
\]
If we now combine these sequences into one sequence $\{(a_j,a_j)\}$, then this combined sequence satisfies
\[
\bigcup_{n=1}^\infty A_n\subseteq \bigcup_{j=1}^\infty (a_j,b_j)
\]
and
\[
\sum_{j=1}^\infty (b_j-a_j)<\sum_{n=1}^\infty \left(\lambda^*(A_n)+\frac{\varepsilon}{2^n}\right)=\sum_{n=1}^\infty \lambda^*(A_n)+\varepsilon. 
\]
These relations, together with the fact that $\varepsilon$ is arbitrary, imply that $\lambda^*(\bigcup_{n=1}^\infty A_n)\leq \sum_{n=1}^\infty\lambda^*(A_n)$. Thus $\lambda^*$ is an outer measure. 

<br><br>
We now compute the outer measure of the subintervals of $\R$. First consider the closed bounded interval $[a,b]$. It is easy to see that $\lambda^*([a,b])\leq b-a$ (cover $[a,b]$ with sequences of open intervals in which the first interval is barely larger than $[a,b]$ and the sum of the lengths of the other intervals is very small). For the reverse inequality, let $\{(a_i,b_i)\}$ be a sequence of bounded open intervals whose union includes $[a,b]$. Since $[a,b]$ is compact, there exists $n\in\N$ such that $[a,b]\subseteq \bigcup_{i=1}^n(a_i,b_i)$. It is easy to check that $b-a\leq \sum_{i=1}^\infty (b_i-a_i)$. Since $\{(a_i,b_i)\}$ was arbitrary, it follows that $b-a\leq \lambda^*([a,b]) and hence $\lambda^*([a,b])=b-a$. 
</details>

Lebesgue outer measure on $\R^d$, which we denote $\lambda_d^*$, is defined similarly. A $d$-dimensional interval is a subset of $\R^d$ of the form $I_1\times \cdots\times I_d$, where $I_1,\cdots,I_d$ are subintervals of $\R$ and $I_1\times \cdots\times I_d$ is given by
\\[
    I_1\times \cdots\times I_d=\{(x_1,\dots,x_d) : x_i\in I_i \text{ for }i=1,\dots,d\}.
\\]
The volume of the $d$-dimensional interval $\text{vol}(I_1\times\cdots\times I_d)$ is the product of the lengths of the intervals $I_1,\cdots,I_d$. For each subset $A\subseteq \R^d$, let $\CC_A$ be the set of all sequences $\\{R_i\\}$ of bounded and open $d$-dimensional intervals for which $A\subseteq \bigcup_{i=1}^\infty R_i$. Then $\lambda^\*(A)$ is defined as
\\[
    \lambda^\*(A)=\inf\left\\{\sum_{i=1}^\infty \text{vol}(R_i) : \\{R_i\\}\in\CC_A \right\\}.
\\]
Just as in the case of $d=1$, $\lambda_d^\*$ is an outer measure and it assigns to each $d$-dimensional intervals its volume. 