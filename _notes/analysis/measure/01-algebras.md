---
title: "Algebras, σ-Algebras, and the Borel σ-Algebra"
topic: "Analysis"
chapter: "Measure Theory"
section: "algebras"
layout: note
permalink: "/notes/analysis/measure/algebras/"
order: 1

subtitle: 
date: 2024-10-11
keywords: analysis, measure theory
published: true
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed."
---

## Algebras and $\sigma$-Algebras

We first state the definitions of two important collections of sets, algebras and $\sigma$-algebras, as well as their algebraic structures. These are the objects whose sizes we measure.

<div class='definition' name='Algebras'>
Let $X$ be an arbitrary set. A collection $\mathscr{A}$ of subsets of $X$ is an algebra on $X$ if
<ol type="a">
    <li>$X\in\mathscr{A}$,</li>
    <li>for each set $A\in\mathscr{A}$, the set $A^c\in\mathscr{A}$,</li>
    <li>for each finite sequence $A_1,\dots,A_n\in\mathscr{A}$, the set $\bigcup_{i=1}^nA_i\in\mathscr{A}$, and</li>
    <li>for each finite sequence $A_1,\dots,A_n\in\mathscr{A}$, the set $\bigcap_{i=1}^nA_i\in\mathscr{A}$.</li>
</ol>
</div>

That is, $\mathscr{A}$ is closed under complimentation, under formation of finite unions, and under formation of finite intersections. A nice-to-have direct implication is that $\AA$ is also closed under set differences since for $A,B\in\AA$, we have that $A-B=A\cap B^c\in\AA$. This holds for the following collection ($\sigma$-algebras) as well. 

<div class='definition' name='σ-Algebras'>
Let $X$ be an arbitrary set. A collection $\mathscr{A}$ of subsets of $X$ is a $\sigma$-algebra on $X$ if
<ol type="a">
    <li>$X\in\mathscr{A}$,</li>
    <li>for each set $A\in\mathscr{A}$, the set $A^c\in\mathscr{A}$,</li>
    <li>for each infinite sequence $\{A_i\}\in\mathscr{A}$, the set $\bigcup_{i=1}^\infty A_i\in\mathscr{A}$, and</li>
    <li>for each infinite sequence $\{A_i\}\in\mathscr{A}$, the set $\bigcap_{i=1}^\infty A_i\in\mathscr{A}$.</li>
</ol>
</div>

Thus, $\mathscr{A}$ is closed under complimentation, under formation of countable unions, and under formation of countable intersections. If $\mathscr{A}$ is a $\sigma$-algebra on the set $X$, it is convenient to call a subset $A\subseteq X$ $\mathscr{A}$-measurable if $A\in\mathscr{A}$. 

<div class='proposition' name='Intersection of a collection of σ-algebras'>
Let $X$ be a set. Then the intersection of an arbitrary nonempty collection of $\sigma$-algebras on $X$ is a $\sigma$-algebra on $X$. 
</div>

<details class='proof'>
<summary>Proof.</summary>
Let $\mathscr{C}$ be a nonempty collection of $\sigma$-algebras on $X$, and let $\mathscr{A}$ be the intersection of the $\sigma$-algebras that belong to $\mathscr{C}$. It is sufficient to check that $X\in\mathscr{A}$, is closed under complimentation, and closed under the formation of countable unions. 

<br><br>
The set $X\in\mathscr{A}$ since it belongs to each $\sigma$-algebra that belongs to $\mathscr{C}$. Now suppose that $A\in\mathscr{A}$. Then each $\sigma$-algebra that belongs to $\mathscr{C}$ also contains $A$ and so contains $A^c$; thus $A^c$ belongs to the intersection $\mathscr{A}$ of these $\sigma$-algebras. Finally, suppose that $\{A_i\}\in\mathscr{A}$ and hence to each $\sigma$-algebra in $\mathscr{C}$. Then $\bigcup_i A_i$ belongs to each $\sigma$-algebra in $\mathscr{C}$ and so to $\mathscr{A}$.
</details>

