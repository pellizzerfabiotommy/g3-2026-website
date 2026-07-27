---
layout: default
title: "Risultati"
permalink: /risultati/
---

# Risultati

## Oltre l'altitudine 

L'applicazione di tecniche di data analysis e clustering ha permesso di superare una lettura uniforme dello spopolamento, mostrando come i piccoli comuni italiani — e in particolare quelli montani — non costituiscano un insieme omogeneo, ma un mosaico di territori con traiettorie evolutive differenti, determinate dalla combinazione di accessibilità ai servizi, contesto altimetrico, rischio idrogeologico, dinamiche climatiche, valori immobiliari e andamento demografico di lungo periodo.

### IL PANORAMA NAZIONALE 

Le seguenti mappe sono state generate utilizzando i dati raccolti sul demografia, accessibilità, rischio idrogeologico e turismo. Rappresentano un momento importante della nostra analisi, in cui abbiamo cercato di rispondere a domande quali:
- Come è distribuito lo spopolamento nel territorio italiano, e quali differenze si evidenziano tra aree diverse? 
- Come si relaziona lo spopolamento all'accessibilità? Il decadimento dell'accessibilità in funzione dell'altitudine ha lo stesso significato (e distribuzione) in diverse aree del territorio italiano?
- Dove si evidenziano scostamenti tra delta negativi e altitudine, ad esempio, zone in cui lo spopolamento non correla all'altitudine? E quali fattori indipendenti possiamo rilevare (es. rischio alluvioni, problemi infrastrutturali)?
- Possiamo identificare aree che, seppur vicine, mostrano fenomeni opposti (es.turismo e crescita; turismo e spopolamento)?

#### Nota Metodologica su Indicatori

La seguente tabella riassume la metodologia e il significato degli indicatori utilizzati nelle mappe interattive sottostanti:
| Indicatore / Metrica | Metodologia di Calcolo | Significato Analitico |
| :--- | :--- | :--- |
| **Accessibilità Alpha 2**<br>*(raggio 45 min)* | Somma degli *score* assegnati, per ciascun comune di origine, a tutte le destinazioni raggiungibili entro 45 minuti.<br><br>**Score dest. = Popolazione Destinazione / (Tempo Effettivo)²** | Misura l'attrattività e l'accessibilità potenziale di un comune in base alla popolazione raggiungibile nei tempi reali di percorrenza. |
| **Delta Frizione Medio**<br>*(raggio 80 min)* | Differenza tra il **tempo effettivo di viaggio** (grafo TomTom) e il **tempo ideale** (senza ritardi dovuti a traffico, meteo o chiusura strade). | Esprime il *ritardo infrastrutturale* medio per raggiungere le destinazioni comprese in un raggio di 80 minuti. |

<div id="mappaSpopolamento"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaSpopolamento', '{{ site.baseurl }}/assets/charts/pop_spop.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


<div id="mappa_interattiva"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappa_interattiva', '{{ site.baseurl }}/assets/charts/map_spopolamento_interact.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>



<div id="mappaAccessiblita"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaAccessiblita', '{{ site.baseurl }}/assets/charts/mappa_access.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

### Clustering (k-means) su serie storica demografica 

