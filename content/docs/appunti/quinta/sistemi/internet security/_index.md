---
title: "Internet Security"
description: ""
date: 2026-09-18
draft: false
weight: 6
showTableOfContents: true
layout: scroll
---

Il modo più facile per proteggere i dati è nasconderli. 
<br>Questo avviene attraverso la crittografia (tramite principi matematici)

Se ho un server che contiene dati riservati e protetti non lo tengo vicino agli argini di un fiume, ai piedi di vulcani, in zone sismiche oppure esposto al libero accesso di tutti. Questa viene chiamata **sicurezza fisica dei dati.**

C'è bisogno anche di curare la sicurezza non solo fisica ma anche quella di quando viaggiano da una rete all'altra.

Attraverso rete pubblica (internet) vengono trasmessi pin eccetera che devono essere letti solamente dal destinatario.

Per questo nasce **l'internet security.**

Prima si usava il web per cose meno importanti, poi sono nati servizi come home-banking, poste, amazon quindi richiedono un certo **livello di sicurezza.**

Nasce quindi un documento chiamato **X.800** e pone dei protocolli agli standard che dovevano essere utilizzati per far si che siano sicuri.

**X.800 impone dei requisiti che il sistema deve soddisfare:**
1) **Autenticazione**
2) **Controllo degli accessi (autorizzazione)**
3) **Confidenzialità** --> protezione riservatezza dei dati.
4) **Integrità** --> assicurarsi che i dati non siano stati alterati.
5) **Non ripudiabilità** --> protezione contro la negazione di un soggetto coinvolto nella comunicazione. 

## TECNICHE DI CRITTOGRAFIA
Ci sono diverse tipologie di attacchi:
- **Attacco passivo (sniffing):** è un attacco che sta solo a guardare e prendere info. La comunicazione viene ascoltata in maniera non autorizzata.
- **Falsificazione dell'identità (spoofing):** A comunica con B spacciandosi per C.
- **Negazione della paternità:** A nega di aver inviato un precedente messaggio.
- **Attacco attivo:** A e B comunicano, C intercetta i messaggi e li sostituisce con altri.
- **Rifiuti di servizio:** compromissione o disattivazione in modo non autorizzato di alcuni servizi di rete.

Esiste quindi la **stenografia** ovvero l'insieme delle tecniche che permettono di nascondere l'esistenza di un messaggio o della comunicazione stessa. Non è quindi la **crittografia.**

La **crittografia** è quindi la tecnica per la quale non viene nascosto il messaggio ma bensì il suo contenuto.