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
<ol>
    <li>$\|x\|\geq0$ $\forall x\in X$; $\|x\|=0$ if and only if $x=0$ (positive definiteness);</li>
    <li>$\|x+y\|\leq\|x\|+\|y\|$ $\forall x,y\in X$ (triangle inequality);/li>
    <li>$\|tx\|=|t|\|x\|$ $\forall t\in\F,x\in X$ (positive homogeneity). </li>
</ol>
</div>