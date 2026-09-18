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

Come fa il sistema operativo guest a funzionare? 

Ci sono 2 famiglie principali di virtualizzatori:
- **Bare metal:** hanno l'accesso diretto all'hardware.
- **Hosted:** girano come app all'interno del sistema operativo stesso.

I virtualizzatori bare metal sono più prestanti.

Il deployment delle applicazioni cloud veniva fatto tramite l'utilizzo di virtual machine. Questo funzionava ma come già detto in maniera non efficiente poichè utilizzava troppe risorse. La soluzione sono stati i **container.**

I container utilizzano Linux quasi per ogni cosa che bisogna fare.

C'è un **enorme vantaggio** ovvero che la memoria che utilizza e occupa un container è strettamente quella dell'applicativo (e delle cose ad esso collegato per esempio il runtime di dotnet qualora l'applicativo fosse .net)

## Elementi architetturali Docker
- **Docker Client:** interfaccia a riga di comando con cui interagisce l'utente.
- **Docker Daemon:** è il cuore del docker. E' un processo server persistente che gira in background. Ascolta le richieste del client e si occupa di tutto il lavoro.
- **Registry:** un repository dove mettere le immagini docker.

## Docker Internals
Docker non sarebbe possibile senza 3 tecnologie chiave del Kernel Linux

- **Namespace:** featur che permette di partizionare risorse globali in modo che un gruppo di processi veda solo un sottoinsieme di tali risorse. 

Ci sono 3 tipi di namespace
- **PID (Process ID):** isola l'albero dei processi.
- **NET (Network):** fornisce ai container il proprio stack di rete isolato. 
- **MNT (Mount):** isola i punti di mount.

## Docker Compose
E' lo strumento di orchestrazione di primo livello per ambienti di sviluppo e testing.

Permette di gestire un'applicazione multi-container attraverso un singolo file di configurazione.

Un enorme **punto di forza** è che è capace di replicare un'intera architettura sofrtware con un unico comando (docker-compose up).

## Comandi di base di Docker

### Lanciare un nuovo container
``` bash
docker run nome-immagine
```

Questo comando con run ogni nuova che viene lanciato lancia un nuovo container quindi se ne devo riutilizzare uno già esistente non va bene ma devo utilizzare un altro comando.

Se l'immagine inserita non è scaricata localmente la scarica in automatico.

### Mostrare tutti i container attivi
``` bash
docker ps
```

Questo comando mostra solamente quelli attualmente in esecuzione.

``` bash
docker ps -a
```

Questo li mostra tutti (anche quelli precedentemente in esecuzione).

### Far partire container esistente
``` bash
docker start container_id
```

### Fermare un container
``` bash
docker stop container_id
```

### Rimuovere un container
``` bash
docker rm container_id
```

### Eseguire un container con rimozione automatica
``` bash
docker run -d --rm ubuntu sleep 20
```

Questo comando *"-d"* permette di non bloccare la shell ma di continuare a utilizzarla anche metre il container è in esecuzione. *"--rm"* lo rimuove al termine di quello che deve fare.

``` bash
docker images
```

### Rimuovere immagini
``` bash
docker rmi id_immagine
```

### Varianti comandi
```bash
-i: permette di avere accesso allo standard input del container ma per poter interagire con esso 
di solito occorre abilitare anche l'opzione -t
-t: spiegato sopra
-d: modalità detached - la shell continua a essere utilizzabile e non si blocca
```