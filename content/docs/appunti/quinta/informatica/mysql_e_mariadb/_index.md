---
title: "MySQL e MariaDb"
description: ""
date: 2026-09-29
draft: false
weight: 6
showTableOfContents: true
layout: scroll
---

## ARCHITETTURA SQL
![Immagine architettura](image.png)

**Engine:** insieme di codice e algoritmi che consentono la gestione dei database. 

**InnoDB:** engine più completo che gestisce anche le transazioni. 

## CARATTERISTICHE LINGUAGGIO SQL
Il linguaggio sql è un linguaggio dichiarativo: non dobbiamo scrivere un algoritmo. Devo solo dichiarare cosa voglio e sarà poi l’engine ad implementare il codice per fornirmi il risultato.

È possibile creare utenti con diversi privilegi. L’utente root è quello con il massimo dei privilegi. 

### Esempio linguaggio dichiarativo
Se io avessi un elenco con tutti gli studenti del Greppi e voglio recuperare l’elenco degli studenti della 5IA. <br>
Per farlo si implementerebbe il seguente codice:

![Immagine](image2.png)

Non sto dicendo cosa devo fare ma cosa voglio fare. Sarà poi l’engine a farmi l’algoritmo per far si che la cosa che ho scritto venga effettuata.

## MODI DI UTILIZZO SQL
1. **Modalità interattiva:** si utilizza un interprete di comandi testuale o grafico che permette di eseguire e visualizzare i risultati delle query. In modalità interattiva io faccio una query e vedo immediatamente il risultato. 

2.	**Modalità programma:** l’applicativo si deve connettere al database e inietta codice sql nella richiesta.

## COMPONENTI LINGUAGGIO SQL
- **DDL: Data Definition Language** – contiene le istruzioni per creare il modello dei dati. Qui dentro si va a definire la struttura dei dati

- **DML: Data Manipulation Language** – contiene quelle istruzioni che ci permettono di manipolare i dati (recuperare i dati da una tabella, inserire dei dati, modificare dei dati, cancellare dei dati).

- **DCL: Data Control Language** – ci sono le istruzioni che mi permettono di definire chi può fare cosa. Posso creare degli utenti e definire permessi per ogni utente.

![Immagine](image3.png)

**Principio minimo privilegio:** un utente deve avere dei permessi minimi per ciò che deve fare in modo che l’effetto di un potenziale attacco sia comunque ridotto. Non deve avere privilegi più elevati rispetto a quello che deve fare. 

## CREARE UN DATABASE
![Immagine](creare_database.png)

Tutte le istruzioni terminano con il ;

Le parentesi quadre indicano parametri opzionali

![Immagine](parentesi_quadre.png)

In questo esempio il [IF NOT EXIST] indica un parametro opzionale. Se non si mettono questi parametri opzionali si assumeranno i valori di default.

### Valori di default
- Default character set: utf8mb4
- Collection: utf8mb4_0900_ai_ci