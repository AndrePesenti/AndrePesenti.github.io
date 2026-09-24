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
## PRIMITIVA
>**DEFINIZIONE:** data una funzione \(f(x)\) definita in un intervallo \(I \subseteq \mathbb{R}\), si dice "primitiva di \(f(x)\)" una funzione \(F(x)\) che:
>1. \(F(x)\) deve essere derivabile.
>2. \(F'(x) = f(x) \quad \forall x \in I\)



**Esempio**

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

## TEOREMA DI LAGRANGE
>Data una funzione \(f(x)\) avente come primitiva \(F(x)\), allora **tutte e sole** le primitive di \(f(x)\) sono le funzioni \(F(x)+c\) con \(c \in \mathbb{R}\).

>L'insieme delle infinite primitive di \(f(x)\) si chiama **INTEGRALE INDEFINITO** di \(f(x)\).



$$\int f(x) dx = F(x) + c, \quad c \in \mathbb{R}$$

In cui \(f(x)\) è la *funzione integranda*, \(dx\) il *differenziale* e \(c\) la *costante*

**CURVE INTEGRALI:** sono i grafici delle funzioni primitive.

>**DEFINIZIONE:** una funzione si dice integrabile se ammette primitiva.

>**TEOREMA:** se una funzione \(f(x)\) è derivabile in \(x_0\) allora \(f(x)\) è continua in \(x_0\)

> **CONDIZIONE SUFFICIENTE DI INTEGRABILITA':** è una condizione che se verificata la funzione è sicuramente integrabile. Tale condizione dice che una funzione è integrabile se è continua nell'intervallo *I*.

## INTEGRALI INDEFINITI IMMEDIATI
### Integrale di una potenza
\[\int x^\alpha \, dx = \frac{x^{\alpha+1}}{\alpha+1} + C, \quad C \in \mathbb{R}\]

Questa formula vale soltanto quando *α ≠* -1 perchè altrimenti avrei *0* al denominatore.


### Integrale di \(\frac{1}{x}\)
$$\int \frac{1}{x} \, dx = \ln|x| + C \quad C \in \mathbb{R}$$

### Integrale di \(e^x\)
$$\int e^x \, dx = e^x + C \quad C \in \mathbb{R}$$

### Integrale di \(a^x\)
$$\int a^x \, dx = \frac{a^x}{\ln a} + C \quad C \in \mathbb{R}$$

### Integrale di \(\sin x\)
$$\int \sin x \, dx = -\cos x + C \quad C \in \mathbb{R}$$

### Integrale di \(\cos x\)
$$\int \cos x \, dx = \sin x + C \quad C \in \mathbb{R}$$

### Integrale di \(\frac{1}{\cos^2 x}\)
$$\int \frac{1}{\cos^2 x} \, dx = \tan x + C \quad C \in \mathbb{R}$$

### Integrale di \(1 + \tan^2 x\)
$$\int (1 + \tan^2 x) \, dx = \tan x + C \quad C \in \mathbb{R}$$

### Integrale di \(\frac{1}{\sin^2 x}\)
$$\int \frac{1}{\sin^2 x} \, dx = -\cot x + C \quad C \in \mathbb{R}$$

### Integrale di \(\frac{1}{1 + x^2}\)
$$\int \frac{1}{1 + x^2} \, dx = \arctan x + C \quad C \in \mathbb{R}$$

### Integrale di \(\frac{1}{\sqrt{1 - x^2}}\)
$$\int \frac{1}{\sqrt{1 - x^2}} \, dx = \arcsin x + C \quad C \in \mathbb{R}$$

## PRINCIPI DI LINEARITA'
### Primo principio
> L'integrale della somma è la somma degli integrali.

\(f(x)\) e \(g(x)\) integrabili in *I*

$$\int [f(x) + g(x)] \, dx = \int f(x) \, dx + \int g(x) \, dx$$

### Secondo principio
> L'integrale di una costante \(k \cdot f(x)\) è *k* volte lintegrale di \(f(x)\).

$$\int k f(x) \, dx = k \int f(x) \, dx$$








<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/contrib/auto-render.min.js" onload="renderMathInElement(document.body);"></script>