To say $\mathscr{A}$ is the smallest $\sigma$-algebra on $X$ that includes $\mathscr{F}$ is to say that $\mathscr{A}$ is a $\sigma$-algebra on $X$ that includes $\mathscr{F}$ and that every $\sigma$-algebra on $X$ that includes $\FF$ also includes $\mathscr{A}$. If $\mathscr{A}_1$ and $\mathscr{A}_2$ are both the smallest $\sigma$-algebras on $X$ that includes $\mathscr{F}$, then $\mathscr{A}_1\subseteq\mathscr{A}_2$ and $\AA_2\subseteq \AA_1$, so $\AA_1=\AA_2$; thus the smallest $\sigma$-algebra on $X$ that includes $\FF$ is unique. 

<div class='corollary' name='σ-algebra generated by ℱ '>
Let $X$ be a set, and let $\mathscr{F}$ be a family of subsets of $X$. Then there is a smallest $\sigma$-algebra on $X$ that includes $\mathscr{F}$. 

<br><br>
The smalleset $\sigma$-algebra is called the $\sigma$-algebra generated by $\FF$ and is denoted $\sigma(\FF)$. 
</div>

<details class='proof'>
<summary>Proof.</summary>
Let $\CC$ be the collection of all $\sigma$-algebras on $X$ that includes $\FF$. Then $\CC$ is nonempty, since it contains the $\sigma$-algebra that consists of all subsets of $X$. The intersection of the $\sigma$-algebras that belong to $\CC$ is, according to Proposition (1), a $\sigma$-algebra; it includes $\FF$ and is included in every $\sigma$-algebra in $\CC$ -- that is, it is included in every $\sigma$-algebra on $X$ that includes $\FF$. 
</details>

We use this preceding corollary to define an important (arguably the most important) family of $\sigma$-algebras. 

## Borel $\sigma$-algebra, $\BB(\R^d)$

<div class='definition' name='The Borel σ-algebra on ℝᵈ'>
The Borel $\sigma$-algebra on $\R^d$ is the $\sigma$-algebra on $\R^d$ generated by the collection of open subsets of $\R^d$; denoted $\BB(\R^d)$. The Borel subsets of $\R^d$ are those sets that belong to $\BB(\R^d)$. For $d=1$, we write $\BB(\R)$. 
</div>

It is important to note the following attractive properties of $\BB(\R)$ :
<ul>
    <li>it contains virtually every subset of $\R$ that is of interest in analysis;</li>
    <li>it is small enough that it can be dealt with in a fairly constructive manner.</li>
</ul>

<div class='proposition' name='Generating ℬ(ℝ)'>
The $\sigma$-algebra $\BB(\R)$ of Borel subsets of $\R$ is generated by each of the following collections of sets:
<ol type='a'>
    <li>the collection of all closed subsets of $\R$;</li>
    <li>the collection of all subintervals of $\R$ of the form $(-\infty,b]$;</li>
    <li>the collection of all subintervals of $\R$ of the form $(a,b]$.</li>
</ol>
</div>

<details class='proof'>
<summary>Proof.</summary>
Let $\BB_1$, $\BB_2$, and $\BB_3$ be the $\sigma$-algebras generated by the collections of sets in parts (a), (b), and (c) of the proposition. We will show that $\BB(\R)\supseteq\BB_1\supseteq\BB_2\supseteq\BB_3$ and finally $\BB_3\supseteq\BB(\R)$, establishing our proposition. 

<br><br>
Since $\BB(\R)$ includes the family of open subsets of $\R$ and is closed under complimentation, it includes the family of closed subsets of $\R$; hence it includes the $\sigma$-algebra generated by the closed subsets of $\R$, i.e., $\BB_1$. The sets of the form $(-\infty,b]$ are closed and so belong to $\BB_1$; consequently $\BB_1\supseteq\BB_2$. Since $(a,b]=(-\infty,b]\cap(-\infty,a]^c$, each set of the form $(a,b]$ belongs to $\BB_2$; thus $\BB_2\supseteq\BB_3$. Finally, note that each open subinterval of $\R$ is the union of a sequnce of sets of the form $(a,b]$ and that each open subset of $\R$ is the union of a sequence of open intervals. Thus each open subset of $\R$ belongs to $\BB_3$ and we have $\BB_3\supseteq\BB(\R)$ .  
</details>

A similar result holds for the $\sigma$-algebra $\BB(\R^d)$ of Borel subsets of $\R^d$, where instead of subsets of $\R$ being intervals, we deal with vector subspaces of $\R^d$. The proof is essentially the same. 