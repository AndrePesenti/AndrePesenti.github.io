---
title: "Integrali Indefiniti"
description: ""
date: 2026-09-15
draft: false
weight: 6
showTableOfContents: true
layout: scroll
math: true
---

>**DEFINIZIONE:** data una funzione \(f(x)\) definita in un intervallo \(I \subseteq \mathbb{R}\), si dice "primitiva di \(f(x)\)" una funzione \(F(x)\) che:
>1. \(F(x)\) deve essere derivabile.
>2. \(F'(x) = f(x) \quad \forall x \in I\)



### Esempio

\(f(x) = 2x \quad D: \mathbb{R}\)

\(F(x) = x^2 \quad D[x^2]=2x\)

\(F(x) = x^2+3 \quad D[x^2+3]=2x\)

Una volta che una funzione \(f(x)\) ha una primitiva allora ne ha infinite.
<br>\(f(x)=2x \quad F(x)=x^2+c \quad c \in \mathbb{R}\)

\(F(x)\) primitiva di \(f(x)\) se \(F'(x) = f(x)\)
<br>\(G(x)\) primitiva di \(f(x)\) se \(G'(x) = f(x)\)

\(D[F(x)-G(x)] = D[F(x)]-D[G(x)] = f(x) - f(x) = 0\)
<br>\(F(x)-G(x) = c\) (costante)
<br>\(F(x)=G(x)+c\)

>Data una funzione \(f(x)\) avente come primitiva \(F(x)\), allora **tutte e sole** le primitive di \(f(x)\) sono le funzioni \(F(x)+c\) con \(c \in \mathbb{R}\).

>L'insieme delle infinite primitive di \(f(x)\) si chiama **INTEGRALE INDEFINITO** di \(f(x)\).



$$\int f(x) dx = F(x) + c, \quad c \in \mathbb{R}$$

In cui \(f(x)\) è la *funzione integranda*, \(dx\) il *differenziale* e \(c\) la *costante*

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/contrib/auto-render.min.js" onload="renderMathInElement(document.body);"></script>

**CURVE INTEGRALI:** sono i grafici delle funzioni primitive.