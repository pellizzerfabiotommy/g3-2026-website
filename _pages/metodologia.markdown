---
layout: default
title: "Metodologia"
permalink: /metodologia/
---

# La nostra Metodologia

L'analisi si basa sull'integrazione di diverse fonti pubbliche, raccolte ed elaborate attraverso un mix di strumenti automatizzati (API, script di scraping) e verifiche manuali.

### ISTAT
Fonte principale per i dati territoriali, demografici e socioeconomici: popolazione residente, dati reddituali, flussi turistici, strutture ricettive, e matrici delle distanze tra comuni. I dati sono stati acquisiti tramite:
- **ISTAT API**, per l'estrazione programmatica delle serie storiche disponibili;
- **web scraping**, per il recupero di dataset non esposti tramite API;
- **download manuale** dai repository pubblici ISTAT, per gli archivi non altrimenti accessibili.

### Open-Meteo API
Utilizzata per ricostruire le serie storiche climatiche relative a circa 3.000 comuni italiani, fornendo il contesto ambientale necessario a mettere in relazione le dinamiche di spopolamento con fattori meteo-climatici di lungo periodo.

### OpenStreetMap API
Impiegata per calcolare lo storico delle distanze dai principali servizi (sanitari, scolastici, di trasporto, ecc.) per circa 3.000 comuni, permettendo di valutare l'evoluzione dell'accessibilità territoriale nel tempo.

### Osservatorio del Mercato Immobiliare (OMI)
Fonte dei dati sulle quotazioni immobiliari dell'Agenzia delle Entrate e le dinamiche del mercato immobiliare, utilizzata per analizzare l'andamento dei valori e dell'attrattività abitativa nei comuni montani oggetto di studio.


## Raccolta e Analisi

La raccolta dei dati è stata automatizzata tramite script Python dedicati all'interrogazione delle diverse API, alla trasformazione delle risposte in DataFrame strutturati e al successivo salvataggio in un database SQL, garantendo un'unica base dati consistente e interrogabile per tutte le analisi successive.

Sui dati raccolti sono stati applicati diversi algoritmi di machine learning, scelti in base all'obiettivo analitico:

- **Clustering**, per individuare gruppi di comuni con caratteristiche simili in termini di spopolamento, accessibilità e contesto socioeconomico: *K-Means*, *DBSCAN* e clustering *gerarchico*;
- **Classificazione**, per identificare i fattori più rilevanti nel distinguere comuni a rischio di abbandono da comuni stabili: *Random Forest* e *regressione logistica*;
- **Regressione lineare**, per quantificare la relazione tra variabili demografiche, infrastrutturali ed economiche;
- **Clustering su serie storiche**, per identificare pattern relativi alle serie storiche 

## Strumenti e strategie

* **Linguaggi di programmazione:** Python, SQL

* **Librerie principali:**
- `pandas`, `numpy` — manipolazione e analisi dei dati
- `scikit-learn` — preprocessing e modelli di machine learning (clustering, classificazione, regressione)
- `statsmodels` — modelli statistici e regressioni su serie storiche
- `scipy` — analisi di correlazione e calcolo delle distanze tra osservazioni
- `matplotlib`, `seaborn`,`Altair` — visualizzazione dei dati e dei risultati

* **Algoritmi:**
- `Kmeans, Hierarchical Clustering, Dbscan, Hdbscan, DTW` (Clustering)
- `Random Forest` (Classificazione)

* **Strategie di preprocessing e feature engineering:**

- **normalizzazione codice** istat per gestire le serie storiche (comuni che si sono accorpati)
- **creazione di indicatori** (es. per riassumere serie storiche) 
- **ri-organizzazione** dati, attraverso pivot, raggruppamenti (es. per ottenere granularità 1 riga 1 comune)
- **gestione dei nulli** attraverso imputazione (v. serie storica flussi turistici presentava nulli durante il covid), dati mancanti