<div id="descriptivo_storico"></div>
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
  vegaEmbed('#descriptivo_storico', '{{ site.baseurl }}/assets/charts/descriptivo_storico.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


#### Interpretazione dei cluster
-Fiorella


### Clustering (aggiungi algoritmo) nazionale su tutti i comuni italiani (su dati triennio 2023-2025)

   PARTE LEO 


#### Interpretazione dei cluster

 PARTE LEO 



### Clustering nazionale sui comuni sotto i 15.000 abitanti + Random Forest 




<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_italia.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Interpretazione dei cluster

`Cluster 0, n.comuni: 1653 – Aree ben accessibili e mercato turistico medio` 
- **Altitudine media:** altitudine media (1.58)
- **Tempo al primo hub (>15.000 ab.):** 18 min
- **Popolazione raggiungibile in 40 minuti:** ~469.000 abitanti
- **Strutture ricettive:** 11
- **Prezzo medio:** 739 €
- **Crescita dal 1992:** stabile (-1%)
- **Delta frizione:** 3.1 (rete stradale efficiente)

È un cluster caratterizzato da una buona accessibilità e da infrastrutture viarie relativamente efficienti. La presenza turistica è contenuta e i prezzi immobiliari sono bassi, suggerendo territori periferici ma ben collegati.
 
`Cluster 1, n.comuni: 144 – Aree montane turistiche consolidate`
- **Altitudine media:** altitudine media (2.83)
- **Tempo al primo hub:** 37 min
- **Popolazione raggiungibile:** ~206.000 abitanti
- **Strutture ricettive:** 163
- **Prezzo medio:** 2.873 €
- **Crescita dal 1992:** stabile
- **Delta frizione:** 11.8 (viabilità difficoltosa)

Comprende località montane con forte vocazione turistica. Pur essendo relativamente isolate e servite da una rete stradale meno efficiente, registrano prezzi immobiliari molto elevati e un'elevata concentrazione di strutture ricettive.
 

`Cluster 2, n. comuni: 1374 -  Aree marginali`
- **Altitudine media:** montana (2.79)
- **Tempo al primo hub:** 34 min
- **Popolazione raggiungibile:** ~147.000 abitanti
- **Strutture ricettive:** 9
- **Prezzo medio:** 631 €
- **Crescita dal 1992:** -23%
- **Delta frizione:** 6.6

Sono territori montani periferici, con scarsa dotazione turistica e valori immobiliari bassi. La marcata diminuzione della popolazione suggerisce aree soggette a spopolamento.

 

`Cluster 4, n. comuni: 524– Aree metropolitane accessibili`
- **Altitudine media:** pianura (1.26)
- **Tempo al primo hub:** 12 min
- **Popolazione raggiungibile:** ~1,79 milioni di abitanti
- **Strutture ricettive:** 6
- **Prezzo medio:** 1.191 €
- **Crescita dal 1992:** +29%
- **Delta frizione:** 8.3

È il cluster con la maggiore accessibilità potenziale grazie alla vicinanza ai grandi poli urbani. Nonostante la scarsa presenza di strutture ricettive, mostra una forte crescita demografica, probabilmente legata a fenomeni di suburbanizzazione.

 
`Cluster 5, n. comuni: 891 – Aree in espansione`
- **Altitudine media:** collina (2.02)
- **Tempo al primo hub:** 18 min
- **Popolazione raggiungibile:** ~520.000 abitanti
- **Strutture ricettive:** 18
- **Prezzo medio:** 1.214 €
- **Crescita dal 1992:** +32%
- **Delta frizione:** 8.4

Comprende territori collinari con buona accessibilità e forte crescita demografica. Il mercato immobiliare è intermedio e la presenza turistica è moderata, indicando aree in fase di sviluppo residenziale e turistico.


`Cluster 6, n.comuni: 607 – Aree montane isolate`
- **Altitudine media:** montana (3.48)
- **Tempo al primo hub:** 48 min
- **Popolazione raggiungibile:** ~82.000 abitanti
- **Strutture ricettive:** 17
- **Prezzo medio:** 858 €
- **Crescita dal 1992:** -16%
- **Delta frizione:** 14.8 (rete stradale più penalizzante)

Rappresenta le aree più isolate del campione, con la minore accessibilità e la peggiore qualità della rete stradale. Nonostante una certa presenza di strutture ricettive, i prezzi immobiliari rimangono contenuti e la dinamica demografica è negativa.

#### Random Forest e Features Importance 


##### Modello Random Forest: Configurazione e Prestazioni

Di seguito sono riportate le specifiche tecniche, i parametri di addestramento e i risultati prestazionali ottenuti dal modello di classificazione per la stima dello **Spopolamento**.

---

#### 🛠️ 1. Configurazione e Parametri del Modello

| Ambito | Parametro / Feature | Valore / Descrizione |
| :--- | :--- | :--- |
| **Obiettivo** | **Target ($y$)** | `Spopolamento` *(Classificazione binaria: 0 / 1)* |
| **Data Split** | **Train / Test** | **75%** Training / **25%** Test *(Stratificato su $y$)* |
| **Algoritmo** | **Estimatore** | `RandomForestClassifier` |
| | **Numero Alberi (`n_estimators`)** | `500` |
| | **Gestione Sbilanciamento** | `class_weight="balanced"` |
| | **Riproducibilità** | `random_state=42` |
| **Feature Input ($X$)** | **Zona altimetrica** | `zona_altimetrica_media` |
| | **Tempo al primo hub (min)** | `tempo_primo_hub_15000` |
| | **Popolazione entro 40 min** | `pop_ray40min` |
| | **Delta frizione** | `delta_frizione_medio` |
| | **Rischio frana** | `PAI_POPP3_P4` |
| | **Strutture ricettive** | `ALL` |
| | **Prezzo medio (€ / m²)** | `Prezzo_medio` |

---

#### 2. Valutazione e Prestazioni del Modello

* **Accuratezza Globale (Accuracy):** **72%** su un campione totale di test pari a **3.737** comuni/unita.

| Classe / Metrica | Precision | Recall | F1-Score | Supporto (Campioni) |
| :--- | :---: | :---: | :---: | :---: |
| **Classe 0** *(Non spopolato)* | `0.75` | `0.74` | **0.74** | 2.056 |
| **Classe 1** *(Spopolato)* | `0.68` | `0.70` | **0.69** | 1.681 |
| **Macro Average** | `0.72` | `0.72` | **0.72** | 3.737 |
| **Weighted Average** | `0.72` | `0.72` | **0.72** | 3.737 |

> **Sintesi delle prestazioni:** Il modello mostra un bilanciamento solido tra le due classi. La classe 0 registra una precisione leggermente più elevata ($75\%$), mentre la classe 1 (spopolamento) mantiene un ottimo richiamo ($70\%$), garantendo la capacità di individuare correttamente la maggior parte dei territori a rischio.

---

*(Di seguito sono riportati i grafici sulla Confusion Matrix e sulla Feature Importance).*### 🌲 Modello Random Forest: Configurazione e Prestazioni

Di seguito sono riportate le specifiche tecniche, i parametri di addestramento e i risultati prestazionali ottenuti dal modello di classificazione per la stima dello **Spopolamento**.

---

#### 🛠️ 1. Configurazione e Parametri del Modello

| Ambito | Parametro / Feature | Valore / Descrizione |
| :--- | :--- | :--- |
| **Obiettivo** | **Target ($y$)** | `Spopolamento` *(Classificazione binaria: 0 / 1)* |
| **Data Split** | **Train / Test** | **75%** Training / **25%** Test *(Stratificato su $y$)* |
| **Algoritmo** | **Estimatore** | `RandomForestClassifier` |
| | **Numero Alberi (`n_estimators`)** | `500` |
| | **Gestione Sbilanciamento** | `class_weight="balanced"` |
| | **Riproducibilità** | `random_state=42` |
| **Feature Input ($X$)** | **Zona altimetrica** | `zona_altimetrica_media` |
| | **Tempo al primo hub (min)** | `tempo_primo_hub_15000` |
| | **Popolazione entro 40 min** | `pop_ray40min` |
| | **Delta frizione** | `delta_frizione_medio` |
| | **Rischio frana** | `PAI_POPP3_P4` |
| | **Strutture ricettive** | `ALL` |
| | **Prezzo medio (€ / m²)** | `Prezzo_medio` |

---

#### 2. Valutazione e Prestazioni del Modello

Target: spopolamento | Accuracy: 0.72 | Precision (Classe 1): 0.68 | Recall (Classe 1): 0.70

<details>
<summary>Dettagli su configurazione, feature e performance</summary>

<br>

#### Configurazione e Iperparametri
| Ambito | Parametro / Configurazione | Dettaglio / Valore |
| :--- | :--- | :--- |
| **Target ($y$)** | Variable Target | `spopolamento` *(Classificazione binaria: 0 / 1)* |
| **Data Split** | Train / Test Ratio | **75%** Training / **25%** Test *(Stratificato su $y$)* |
| **Algoritmo** | Estimatore | `RandomForestClassifier` |
| | Numero Alberi (`n_estimators`) | `500` |
| | Bilanciamento Classi (`class_weight`) | `"balanced"` |
| | Riproducibilità (`random_state`) | `42` |

#### Feature di Input ($X$)
| Nome Variabile Originale | Nome "Human-Readable" | Descrizione / Ambito |
| :--- | :--- | :--- |
| `zona_altimetrica_media` | Zona altimetrica | Caratterizzazione altimetrica del territorio |
| `tempo_primo_hub_15000` | Tempo al primo hub (min) | Accessibilità ai servizi essenziali |
| `pop_ray40min` | Popolazione entro 40 min | Bacino demografico gravitazionale |
| `delta_frizione_medio` | Delta frizione | Ritardo infrastrutturale medio della rete viaria |
| `PAI_POPP3_P4` | Rischio frana | Esposizione al rischio idrogeologico (PAI) |
| `ALL` | Strutture ricettive | Offerta turistico-ricettiva locale |
| `Prezzo_medio` | Prezzo medio (€ / m²) | Valore del mercato immobiliare |

#### Report di Classificazione Completo
| Classe / Metrica | Precision | Recall | F1-Score | Supporto (Campioni) |
| :--- | :---: | :---: | :---: | :---: |
| **Classe 0** *(Non spopolato)* | 0.75 | 0.74 | **0.74** | 2.056 |
| **Classe 1** *(Spopolato)* | 0.68 | 0.70 | **0.69** | 1.681 |
| **Accuracy** | — | — | **0.72** | 3.737 |
| **Macro Average** | 0.72 | 0.72 | **0.72** | 3.737 |
| **Weighted Average** | 0.72 | 0.72 | **0.72** | 3.737 |

</details>

<div id="feature_imp_ginevra_it"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_it', '{{ site.baseurl }}/assets/charts/feature_importance_it.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>




### Clustering (K-means) sui comuni Alpini  + Modello classificatori (Random Forest)

<div id="clusterItaliaGinevra_montani"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra_montani', '{{ site.baseurl }}/assets/charts/clustering_montani.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Interpretazione dei cluster

 `Cluster 0 – Piccole località montane periferiche`

- Presenza di impianti limitata.
- Accessibilità ridotta (41 min dal primo hub e meno di 100 mila abitanti raggiungibili).
- Poche strutture ricettive (14 in media).
- Prezzi immobiliari contenuti.
- Marcato calo demografico (-17% dal 1992).
- Elevata quota di abitazioni non occupate.

Si tratta di piccole destinazioni montane periferiche, con un'offerta turistica limitata e un progressivo indebolimento demografico.

---

`Cluster 1 – Montagna accessibile e residenziale`

- Buona accessibilità (21 min dal primo hub).
- Bacino potenziale di quasi 500 mila abitanti.
- Crescita demografica positiva (+16%).
- Prezzi immobiliari medio-alti.
- Bassa quota di abitazioni vuote.
- Presenza di impianti contenuta.

Comprende comuni facilmente raggiungibili che sembrano svolgere una funzione sia residenziale sia turistica, beneficiando della vicinanza ai principali centri urbani.

 
`Cluster 2 – Montagna isolata con criticità infrastrutturali`

- Accessibilità molto bassa (53 min dal primo hub).
- Peggiore qualità della rete stradale (delta frizione più elevato).
- Bacino di popolazione ridotto.
- Turismo limitato.
- Prezzi immobiliari relativamente bassi.
- Calo demografico moderato.

Sono territori montani isolati, penalizzati soprattutto dalle condizioni infrastrutturali e dalla distanza dai principali poli.

`Cluster 3 – Località montane in trasformazione`

- Accessibilità intermedia.
- Ridotta presenza di strutture ricettive.
- Minore quota altimetrica rispetto agli altri cluster.
- Maggiore riduzione dell'innevamento.
- Prezzi immobiliari contenuti.
- Dinamica demografica sostanzialmente stabile.

Rappresentano località montane meno elevate, nelle quali la diminuzione dell'innevamento potrebbe incidere maggiormente sulla competitività del turismo invernale.

`Cluster 4 – Destinazioni sciistiche di pregio`

- Elevata presenza di impianti.
- Offerta ricettiva molto sviluppata (75 strutture in media).
- Prezzi immobiliari più elevati.
- Quota altimetrica molto elevata.
- Perdite di innevamento relativamente contenute.
- Accessibilità limitata ma compensata dall'attrattività turistica.

Sono le principali destinazioni sciistiche, caratterizzate da un mercato immobiliare di valore elevato e da un'offerta turistica consolidata.

`Cluster 5 – Grandi poli dello sci`

- Massima presenza di impianti.
- Oltre 440 strutture ricettive in media.
- Comuni molto isolati.
- Bacino di popolazione ridotto.
- Prezzi immobiliari molto elevati.
- Condizioni nivologiche relativamente favorevoli.
- Elevata incidenza di seconde case.

Comprende i grandi comprensori sciistici nazionali. Nonostante l'isolamento geografico, l'elevata specializzazione turistica sostiene un'importante offerta ricettiva e valori immobiliari elevati.


`Clustering sui comuni Alpini su features (LEO??)` 
plot feature importance SHAP

#### Random Forest e Features Importance su comuni Alpini 

Target: spopolamento | Accuracy: 0.76 | Precision (Classe 1): 0.76 | Recall (Classe 1): 0.85

<details>
<summary>Dettagli su configurazione, feature e performance</summary>

<br>

#### Configurazione e Iperparametri
| Ambito | Parametro / Configurazione | Dettaglio / Valore |
| :--- | :--- | :--- |
| **Target ($y$)** | Variable Target | `spopolamento` *(Classificazione binaria: 0 / 1)* |
| **Data Split** | Train / Test Ratio | **75%** Training / **25%** Test *(Stratificato su $y$)* |
| **Algoritmo** | Estimatore | `RandomForestClassifier` |
| | Numero Alberi (`n_estimators`) | `500` |
| | Bilanciamento Classi (`class_weight`) | `"balanced"` |
| | Riproducibilità (`random_state`) | `42` |

#### Feature di Input ($X$)
| Nome Variabile Originale | Descrizione / Ambito |
| :--- | :--- |
| `zona_altimetrica_media` | Zona altimetrica media |
| `tempo_primo_hub_15000` | Tempo di percorrenza verso il primo hub di servizi |
| `pop_ray40min` | Popolazione residente nel raggio di 40 minuti |
| `delta_temp` | Variazione della temperatura media |
| `delta_snow` | Variazione delle precipitazioni nevose / copertura nevosa |
| `Prezzo_medio` | Prezzo medio immobiliare (€ / m²) |
| `presenza_impianti` | Indicatore presenza impianti sportivi / sciistici |
| `pct_vuote` | Percentuale di abitazioni non occupate / vuote |

#### Report di Classificazione Completo
| Classe / Metrica | Precision | Recall | F1-Score | Supporto (Campioni) |
| :--- | :---: | :---: | :---: | :---: |
| **Classe 0** *(Non spopolato)* | 0.76 | 0.64 | **0.69** | 400 |
| **Classe 1** *(Spopolato)* | 0.76 | 0.85 | **0.80** | 542 |
| **Accuracy** | — | — | **0.76** | 942 |
| **Macro Average** | 0.76 | 0.74 | **0.75** | 942 |
| **Weighted Average** | 0.76 | 0.76 | **0.76** | 942 |

</details>
<div id="feature_imp_ginevra_montani"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_montani', '{{ site.baseurl }}/assets/charts/fi_montano.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


## I RISULTATI IN SINTESI 

I risultati indicano che non esiste una quadro unitario, né per i piccoli comuni in generale né per la montagna in particolare. Il turismo non sempre basta a garantire la sopravvivenza demografica della montagna; a volte può essere un fattore di spopolamento, legato, ad esempio, al costo della vita o all'impatto dell'overtourism sulla qualità dei servizi e del benessere.
Che altitudine significhi meno servizi e meno accessibilità sembra abbastanza intuitivo, ma da questo punto di vista la situazione non è omogenea, e ci sono delle differenze tra nord, sud, centro. Inoltre, comuni poco accessibili posso presentare alta vocazione turistica (l'interesse verso alcuni luoghi fa superare alcune barriere, e forse è tipco di certe destinazioni l'essere isolate).

Nel nord, l'altitudine ha un forte potere esplicativo rispetto all'accessibilità. La rete infrastrutturale generale è più solida e risente prevalentemente di limitazioni legate ai territori a quota eleveta; l'accessibilità del centro italia parte da valori più bassi, quella del sud suggerisce criticità più generali, forse indipendenti dall'altitudine.

Le features maggiormente rilevanti a **livello globale sono**: accessibilità, turismo, redditi, stratificazione demografica.

Le features maggiormente rilevanti a **livello alpino**: accessibilità, turismo, variazioni climatiche, redditi.

Una cosa interessante, che rappresenta un possibile punto di partenza per sviluppi ulteriori, è il fatto che le features rilevanti a livello globale sembrano giocare ruoli differenti a seconda dei contesti.

A livello di comprensione del fenomeno, questo lavoro può costituire un punto di partenza per analisi più dettagliate. Il clustering e le mappe,ad esempio, sono funzionali all'individuazione di unità analitiche più significative di quelle imposte dai confini amministrativi (es. aree di comuni che condividono alcuni trend, es. forte spopolamento e pressione turistica vs. crescita e pressione turistica), cambiando granularità nelle analisi (utilizzando dati su flussi stagionali, non solo annuali). 

Può anche essere rilevante per la progettazione di misure politiche territoriali differenziate e maggiormente mirate alle specifiche condizioni dei diversi contesti locali.



<script>
  const chartData = {{ site.data.chart | jsonify }};
</script>
---

### Dai numeri ai luoghi

Questi profili raccontano dinamiche statistiche su larga scala. Ma cosa significano concretamente per chi vive questi territori? Nella sezione **Casi Studio** raccontiamo da vicino alcuni comuni rappresentativi di questi cluster, incrociando i dati con testimonianze dirette.

[→ Alcuni esempi]({{ '/casi-studio/' | relative_url }})