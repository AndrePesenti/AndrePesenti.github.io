---
title: "Elementi di DevOps"
description: ""
date: 2026-09-15
draft: false
weight: 6
showTableOfContents: true
layout: scroll
---

# Guida completa virtualizzazione e Container
**Cosa fa un virtualizzatore?** Il virtualizzatore serve ad emulare un'archtettura hardware, che viene quindi emulata tramite software.

In un sistema virtualizzato sono presenti 2 sottosistemi:
- **Sistema host:** è il sistema vero e proprio che ospita il virtualizzatore.
- **Sistema guest:** è il sistema che viene virtualizzato (sistema ospite).

Tempo fa si installava una macchina virtuale su cui si andava ad installare il servizio di cui si aveva bisogno. 
<br>Questo funzionava ma costava tanto siccome richiedeva il funzionamento di un intero sistema operativo per ogni virtual machine. Ognuna impiegava quindi moltissime risorse.

L'altro problema è che se si hanno 3 macchine virtuali su un pc, il pc farà fatica a farle girare tutte e 3 contemporaneamente perchè la ram e le risorse sono spesso insufficienti rispetto a quelle richieste. 

Quindi **ognuna delle virtual machine consuma risorse anche semplicemente per stare in vita e accesa.**

Per questo motivo da un po di anni si utilizza un **container engine**, ovvero una infrastruttura che permette di far girare più container (anche una decina).

E' molto vantaggioso perchè non ha bisogno di emulare tutta la parte riguardante il sistema operativo.

Tiene separato ciò che c'è in un determinato container da un'altro. In ogni container metto l'app più le librerie e le dipendenze e basta senza bisogno di tirare su anche il sistema operativo.

Quindi al giorno d'oggi ciascuno sviluppatore sviluppa la propria app direttamente dentro al container.

Quindi **un container è una tecnologia in cui posso mettere le stesse cose della virtual machine senza aver bisogno del sistema operativo.**

Enorme vantaggio è anche che posso far girare anche 10 container assieme senza alcun tipo di problema e in aggiunta sono anche molto più veloci.