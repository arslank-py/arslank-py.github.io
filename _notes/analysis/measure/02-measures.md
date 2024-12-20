---
title: "Measures and some Properties"
topic: "Analysis"
chapter: "Measure Theory"
section: "measures"
layout: note
permalink: "/notes/analysis/measure/measures/"
order: 2

subtitle: 
date: 2024-10-12
keywords: analysis, measure theory
published: true
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed."
---

## Measures

<div class='definition' name='Countably additive'>
Let $X$ be a set, and let $\AA$ be a $\sigma$-algebra on $X$. A function $\mu:\AA\to [0,+\infty] $ is said to be countably additive if it satisfies
\[
\mu\left(\bigcup_{i=1}^\infty A_i\right)=\sum_{i=1}^\infty \mu(A_i),
\]
for each infinite sequence $\{A_i\}$ of disjoint sets that belong to $\AA$. 
</div>

<div class='definition' name='Measure'>
A measure (or countably additive measure) on $\AA$ is a function $\mu:\AA\to[0,+\infty] $ that satisfies
<ol type="a">
    <li>$\mu(\emptyset)=0$ ,</li>
    <li>countably additive.</li>
</ol>
</div>

The finite analogue of both definitions hold, where $\AA$ is an algebra and $\mu:\AA\to[0,+\infty]$ is finitely additive and satsfies $\mu(\emptyset)=0$ . In fact, every countably additive measure is finitely additive (let $A_i=\emptyset $ for $ i>n$). 

We are now ready to define one of the primary building blocks in Measure Theory.

<div class='definition' name='Measure space'>
If $X$ is a set, $\AA$ a $\sigma$-algebra on $X$, and $\mu$ a measure on $\AA$, then the triplet $(X,\AA,\mu) $ is called a measure space. Likewise, if $X$ is a set and $\AA$ is a $\sigma$-algebra on $X$, then the pair $(X,\AA) $ is called a measurable space. If $(X,\AA,\mu) $ is a measure space, then we say $\mu$ is a measure on $(X,\AA) $. 
</div>

#### Examples:

<ol>
    <li>Let $X$ be an arbitray set, and let $\AA$ be a $\sigma$-algebra on $X$. Define a function $\mu:\AA\to[0,+\infty]$ by letting $\mu(A)=n $ if $A$ is a finite set with $n$ elements and letting $\mu(A)=+\infty $ if $A$ is an infinite set. Then $\mu$ is a measure; referred to as the counting measure on $(X,\AA)$ .</li>
    <li>Let $X$ be a nonempty set, and let $\AA$ be a $\sigma$-algebra on $X$. Let $x\in X$ and define a function $\delta_x:\AA\to[0,+\infty] $ by letting $\delta_x(A)=1 $ if $x\in A $ and $\delta_x(A)=0 $ if $x\notin A$ . Then $\delta_x$ is a measure; referred to as a point mass or dirac measure concentrated at $x$.</li>
</ol>

<div class='proposition' name='Monotonicity of measures'>
Let $(X,\AA,\mu) $ be a measure space and let $A$ and $B$ be subsets of $X$ such that $A,B\in\AA$ and satisfy $A\subseteq B$. Then $\mu(A)\leq \mu(B)$ . If in addition $A$ satisfies $\mu(A)<+\infty$ , then $\mu(B-A)=\mu(B)-\mu(A)$ . 
</div>

<details class='proof'>
<summary>Proof.</summary>
The sets $A$ and $B-A$ are disjoint and satisfy $B=A\cup (B-A)$ ; thus the additivity of $\mu$ implies that
\[
\mu(B)=\mu(A)+\mu(B-A).
\]
Since $\mu(B-A)\geq 0$ , it follows that $\mu(A)\leq \mu(B)$ . If $\mu(A)<+\infty$ , the relation $\mu(B-A)=\mu(B)-\mu(A) $ also follows. 
</details>

We now provide two ways of characterizing measures and their respective spaces by how the handle the "total" measure of the space $X$. 

