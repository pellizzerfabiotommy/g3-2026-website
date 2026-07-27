---
layout: default
title: "Risultati"
permalink: /risultati/
---

# Risultati

## Oltre l'altitudine 

L'applicazione di tecniche di data analysis e clustering ha permesso di superare una lettura uniforme dello spopolamento, mostrando come i piccoli comuni italiani — e in particolare quelli montani — non costituiscano un insieme omogeneo, ma un mosaico di territori con traiettorie evolutive differenti, determinate dalla combinazione di accessibilità ai servizi, contesto altimetrico, rischio idrogeologico, dinamiche climatiche, valori immobiliari e andamento demografico di lungo periodo.



1. **IL PANORAMA NAZIONALE** 

Le seguenti mappe sono state generate utilizzando i dati raccolti sul demografia, accessibilità, rischio idrogeologico e turismo. Rappresentano un momento importante della nostra analisi, in cui abbiamo cercato di rispondere a domande quali:
- Come è distribuito lo spopolamento nel territorio italiano, e quali differenze si evidenziano tra aree diverse? 
- Come si relaziona lo spopolamento all'accessibilità? Il decadimento dell'accessibilità in funzione dell'altitudine ha lo stesso significato (e distribuzione) in diverse aree del territorio italiano?
- Dove si evidenziano scostamenti tra delta negativi e altitudine, ad esempio, zone in cui lo spopolamento non correla all'altitudine? E quali fattori indipendenti possiamo rilevare (es. rischio alluvioni, problemi infrastrutturali)?
- Possiamo identificare aree che, seppur vicine, mostrano fenomeni opposti (es.turismo e crescita; turismo e spopolamento)?

*MAPPA CRESCITA E SPOPOLAMENTO*
<div id="mappaSpopolamento"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaSpopolamento', '{{ site.baseurl }}/assets/charts/pop_spop.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


*MAPPA SPOPOLAMENTO E TERRITORIO*

<div id="mappa_interattiva"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappa_interattiva', '{{ site.baseurl }}/assets/charts/map_spopolamento_interact.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>




*MAPPA ACCESSIBILITA'*

<div id="mappaAccessiblita"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaAccessiblita', '{{ site.baseurl }}/assets/charts/mappa_access.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>



2. **Clustering su serie storica demografica**

   <div id="descriptivo_storico"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#descriptivo_storico', '{{ site.baseurl }}/assets/charts/clustering_montani.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

3. **Clustering nazionale**, su tutti i comuni italiani, utilizzando dati del triennio 2023-2025

   PARTE LEO 

4. **Clustering sui comuni italiani sotto i 15.000 abitanti**

*FEATURES & RISULTATI*


<div id="feature_imp_ginevra_it"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_it', '{{ site.baseurl }}/assets/charts/feature_importance_it.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>



<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_italia.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

## Interpretazione dei cluster

### Cluster 0 – Aree collinari ben accessibili e mercato turistico medio
- **Altitudine media:** collinare (1.58)
- **Tempo al primo hub (>15.000 ab.):** 18 min
- **Popolazione raggiungibile in 40 minuti:** ~469.000 abitanti
- **Strutture ricettive:** 11
- **Prezzo medio:** 739 €
- **Crescita dal 1992:** stabile (-1%)
- **Delta frizione:** 3.1 (rete stradale efficiente)

È un cluster caratterizzato da una buona accessibilità e da infrastrutture viarie relativamente efficienti. La presenza turistica è contenuta e i prezzi immobiliari sono bassi, suggerendo territori periferici ma ben collegati.
 
### Cluster 1 – Aree montane turistiche consolidate
- **Altitudine media:** montana (2.83)
- **Tempo al primo hub:** 37 min
- **Popolazione raggiungibile:** ~206.000 abitanti
- **Strutture ricettive:** 163
- **Prezzo medio:** 2.873 €
- **Crescita dal 1992:** stabile
- **Delta frizione:** 11.8 (viabilità difficoltosa)

Comprende località montane con forte vocazione turistica. Pur essendo relativamente isolate e servite da una rete stradale meno efficiente, registrano prezzi immobiliari molto elevati e un'elevata concentrazione di strutture ricettive.
 

### Cluster 2 – Aree montane marginali
- **Altitudine media:** montana (2.79)
- **Tempo al primo hub:** 34 min
- **Popolazione raggiungibile:** ~147.000 abitanti
- **Strutture ricettive:** 9
- **Prezzo medio:** 631 €
- **Crescita dal 1992:** -23%
- **Delta frizione:** 6.6

Sono territori montani periferici, con scarsa dotazione turistica e valori immobiliari bassi. La marcata diminuzione della popolazione suggerisce aree soggette a spopolamento.

 

