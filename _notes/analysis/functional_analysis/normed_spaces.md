---
title: "Normed Spaces: Basic Definitions"
topic: "Analysis"
chapter: "Functional Analysis"
section: "normed_spaces"
layout: note
permalink: "/notes/analysis/functional_analysis/normed_spaces/"

subtitle: 
date: 2024-10-17
keywords: analysis, functional analysis
published: true
references: "Clarke, Francis. (2013). Functional Analysis, Calculus of Variations and Optimal Control."
---

## Basic Definitions

<div class='definition' name='Normed Space'>
Given a vector space $X$ over a field $\F$, a norm on $X$ is a real-valued function $\|x\|:X\to\R$ satisfying the following properties:
<ul>
    <li>$\|x\|\geq0$ for all $x\in X$; $\|x\|=0$ if and only if $x=0$ (positive definiteness);</li>
    <li>$\|x+y\|\leq\|x\|+\|y\|$ for all $x,y\in X$ (triangle inequality);</li>
    <li>$\|tx\|=|t|\|x\|$ for all $t\in\F, x\in X$ (positive homogeneity). </li>
</ul>

Once it has been equipped with a norm, the pair $(X,\|\cdot\|),$ is referred to as a normed space. 
</div>

A norm always induces a metric on $X$ in a natural way; the distance $d:X\times X\to\R$ is $d(x,y)=\|x-y\|$. Thus a normed space is endowed with a metric topology, one which is compatible with the vector space operations. 

<div class='definition' name='Closed and open balls'>
The closed and open balls in $X$ are (respectively) the sets of the form
\[
B(x,r)=\{y\in X: \|y-x\|\leq r\}, \\
B^circ(x,r)=\{y\in X: \|y-x\|<> r\},
\]
where the radius $r>0$. 
</div>

A subset of $X$ is bounded if there is a ball that contains it. 