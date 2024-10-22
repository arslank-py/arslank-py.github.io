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
    <li>$\|x\|\geq0$ for all $x\in X$; $\|x\|=0$ if and only if $x=0$  (positive definiteness);</li>
    <li>$\|x+y\|\leq\|x\|+\|y\|$ for all $x,y\in X$  (triangle inequality);</li>
    <li>$\|tx\|=|t|\|x\|$ for all $t\in\F, x\in X$  (positive homogeneity). </li>
</ul>

Once it has been equipped with a norm, the pair $(X,\|\cdot\|),$ is referred to as a normed space. 
</div>

A norm always induces a metric on $X$ in a natural way; the distance $d:X\times X\to\R$ is $d(x,y)=\|x-y\|$. Thus a normed space is endowed with a metric topology, one which is compatible with the vector space operations. 

<div class='definition' name='Closed and open balls'>
The closed and open balls in $X$ are (respectively) the sets of the form
\[
B(x,r)=\{y\in X: \|y-x\|\leq r\}, \\
B^\circ(x,r)=\{y\in X: \|y-x\|< r\},
\]
with radius $r>0 $. 
</div>

A subset of $X$ is bounded if there is a ball that contains it. 

<div class='definition' name='Interior and closure of a set'>
Let $X$ be a metric space and $A\subseteq X$ a subset. The interior and closure of $A$ are (resectively) the sets
\[
\text{int}(A)=A^\circ=\{a\in A : \exists B(a,r)}\subseteq A, r>0 \}, \\
\text{cl}(A)=\bar{A}=\{x\in X : \lim_{n\to\infty} a_n=x, a_n\in A \forall n\}.
\]
Clearly, $\text{int}(A)\subseteq A\subseteq \text{cl}(A)$. 
</div>

The compatibility between the vector space and its norm topolgy manifests itself by the fact that if $U$ is an open subset of $X$, then so is its translate $x+U$ and its scalar multiple $tU$ (if $t\neq 0$). This follows from the fact that balls, which generate the underlying metric topology, cooperate well with the operations of translation and dilation:
\\[
B(x,r)=x+B(0,r), \\quad B(0,tr)=tB(0,r) \\quad (t>0). 
\\]
A useful consequence is that a sequence $x_i$ converges to a limit $x$ if and only iff the difference $x_i-x$ converges to 0. 

<br>
A vector space $X$ always admits a norm. Recall that one consequence of Zorn's lemma asserts that any vector space has a basis $\{e_\alpha\}$. That is, any $x\in X$ has a unique representation $x=\sum_{\alpha} x_\alpha e_\alpha$, where all but a finite number of the coefficients $x_\alpha$ are 0. Then $\|x\|:=\sum_\alpha |x_\alpha|$ defines a suitable norm on $X$. 

