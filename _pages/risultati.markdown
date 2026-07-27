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


**Accessibilità Alpha 2** (raggio 45 min):
Somma degli score di popolazione assegnati, per ciascun comune di origine, a tutte le destinazioni raggiungibili entro 45 minuti.
(Score dest. = Popolazione Destinazione / Tempo Effettivo²) 
Misura l'attrattività e l'accessibilità potenziale di un comune in base alla popolazione raggiungibile nei tempi reali di percorrenza.  

**Delta Frizione Medio** (raggio 80 min):
Differenza tra il tempo effettivo di viaggio (grafo TomTom) e il tempo ideale (senza ritardi dovuti a traffico, meteo o chiusura strade). 
Esprime il *ritardo infrastrutturale* medio per raggiungere le destinazioni comprese in un raggio di 80 minuti. 


<div id="mappaSpopolamento"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaSpopolamento', '{{ site.baseurl }}/assets/charts/pop_spop.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script><br>



<div id="mappa_interattiva"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappa_interattiva', '{{ site.baseurl }}/assets/charts/map_spopolamento_interact.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script><br>




<div id="mappaAccessiblita"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaAccessiblita', '{{ site.baseurl }}/assets/charts/mappa_access.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script><br>

---

### Tre Italie: territorio, rischio e mercato immobiliare a confronto

<style>
  .grafico-scroll-container {
    overflow-x: auto;
    overflow-y: hidden;
    max-width: 100%;
    padding-bottom: 12px;      
    border: 1px solid rgba(0, 0, 0, 0.06); 
  }
  .grafico-scroll-container > div {
    display: inline-block;     
  }
</style>

<div class="grafico-scroll-container">
  <div id="descriptivo_storico"></div>
