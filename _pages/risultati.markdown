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
  vegaEmbed('#mappaSpopolamento', '{{ site.baseurl }}/assets/charts/mapppa_spopolament.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


*MAPPA SPOPOLAMENTO E TERRITORIO*

<div id="mappa_interattiva"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappa_interattiva', '{{ site.baseurl }}/assets/charts/interattiva_spop.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>




*MAPPA ACCESSIBILITA'*

<div id="mappaAccessiblita"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#mappaAccessiblita', '{{ site.baseurl }}/assets/charts/test_access.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

2. **Clustering su serie storica demografica**



3. **Clustering nazionale**, su tutti i comuni italiani, utilizzando dati del triennio 2023-2025



4. **Clustering sui comuni italiani sotto i 15.000 abitanti**

*FEATURES & RISULTATI*

plot imp features 

*CLUSTER INDIVIDUATI*

<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_italia.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

 


5. **Clustering sui comuni Alpini su features.... ** 
esclusivamente ai comuni Alpini, per indagare le differenti traiettorie interne a un territorio spesso percepito come uniformemente marginale.

*FEATURES & RISULTATI*

*CLUSTER INDIVIDUATI (MONTANI)*
<div id="clusterMontaniGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterMontaniGinevra', '{{ site.baseurl }}/assets/charts/clustering_montani.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


6. **Clustering sui comuni Alpini su features bla bla** 
plot feature importance SHAP

7. **Classificazione**
    - random forest nazionale
    - random forest montano 
 
---spiegazione  

 
  

## INTERPRETAZIONE DEI RISULTATI 

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