### Cluster 3 – Poli urbani
- **Altitudine media:** pianura (1.00)
- **Tempo al primo hub:** 31 min
- **Popolazione raggiungibile:** ~222.000 abitanti
- **Strutture ricettive:** 4.649
- **Prezzo medio:** 2.218 €
- **Crescita dal 1992:** +10%
- **Delta frizione:** 2.7 (rete molto efficiente)

Rappresenta i principali centri urbani, caratterizzati dalla maggiore concentrazione di strutture ricettive, prezzi immobiliari elevati e buona qualità della rete stradale. La crescita demografica positiva conferma la loro attrattività.

 

### Cluster 4 – Aree metropolitane accessibili
- **Altitudine media:** pianura (1.26)
- **Tempo al primo hub:** 12 min
- **Popolazione raggiungibile:** ~1,79 milioni di abitanti
- **Strutture ricettive:** 6
- **Prezzo medio:** 1.191 €
- **Crescita dal 1992:** +29%
- **Delta frizione:** 8.3

È il cluster con la maggiore accessibilità potenziale grazie alla vicinanza ai grandi poli urbani. Nonostante la scarsa presenza di strutture ricettive, mostra una forte crescita demografica, probabilmente legata a fenomeni di suburbanizzazione.

 
### Cluster 5 – Aree collinari in espansione
- **Altitudine media:** collina (2.02)
- **Tempo al primo hub:** 18 min
- **Popolazione raggiungibile:** ~520.000 abitanti
- **Strutture ricettive:** 18
- **Prezzo medio:** 1.214 €
- **Crescita dal 1992:** +32%
- **Delta frizione:** 8.4

Comprende territori collinari con buona accessibilità e forte crescita demografica. Il mercato immobiliare è intermedio e la presenza turistica è moderata, indicando aree in fase di sviluppo residenziale e turistico.

 

### Cluster 6 – Aree montane isolate
- **Altitudine media:** montana (3.48)
- **Tempo al primo hub:** 48 min
- **Popolazione raggiungibile:** ~82.000 abitanti
- **Strutture ricettive:** 17
- **Prezzo medio:** 858 €
- **Crescita dal 1992:** -16%
- **Delta frizione:** 14.8 (rete stradale più penalizzante)

Rappresenta le aree più isolate del campione, con la minore accessibilità e la peggiore qualità della rete stradale. Nonostante una certa presenza di strutture ricettive, i prezzi immobiliari rimangono contenuti e la dinamica demografica è negativa.



5. **Clustering sui comuni Alpini** 
esclusivamente ai comuni Alpini, per indagare le differenti traiettorie interne a un territorio spesso percepito come uniformemente marginale.

*FEATURES & RISULTATI*


<div id="feature_imp_ginevra_montani"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_montani', '{{ site.baseurl }}/assets/charts/fi_montano.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>



<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_montani.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

## Interpretazione dei cluster
#%% md
## Interpretazione dei cluster

### Cluster 0 – Piccole località montane periferiche

- Presenza di impianti limitata.
- Accessibilità ridotta (41 min dal primo hub e meno di 100 mila abitanti raggiungibili).
- Poche strutture ricettive (14 in media).
- Prezzi immobiliari contenuti.
- Marcato calo demografico (-17% dal 1992).
- Elevata quota di abitazioni non occupate.

Si tratta di piccole destinazioni montane periferiche, con un'offerta turistica limitata e un progressivo indebolimento demografico.

---

### Cluster 1 – Montagna accessibile e residenziale

- Buona accessibilità (21 min dal primo hub).
- Bacino potenziale di quasi 500 mila abitanti.
- Crescita demografica positiva (+16%).
- Prezzi immobiliari medio-alti.
- Bassa quota di abitazioni vuote.
- Presenza di impianti contenuta.

Comprende comuni facilmente raggiungibili che sembrano svolgere una funzione sia residenziale sia turistica, beneficiando della vicinanza ai principali centri urbani.

---

### Cluster 2 – Montagna isolata con criticità infrastrutturali

- Accessibilità molto bassa (53 min dal primo hub).
- Peggiore qualità della rete stradale (delta frizione più elevato).
- Bacino di popolazione ridotto.
- Turismo limitato.
- Prezzi immobiliari relativamente bassi.
- Calo demografico moderato.

Sono territori montani isolati, penalizzati soprattutto dalle condizioni infrastrutturali e dalla distanza dai principali poli.

---

### Cluster 3 – Località montane in trasformazione

- Accessibilità intermedia.
- Ridotta presenza di strutture ricettive.
- Minore quota altimetrica rispetto agli altri cluster.
- Maggiore riduzione dell'innevamento.
- Prezzi immobiliari contenuti.
- Dinamica demografica sostanzialmente stabile.

