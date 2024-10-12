---
title: "Algebras and Sigma-Algebras"
topic: "Analysis"
chapter: "Measure Theory"
section: "algebras"
layout: note
permalink: "/notes/analysis/measure/algebras/"

subtitle: 
date: 2024-10-11
keywords: analysis, measure theory
published: true
references: "Cohn, Donald. (2013). Measure theory. 2nd revised ed."
---

We state the definitions of two important collections of sets, algebras and $\sigma$-algebras, as well as their algebraic structures. 

<div class='definition' name='Algebras'>
Let $X$ be an arbitrary set. A collection $\mathscr{A}$ of subsets of $X$ is an algebra on $X$ if
<ol type="a">
    <li>$X\in\mathscr{A}$,</li>
    <li>for each set $A\in\mathscr{A}$, the set $A^c\in\mathscr{A}$,</li>
    <li>for each finite sequence $A_1,\dots,A_n\in\mathscr{A}$, the set $\bigcup_{i=1}^nA_i\in\mathscr{A}$, and</li>
    <li>for each finite sequence $A_1,\dots,A_n\in\mathscr{A}$, the set $\bigcap_{i=1}^nA_i\in\mathscr{A}$.</li>
</ol>

That is, $\mathscr{A}$ is closed under complimentation, under formation of finite unions, and under formation of finite intersections. 
</div>