</div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
vegaEmbed('#descriptivo_storico', '{{ site.baseurl }}/assets/charts/descriptivo_storico.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>



#### Interpretazione dei gruppi
##### Gruppo 1. Crescita

- **Numero di comuni:** 2.209
- **Rischio frana (% area media):** 5,73%
- **Rischio alluvione (% area media):** 6,27%
- **Comuni montani:** 34,0%
- **Altitudine media:** 398,0 m
- **Indice di accessibilità (media):** 45.560
- **Tempo dall'hub più vicino:** 18,1 min
- **Andamento prezzo abitazioni:** +1,51%/anno

È un gruppo di comuni caratterizzato da migliore connettività, minore esposizione al rischio geologico e situato prevalentemente in zone di pianura. Presenta il mercato immobiliare più dinamico dei tre gruppi, con la crescita di prezzo più marcata.

##### Gruppo 2. Declino leve

- **Numero di comuni:** 618
- **Rischio frana (% area media):** 8,86%
- **Rischio alluvione (% area media):** 6,54%
- **Comuni montani:** 46,0%
- **Altitudine media:** 465,5 m
- **Indice di accessibilità (media):** 24.775
- **Tempo dall'hub più vicino:** 23,9 min
- **Andamento prezzo abitazioni:** +0,31%/anno

È un gruppo di comuni in una fase intermedia di declino, con un profilo geografico anch'esso intermedio tra crescita e declino severo per rischio, altitudine e accessibilità. Il mercato immobiliare mostra ancora una lieve crescita, ma nettamente più debole rispetto al gruppo in crescita.

##### Gruppo 3. Declino severo

- **Numero di comuni:** 1.268
- **Rischio frana (% area media):** 9,79%
- **Rischio alluvione (% area media):** 5,11%
- **Comuni montani:** 59,6%
- **Altitudine media:** 640,2 m
- **Indice di accessibilità (media):** 17.537
- **Tempo dall'hub più vicino:** 30,6 min
- **Andamento prezzo abitazioni:** −0,08%/anno

È il gruppo di comuni con l'altitudine media maggiore, la più alta proporzione di territorio montano, il rischio frana più elevato e la peggiore accessibilità dei tre gruppi. È l'unico gruppo con il mercato immobiliare stagnante, coerente con un processo di spopolamento strutturale e prolungato in zone di isolamento territoriale.

---
#### Interpretazione dei gruppi

| Indicatore | Crescita | Declino leve | Declino severo |
|---|---|---|---|
| Numero di comuni | 2.209 | 618 | 1.268 |
| Rischio frana (% area media) | 5,73% | 8,86% | 9,79% |
| Rischio alluvione (% area media) | 6,27% | 6,54% | 5,11% |
| Comuni montani | 34,0% | 46,0% | 59,6% |
| Altitudine media | 398,0 m | 465,5 m | 640,2 m |
| Indice di accessibilità (media) | 45.560 | 24.775 | 17.537 |
| Tempo dall'hub più vicino | 18,1 min | 23,9 min | 30,6 min |
| Andamento prezzo abitazioni | +1,51%/anno | +0,31%/anno | −0,08%/anno |

**Crescita** — Migliore connettività, minore esposizione al rischio geologico, situato prevalentemente in zone di pianura. Il mercato immobiliare più dinamico dei tre gruppi.

**Declino leve** — Una fase intermedia di declino, con un profilo geografico anch'esso intermedio tra crescita e declino severo. Il mercato immobiliare mostra ancora una lieve crescita, ma nettamente più debole.

**Declino severo** — L'altitudine media maggiore, la più alta proporzione di territorio montano, il rischio frana più elevato e la peggiore accessibilità. L'unico gruppo con il mercato immobiliare stagnante, coerente con un processo di spopolamento strutturale.

---

### Un ritratto dell'Italia intera: tutti i comuni, 2023-2025
Clustering (aggiungi algoritmo) nazionale su tutti i comuni italiani (su dati triennio 2023-2025)

   PARTE LEO 


#### Interpretazione dei cluster

 PARTE LEO 


---

### I piccoli comuni d'Italia: profili a confronto
Clustering nazionale sui comuni sotto i 15.000 abitanti + Random Forest 




<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_italia.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Interpretazione dei cluster

##### Gruppo 0. Aree ben accessibili e mercato turistico medio
- **Numero di comuni:** 1653
- **Altitudine media:** altitudine media (1.58)
- **Tempo al primo hub (>15.000 ab.):** 18 min
- **Popolazione raggiungibile in 40 minuti:** ~469.000 abitanti
- **Strutture ricettive:** 11
- **Prezzo medio:** 739 €
- **Crescita dal 1992:** stabile (-1%)
- **Delta frizione:** 3.1 (rete stradale efficiente)

È un gruppo caratterizzato da una buona accessibilità e da infrastrutture viarie relativamente efficienti. La presenza turistica è contenuta e i prezzi immobiliari sono bassi, suggerendo territori periferici ma ben collegati.
 
##### Gruppo 1. Aree montane turistiche consolidate
- **Numero di comuni:** 144
- **Altitudine media:** altitudine media (2.83)
- **Tempo al primo hub:** 37 min
- **Popolazione raggiungibile:** ~206.000 abitanti
- **Strutture ricettive:** 163
- **Prezzo medio:** 2.873 €
- **Crescita dal 1992:** stabile
- **Delta frizione:** 11.8 (viabilità difficoltosa)

Comprende località montane con forte vocazione turistica. Pur essendo relativamente isolate e servite da una rete stradale meno efficiente, registrano prezzi immobiliari molto elevati e un'elevata concentrazione di strutture ricettive.
 

##### Gruppo 2. Aree marginali
- **Numero di comuni:** 1374
- **Altitudine media:** montana (2.79)
- **Tempo al primo hub:** 34 min
- **Popolazione raggiungibile:** ~147.000 abitanti
- **Strutture ricettive:** 9
- **Prezzo medio:** 631 €
- **Crescita dal 1992:** -23%
- **Delta frizione:** 6.6

Sono territori montani periferici, con scarsa dotazione turistica e valori immobiliari bassi. La marcata diminuzione della popolazione suggerisce aree soggette a spopolamento.

 
##### Gruppo 4. Aree metropolitane accessibili
- **Numero di comuni:** 524
- **Altitudine media:** pianura (1.26)
- **Tempo al primo hub:** 12 min
- **Popolazione raggiungibile:** ~1,79 milioni di abitanti
- **Strutture ricettive:** 6
- **Prezzo medio:** 1.191 €
- **Crescita dal 1992:** +29%
- **Delta frizione:** 8.3

Questo gruppo ha la maggiore accessibilità potenziale grazie alla vicinanza ai grandi poli urbani. Nonostante la scarsa presenza di strutture ricettive, mostra una forte crescita demografica, probabilmente legata a fenomeni di suburbanizzazione.

 
##### Gruppo 5. Aree in espansione
- **Numero di comuni:** 891
- **Altitudine media:** collina (2.02)
- **Tempo al primo hub:** 18 min
- **Popolazione raggiungibile:** ~520.000 abitanti
- **Strutture ricettive:** 18
- **Prezzo medio:** 1.214 €
- **Crescita dal 1992:** +32%
- **Delta frizione:** 8.4

Comprende territori collinari con buona accessibilità e forte crescita demografica. Il mercato immobiliare è intermedio e la presenza turistica è moderata, indicando aree in fase di sviluppo residenziale e turistico.


##### Gruppo 6. Aree montane isolate
- **Numero di comuni:** 607
- **Altitudine media:** montana (3.48)
- **Tempo al primo hub:** 48 min
- **Popolazione raggiungibile:** ~82.000 abitanti
- **Strutture ricettive:** 17
- **Prezzo medio:** 858 €
- **Crescita dal 1992:** -16%
- **Delta frizione:** 14.8 (rete stradale più penalizzante)

Rappresenta le aree più isolate del campione, con la minore accessibilità e la peggiore qualità della rete stradale. Nonostante una certa presenza di strutture ricettive, i prezzi immobiliari rimangono contenuti e la dinamica demografica è negativa.

---
#### Cosa spiega lo spopolamento nei piccoli comuni?
Random Forest e Features Importance (variabile target: spopolamento SI/NO)
 

<div id="feature_imp_ginevra_it"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_it', '{{ site.baseurl }}/assets/charts/feature_importance_it.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


#### Valutazione e Prestazioni del Modello

**Accuratezza Globale (Accuracy):** 72%<br>
**Precision:** classe 0 - 75%; classe 1 - 68%<br>
**Recall:** classe 0 - 74%; classe 1 - 70%<br>

---

### I comuni alpini: profili a confronto
Clustering (K-means) sui comuni Alpini  + Modello classificatorio (Random Forest)

<div id="clustering_montani_ginivra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clustering_montani_ginivra', '{{ site.baseurl }}/assets/charts/clustering_montani.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Interpretazione dei cluster

 ##### Gruppo 0. – Piccole località montane periferiche

- **Numero di comuni:** 164
- **Presenza di impianti:** limitata.
- **Accessibilità** ridotta (41 min dal primo hub e meno di 100 mila abitanti raggiungibili).
- **Strutture ricettive:** Poche (14 in media).
- **Prezzi immobiliari** contenuti.
- **Demografia:**  marcato Calo (-17% dal 1992).
- **Quota di abitazioni non occupate:** Elevata.

Si tratta di piccole destinazioni montane periferiche, con un'offerta turistica limitata e un progressivo indebolimento demografico.


##### Gruppo 1. – Montagna accessibile e residenziale

- **Numero di comuni:** 94
- **Presenza di impianti:** contenuta
- **Accessibilità** buona (21 min dal primo hub).
- **Prezzi immobiliari** medio-alto.
- **Demografia:** crescita positiva (+16%)
- **Quota di abitazioni non occupate:** Bassa

Comprende comuni facilmente raggiungibili che sembrano svolgere una funzione sia residenziale sia turistica, beneficiando della vicinanza ai principali centri urbani.

 
##### Gruppo 2. – Montagna isolata con criticità infrastrutturali

- **Numero di comuni:** 126
- **Accessibilità:** molto bassa (53 min dal primo hub).
- **Delta frizione:** elevato
- **Prezzi immobiliari** relativamente bassi.
- **Demografia:** calo moderato
- **Turismo:** limitato

Sono territori montani isolati, penalizzati soprattutto dalle condizioni infrastrutturali e dalla distanza dai principali poli.

##### Gruppo 3. – Località montane in trasformazione

- **Numero di comuni:** 205
- **Accessibilità:** intermedia
- **Strutture ricettive:** ridotta
- **Prezzi immobiliari** contenuti
- **Demografia:** sostanzialmente stabile.
- **Perdite di innevamento:** bassa

Rappresentano località montane meno elevate, nelle quali la diminuzione dell'innevamento potrebbe incidere maggiormente sulla competitività del turismo invernale.

##### Gruppo 4. – Destinazioni sciistiche di pregio

- **Numero di comuni:** 37
- **Accessibilità:** limitata ma compensata dall'attrattività turistica.
- **Quota altimetrica:** molto elevata
- **Strutture ricettive:** molto sviluppata (75 strutture in media).
- **Prezzi immobiliari** elevati
- **Presenza impianti:** elevata
- **Perdite di innevamento:** relativamente contenute.
- **Quota altimetrica:**  molto elevata

Sono le principali destinazioni sciistiche, caratterizzate da un mercato immobiliare di valore elevato e da un'offerta turistica consolidata.

##### Gruppo 5. – Grandi poli dello sci

- **Numero di comuni:** 11
- **Accessibilità:** comuni molto isolati
- **Strutture ricettive:** molto alta (Oltre 440 strutture ricettive in media.).
- **Prezzi immobiliari** molto elevati
- **Presenza impianti:** massima
- **Perdite di innevamento:** relativamente contenute.
- **Presenza  seconde case:** Elevata

Comprende i grandi comprensori sciistici nazionali. Nonostante l'isolamento geografico, l'elevata specializzazione turistica sostiene un'importante offerta ricettiva e valori immobiliari elevati.


`Clustering sui comuni Alpini su features (LEO??)` 
plot feature importance SHAP

#### Cosa spiega lo spopolamento nei comuni alpini?
Random Forest e Features Importance su comuni Alpini (variabile target: spopolamento SI/NO)

<div id="feature_imp_ginevra_montani"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_montani', '{{ site.baseurl }}/assets/charts/fi_montano.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Valutazione e Prestazioni del Modello

**Accuratezza Globale (Accuracy):** 76%<br>
**Precision:** classe 0 - 76%; classe 1 - 76%<br>
**Recall:** classe 0 - 64%; classe 1 - 85%<br>


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