---
title: "Ripasso"
description: ""
date: 2026-09-16
draft: false
weight: 6
showTableOfContents: true
layout: scroll
---

## Subnetting
Fare subnetting significa suddividere gruppi di host nella rete.

E' un **indirizzamento logico** che consente di assegnare a delle schede di rete con indirizzo fisico un indirizzo logico. 

Ogni scheda di rete ha un proprio **indirizzo fisico (MAC address)** che rimane lo stesso per tutta la vita. A questa scheda di rete viene assegnato un indirizzo logico: la **subnet**.

### Classi
- Classe A: /8
- Classe B: /16
- Classe C: /24

L'indirizzamento più elementare è **l'indirizzamento classfull** ma presenta dei difetti: si creno degli spazi che non si possono utilizzare, e tutti questi sono spazi sprecati. 

### Subnet Mask
- /8: 255.0.0.0
- /16 255.255.0.0
- /24: 255.255.255.0

L'**arp table** è una tabella che associa il MAC address (indirizzo fisico), all'indirizzo IP (indirizzo logico). 

Per mediare al problema dell'indirizzamento classfull si è creato **l'indirizzamento classless.**

In questo indirizzamento posso utilizzare tutti i cidr che voglio e non limitarmi alle /8, /16 o /24. Per esempio se devo subnettare 20 hosto posso usare una /27.

### Esempi di Indirizzamento Classless

Major: 162.168.0.0

Subnettare 4 reti da 20 host ciascuna. Quindi 4 reti /27.

| **CIDR** | **RETE** | **B.C.** | **S.M.** |
| :---: | :---: | :---: | :---: |
| */27* | .0.0 | .0.31 | 255.224 |
| */27* | .0.32 | .0.63 | 255.224 |
| */27* | .0.64 | .0.95 | 255.224 |
| */27* | .0.96 | .0.127 | 255.224 |


_______________________________________________________________________________________________

Major: 162.168.0.0

Subnettare le seguenti reti:
- A: 6 host
- B: 40 host
- C: 10 host
- D: 52 host

| **HOST** | **CIDR** | **RETE** | **B.C.** | **S.M.** |
| :---: | :---: | :---: | :---: | :---: |
| 6 | */26* | .0.0 | .0.63 | 255.192 |
| 40 | */26* | .0.64 | .0.127 | 255.192 |
| 10 | */26* | .0.128 | .0.191 | 255.192 |
| 52 | */26* | .0.192 | .0.255 | 255.192 |

Essendo questo un **indirizzamento classless** devo scegliere il cidr per quello più grande e la assegno uguale a tutti. Quindi in questo caso la rete più grande è la D da 52 host quindi prendo un */26* e la assegno a tutti. 

Facendo questo spreco ancora spazio quindi il problema non viene risolto.

Quindi si usa **l'indirizzamento VLSM**, ovvero un **indirizzamento a lunghezza variabile.**

### Esempio di Indirizzamento VLSM

Major: 162.168.0.0

| **HOST** | **CIDR** | **M.N.** | **RETE** | **RETE SUCCESSIVA** | **B.C.** | **S.M.** |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 6 | */29* | 8 | .0.0 | .0.8 | .0.7 | 255.248 |
| 40 | */26* | 64 | .0.64 | .0.128 | .0.127 | 255.192 |
| 10 | */28* | 16 | .0.16 | .0.32 | .0.31 | 255.240 |
| 52 | */26* | 64 | .0.128 | .0.192 | .0.192 | 255.192 |

_______________________________________________________________________________________________

Major: 162.168.0.0

Subnettare le seguenti reti:
- A: 6 host
- B: 20 host
- C: 12 host
- D: 2 host
- E: 31 host
- F: 40 host
- G: 18 host
- H: 30 host

| **HOST** | **CIDR** | **M.N.** | **RETE** | **RETE SUCCESSIVA** | **B.C.** | **S.M.** |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| A: 6 | */29* | 8 | .0.0 | .0.8 | .0.7 | 255.248 |
| B: 20 | */27* | 32 | .0.32 | .0.64 | .0.63 | 255.224 |
| C: 12 | */28* | 16 | .0.16 | .0.32 | .0.31 | 255.240 |
| D: 2 | */30* | 4 | .0.8 | .0.12 | .0.11 | 255.252 |
| E: 31 | */26* | 64 | .0.64 | .0.128 | .0.127 | 255.192 |
| F: 40 | */26* | 64 | .0.128 | .0.192 | .0.191 | 255.192 |
| G: 18 | */27* | 32 | .0.192 | .0.224 | .0.223 | 255.224 |
| H: 30 | */27* | 32 | .0.224 | .0.256 | .0.255 | 255.224 |

## Routing
Ci da la possibilità di far comunicare host che non appartengono alla stessa rete. 

Esistono diversi protocolli di routing: OSPF, routing statico e routing dinamico.

Lo strumento che consente al router di instradare i pacchetti è la **routing table.**

La **routing table** contiene 
- Next Hop
- Distanza Amministrativa
- IP di destinazione
- Metrica

La **distanza amministrativa** è il grado di afffidabilità di un percorso. Si tratta di un numero da 0 a 255 in cui 0 è la massima affidabilità e 255 la meno affidabile. 
- Con 0 si indicano i direttamente connessi.
- Con 1 si indicano le reti statiche.

### Come capire di quale rete fa parte un host
192.168.10.10/21 - a partire da questo indirizzo host devo capire qual'è la sua rete di appartenenza.

Essendo una /21 significa che l'ottetto critico è il terzo.

Scomp0ngo il terzo ottetto in numero binario: 00001/010. La parte prima della barra è *net* mentre quello dopo + *host*.

A partire da quello per avere l'indirizzo di rete devo porre tutta la parte host a 0.

L'indirizzo di rete diventa sarà quindi 162.168.8.0/21

_______________________________________________________________________________________________

Indirizzo host: 192.168.101.10/19

Determinare l'indirizzo della rete di appartenenza

Ottetto critico: terzo

Terzo ottetto in codice binario: 011/00101

Conversione della parte host a 0: 01100000 = 96

**Indirizzo di rete:** 192.168.96.0

Passo di una barra 19: 32-19=13
<br> 2^13 = 8192, 32 sul 3° ottetto

**Indirizzo di rete successivo:** 192.168.128.0

**Indirizzo di broadcast:** 192.168.127.255