<div class='definition' name='Finite measure'>
Let $\mu$ be a measure on a measurable space $(X,\AA)$. Then $\mu$ is finite if it satisfies $\mu(X)<+\infty$ . By the monotonicity of measures, this implies
\[
\mu(A)<+\infty \quad\text{for all}\quad A\in\AA.
\]
</div>

Finite measure possess a number of attractive properties that allow their handling to be much easier to work with than more general measures. The most familiar family of finite measures are probability measures. 

<div class='definition' name='σ-Finite measure'>
Let $\mu$ be a measure on a measurable space $(X,\AA)$. The measure $\mu$ is called $\sigma$-finite if the set $X$ can be covered with at most countably many measurable sets with finite measure. That is, there exists $\{A_i\}\in\AA$ such that $\mu(A_i)<+\infty $  and
\[
X=\bigcup_{i=1}^\infty A_i \quad\text{for all}\quad i\in\N.   
\]

More generally, a set $A\in\AA$ is $\sigma$-finite under $\mu$ if it is the countable union of a sequence of sets that belong to $\AA$ and have finite measure under $\mu$. 
</div>

#### Example: 

Consider $(\R,\BB(\R),\lambda) $, where $\BB(\R)$ is the Borel $\sigma$-algebra on $\R$ and $\lambda$ is the Lebesgue measure: $\lambda([a,b])=b-a$. 

$(\R,\BB(\R),\lambda) $ is $\sigma$-finite: Clearly, $\lambda(\R)=+\infty$. $\R$ can be expressed as the countable union of sets with finite measure. Let
\\[
\R=\bigcup_{n=1}^\infty I_n, \quad\text{where}\quad I_n=[-n,n].
\\]
Since $n$ is a finite real number and for each interval $I_n\in\BB(\R)$ we have that
\\[
\lambda(I_n)=\lambda([-n,n])=2n<+\infty,
\\]
$(\R,\BB(\R),\lambda) $ is $\sigma$-finite. 

$\sigma$-finite measures generalize finite measures and allows for spaces with potentially infinite measure to be decomposed into countably many subsets with finite measure. This allows the application of techniques of finite-measure to be extended to infinite-measure problems. 

**Note:** If the measure space $(X,\AA,\mu) $  is $\sigma$-finite, then $X$ is the union of a sequence $\lbrace B_i\rbrace$ of disjoint sets that belong to $\AA$ and have finite measure under $\mu$; such a sequence $\lbrace B_i\rbrace$ can be formed by choosing a sequence $\lbrace A_i\rbrace$ as in the definition of $\sigma$-finiteness, and then letting
\\[
B_1=A_1, \quad\text{and}\quad B_i=A_i-\left(\bigcup_{j=1}^{i-1} A_j\right) \quad\text{if}\quad i>1. 
\\] 

The measure space $(X,\AA,\mu) $  is also called finite or $\sigma$-finite if $\mu$ is finite or $\sigma$-finite.

<div class='proposition' name='Countable subadditivity of μ'>
Let $(X,\AA,\mu) $ be a measure space. If $\{A_k\}$ is an arbitrary sequence of sets that belong to $\AA$, then 
\[
\mu\left(\bigcup_{k=1}^\infty A_k\right)\leq \sum_{k=1}^\infty \mu(A_k).
\]
</div>

<details class='proof'>
<summary>Proof.</summary>
 Define a sequence $\{B_k\}$ of subsets of $X$ by letting $B_1=A_1$ and letting $B_k=A_k-\left(\bigcup_{i=1}^{k-1} A_i\right)$ if $k>1$. Then each set $B_k$ belongs to $\AA$ and is a subset of the corresponding $A_k$, thus satisfying $\mu(B_k)\leq \mu(A_k)$. Since in addition the sets $B_k$ are disjoint and satisfy $\bigcup_{k=1}^\infty B_k=\bigcup_{k=1}^\infty A_k$, it follows that 
 \[
\mu\left(\bigcup_{k=1}^\infty A_k\right)=\mu\left(\bigcup_{k=1}^\infty B_k\right) = \sum_{k=1}^\infty \mu(B_k)\leq \sum_{k=1}^\infty \mu(A_k). 
 \]
</details>