Rappresentano località montane meno elevate, nelle quali la diminuzione dell'innevamento potrebbe incidere maggiormente sulla competitività del turismo invernale.

---

### Cluster 4 – Destinazioni sciistiche di pregio

- Elevata presenza di impianti.
- Offerta ricettiva molto sviluppata (75 strutture in media).
- Prezzi immobiliari più elevati.
- Quota altimetrica molto elevata.
- Perdite di innevamento relativamente contenute.
- Accessibilità limitata ma compensata dall'attrattività turistica.

Sono le principali destinazioni sciistiche, caratterizzate da un mercato immobiliare di valore elevato e da un'offerta turistica consolidata.

---

### Cluster 5 – Grandi poli dello sci

- Massima presenza di impianti.
- Oltre 440 strutture ricettive in media.
- Comuni molto isolati.
- Bacino di popolazione ridotto.
- Prezzi immobiliari molto elevati.
- Condizioni nivologiche relativamente favorevoli.
- Elevata incidenza di seconde case.

Comprende i grandi comprensori sciistici nazionali. Nonostante l'isolamento geografico, l'elevata specializzazione turistica sostiene un'importante offerta ricettiva e valori immobiliari elevati.


6. **Clustering sui comuni Alpini su features bla bla** 
plot feature importance SHAP

7. **Classificazione**
    - random forest nazionale
    - random forest montano 
 
---spiegazione  

 
  

## INTERPRETAZIONE GENERALE DEI RISULTATI 

I risultati indicano che non esiste una quadro unitario, né per i piccoli comuni in generale né per la montagna in particolare. Il turismo non solo non basta a proteggere la sopravvivenza demografica della montagna, ma può essere un fattore di spopolamento, legato, ad esempio, al costo della vita o all'impatto dell'overtourism sulla qualità dei servizi e del benessere.
Che altitudine significhi meno servizi e meno accessibilità sembra abbastanza intuitivo, ma da questo punto di vista la situazione non è omogenea, e ci sono delle differenze tra nord, sud, centro. Inoltre, comuni poco accessibili posso presentare alta vocazione turistica (l'interesse verso alcuni luoghi fa superare alcune barriere, e forse è tipco di certe destinazioni l'essere isolate).

Nel nord, l'altitudine ha un forte potere esplicativo rispetto all'accessibilità. La rete infrastrutturale generale è più solida e risente prevalentemente di limitazioni legate ai territori a quota eleveta; l'accessibilità del centro italia parte da valori più bassi, quella del sud mostra criticità più generali, anche indipendenti dalla quota.


Le features maggiormente rilevanti a **livello globale sono**: accessibilità, turismo, redditi, stratificazione demografica. 


Le features maggiormente rilevanti a **livello alpino**: accessibilità, turismo, variazioni climatiche, redditi.

Una cosa interessante, che rappresenta un possibile punto di partenza per sviluppi ulteriore, è il fatto che le features rilevanti a livello globale possono giocare ruoli differenti a seconda dei contesti.

- nei **territori resilienti**, l'obiettivo è consolidare i fattori di attrattività (servizi, mobilità, diversificazione economica);
- nei **territori vulnerabili**, sono prioritari gli interventi contro lo spopolamento, la riduzione del rischio idrogeologico e il mantenimento dei servizi essenziali;
- nei **territori intermedi/in transizione**, assumono rilievo le strategie di adattamento climatico e la diversificazione dell'economia locale, in particolare riducendo la dipendenza dal turismo legato alla neve.

A livello di comprensione del fenomeno, questa analisi può costituire il punto di partenza per analisi più dettagliate, utilizzando unità analitiche più significative delle unità amministrative (es. aree di comuni che condividono alcuni trend, es. forte spopolamento e pressione turistica vs. crescita e pressione turistica), cambiando granularità nelle analisi (utilizzando dati su flussi stagionali, non solo annuali). 

Può anche offrire un possibile punto di partenza per indirizzare politiche territoriali differenziate e maggiormente mirate alle specifiche condizioni dei diversi contesti locali.



- il clustering sulle serie storiche ha evidenziato.....

-mappe e grafici hanno confermato che..... 

<script>
  const chartData = {{ site.data.chart | jsonify }};
</script>
---

## Dai numeri ai luoghi

Questi profili raccontano dinamiche statistiche su larga scala. Ma cosa significano concretamente per chi vive questi territori? Nella sezione **Casi Studio** raccontiamo da vicino alcuni comuni rappresentativi di questi cluster, incrociando i dati con testimonianze dirette.

[→ Alcuni esempi]({{ '/casi-studio/' | relative_url }})