That is, the countable additivity of $\mu$ implies the countably subadditivity of $\mu$. The following proposition will prove to be a very useful tool in the future. 

<div class='proposition' name='Continuity of measure'>
<ol>
    <li>If $\{A_k\}$ is an increasing sequence of sets that belong to $\AA$, then 
    \[
    \mu\left(\bigcup_{k=1}^\infty A_k\right)=\lim_{k\to\infty}\mu(A_k).
    \]</li>
    <li>If $\{A_k\}$ is an increasing sequence of sets that belong to $\AA$ and $\mu(A_n)<+\infty$ holds for some $n$, then 
    \[
        \mu\left(\bigcap_{k=1}^\infty A_k\right)=\lim_{k\to\infty}\mu(A_k).
    \]</li>
</ol>
</div>

<details class='proof'>
<summary>Proof.</summary>
First suppose that $\{A_k\}$ is an increasing sequence of sets that belong to $\AA$, and define a sequence $\{B_i\}$ of sets by letting $B_1=A_1$ and letting $B_i=A_i-A_{i-1}$ if $i>1$. The sets just constructed are disjoint, belong to $\AA$, and satisfy $A_k=\bigcup_{i=1}^k B_i$ for each $k$. It follows that $\bigcup_{k=1}^\infty A_k=\bigcup_{i=1}^\infty B_i$ and hence that
\[
\mu\left(\bigcup_{k=1}^\infty A_k\right)=\sum_{i=1}^\infty \mu(B_i)=\lim_{k\to\infty}\sum_{i=1}^k \mu(B_i)=\lim_{k\to\infty}\mu\left(\bigcup_{i=1}^k B_i\right)=\lim_{k\to\infty}\mu(A_k). 
\]
This completes the proof of (a). 

<br><br>
Now suppose that $\{A_k\}$ is a decreasing sequence of sets that belong to $\AA$ and that $\mu(A_n)<+\infty$ holds for some $n$. We can assume $n=1$. For each $k$ let $C_k=A_1-A_k$. Then $\{C_k\}$ is an increasing sequence of sets that belong to $\AA$ and satisfy
\[
\bigcup_{k=1}^\infty C_k=A_1-\left(\bigcap_{k=1}^\infty A_k\right).    
\]
It follows from part (a) that $\mu\left(\bigcup_{k=1}^\infty C_k\right)=\lim_{k\to\infty}\mu(C_k)$ and hence that
\[
\mu\left(A_1-\left(\bigcap_{k=1}^\infty A_k\right)\right)=\mu\left(\bigcup_{k=1}^\infty C_k\right)=\lim_{k\to\infty}\mu(C_k)=\lim_{k\to\infty}\mu(A_1-A_k).
\]
By Proposition 1 (monotonicity of measures) and the assumption that $\mu(A_1)<+\infty$, this implies that $\mu\left(\bigcap_{k=1}^\infty A_k\right)=\lim_{k\to\infty}\mu(A_k)$. 
</details>

It is easy to see that this property acts as a sort of measure-analogue to the known result that the limit of a montone sequence of sets $\{E_k\}$ is either its countable union or countable intersection. We now finish off with a few more helpful definitions. 

<div class='definition' name='Borel measure on ℝᵈ'>
A measure on $(\R^d,\BB(\R^d)) $ is called a Borel measure on $\R^d$. More generally, if $X$ is a Borel subset of $\R^d$ and if $\AA$ is the $\sigma$-algebra consisting of those Borel subsets of $\R^d$ included in $X$, then a measure on $(X,\AA) $ is called a Borel measure on $X$. 
</div>

<div class='definition' name='Continuous and discrete measures'>
Suppose $(X,\AA) $ is a measurable space such that for every $x\in X$ the set $\{x\}$ belongs to $\AA$. A finite or $\sigma$-finite measure $\mu$ on $(X,\AA) $ is continuous if $\mu(\{x\})=0$ holds for all $x\in X$ and is discrete if there is a countable subset $D\subseteq X$ such that $\mu(D^c)=0$.  
</div>

The distinction between the two types of measure is a classic characterization; the latter deals with countable sets, while the former deals with uncountable sets. 