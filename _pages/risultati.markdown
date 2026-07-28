---
layout: default
title: "Risultati"
permalink: /risultati/
---

# Risultati

## Oltre l'altitudine 

L'applicazione di tecniche di data analysis e clustering ha permesso di superare una lettura uniforme dello spopolamento, mostrando come i piccoli comuni italiani — e in particolare quelli montani — non costituiscano un insieme omogeneo, ma un mosaico di territori con traiettorie evolutive differenti, determinate dalla combinazione di accessibilità ai servizi, contesto altimetrico, rischio idrogeologico, dinamiche climatiche, valori immobiliari e andamento demografico di lungo periodo.

### IL PANORAMA NAZIONALE 

Le seguenti mappe e grafici sono state generate utilizzando i dati raccolti sul demografia, accessibilità, rischio idrogeologico e turismo. Rappresentano un momento importante della nostra analisi, in cui abbiamo cercato di rispondere a domande quali:
- Come è distribuito lo spopolamento nel territorio italiano, e quali differenze si evidenziano tra aree diverse? 
- Come si relaziona lo spopolamento all'accessibilità? Il decadimento dell'accessibilità in funzione dell'altitudine ha lo stesso significato (e distribuzione) in diverse aree del territorio italiano?
- Dove si evidenziano scostamenti tra delta negativi e altitudine, ad esempio, zone in cui lo spopolamento non correla all'altitudine? E quali fattori indipendenti possiamo rilevare (es. rischio alluvioni, problemi infrastrutturali)?
- Possiamo identificare aree che, seppur vicine, mostrano fenomeni opposti (es.turismo e crescita; turismo e spopolamento)?

#### Nota Metodologica su Indicatori


**Accessibilità Alpha 2** (raggio 45 min):
Somma degli score di popolazione assegnati, per ciascun comune di origine, a tutte le destinazioni raggiungibili entro 45 minuti.
(Score dest. = Popolazione Destinazione / Tempo Effettivo²) 
Misura la centralità di un comune in base alla popolazione raggiungibile nei tempi reali di percorrenza. Raggruppando diversi comuni, l'accessibilità media può anche esprimere la facilità o difficoltà nelle connesioni tra unità territoriali.  

**Delta Frizione Medio** (raggio 80 min):
Differenza tra il tempo effettivo di viaggio (grafo TomTom) e il tempo ideale (senza ritardi dovuti a traffico, meteo o chiusura strade). 
Esprime il *ritardo infrastrutturale* medio per raggiungere le destinazioni comprese in un raggio di 80 minuti. La scelta di questo raggio dipende dal focus del progetto: si è scelto di misurare il ritardo infrastrutturale nei tratti che collegano i comuni montani ad altre aree locali e centri di rilievo, indipendentemente dal contesto più ampio (provinciale e regionale).


---
<style>
  .mapas-comparacion {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 24px;
    align-items: start;
    margin: 20px 0;
  }
  .mapa-container {
    width: 100%;
    max-width: 500px;
  }
  .mapa-container p {
    font-size: 0.9em;
    line-height: 1.5;
    margin-bottom: 12px;
    color: #444;
  }
</style>

<div class="mapas-comparacion">

  <div class="mapa-container">
    <p>La mappa 1 mostra il diverso grado di spopolamento e crescita (il delta tra inizio della serie storica e fine) dei comuni italiani di cui abbiamo ricavato le metriche di accessibilità (accessibilità alpha2 è visibile nel tooltip, insieme a fascia altimetrica, delta demografico e vocazione turistica). Possiamo osservare differenze interessanti: ad esempio, le aree montane del Friuli-Venezia Giulia mostrano alta vocazione turistica, accessibilità tendenzialmente bassa e forte spopolamento, mentre nelle vicine aree montane del Trentino-Alto Adige (che includono destinazioni molto note e ricercate) l'alta vocazione turistica si accompagna ad accessibilità più alta, e i comuni presentano trend positivi.</p>
    <div id="mappaSpopolamento"></div>
  </div>

  <div class="mapa-container">
    <p>La mappa 2 visualizza l'accessibilità (nel tooltip: delta frizione, delta demografico, fascia altimetrica media). Possiamo osservare un "corridoio" di alta accessibilità nel Trentino-Alto Adige. In generale, la mappa conferma quanto osservato nelle analisi riguardo alla distribuzione dell'accessibilità nel territorio italiano (differenze tra nord, centro e sud; decadimento dell'accessibilità all'aumentare dell'altitudine, soprattutto al nord; situazioni dove il ritardo infrastrutturale (delta frizione) correla con poca accessibilità).</p>
    <div id="mappaAccessiblita"></div>
  </div>

  <div class="mapa-container">
    <p>La mappa 3 invece permette di selezionare diversi intervalli di altitudine e di spopolamento, evidenziando i comuni montani (score di altezza media = 3, circa 800 mt). Questo consente di individuare in quali aree lo spopolamento si sovrappone (o si discosta) dall'altitudine, testando diversi range e verificando (nel tooltip) la presenza di impianti e score di accessibilità.</p>
    <div id="mappa_interattiva"></div>
  </div>

</div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
vegaEmbed('#mappaSpopolamento', '{{ site.baseurl }}/assets/charts/pop_spop.json')
    .catch(err => console.error('Errore rendering grafico:', err));

vegaEmbed('#mappaAccessiblita', '{{ site.baseurl }}/assets/charts/mappa_access.json')
    .catch(err => console.error('Errore rendering grafico:', err));

vegaEmbed('#mappa_interattiva', '{{ site.baseurl }}/assets/charts/map_spopolamento_interact.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>  



<div id="jitter_acc"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#jitter_acc', '{{ site.baseurl }}/assets/charts/jitter_acc.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

---

### Tre Italie: territorio, rischio e mercato immobiliare a confronto

C'è un'Italia che cresce a diciotto minuti da un centro urbano, e un'Italia che ne dista più di trenta. Analizzando trent'anni di dati su tutti i comuni italiani, emerge un pattern chiaro: più un comune è isolato, più rapidamente perde i suoi abitanti. Non è un caso — è una tendenza che si ripete, comune dopo comune, con una regolarità sorprendente.

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


| Indicatore  |  Crescita  |   Declino leve  |   Declino severo |
|----| ----| ----| ----|
| Numero di comuni  |  2.209   |   618  |   1.268 |
| Rischio frana (% area media)   |  5,73%  |   8,86%  |   9,79% |
| Rischio alluvione (% area media)   |  6,27%  |   6,54%  |   5,11% |
| Comuni montani   |  34,0%  |  46,0%   |  59,6% |
| Altitudine media   |  398,0 m  |   465,5 m   |   640,2 m |
| Indice di accessibilità (media)   | 45.560   |   24.775  |   17.537 |
| Tempo dall'hub più vicino    | 18,1 min   |   23,9 min  |   30,6 min |
| Andamento prezzo abitazioni   | +1,51%/anno   |   +0,31%/anno  |   −0,08%/anno |


**Crescita** — Migliore connettività, minore esposizione al rischio geologico, situato prevalentemente in zone di pianura. Il mercato immobiliare più dinamico dei tre gruppi.

**Declino leve** — Una fase intermedia di declino, con un profilo geografico anch'esso intermedio tra crescita e declino severo. Il mercato immobiliare mostra ancora una lieve crescita, ma nettamente più debole.

**Declino severo** — L'altitudine media maggiore, la più alta proporzione di territorio montano, il rischio frana più elevato e la peggiore accessibilità. L'unico gruppo con il mercato immobiliare stagnante, coerente con un processo di spopolamento strutturale.

---

### Un ritratto dell'Italia intera: tutti i comuni, 2023-2025


<div id="p1"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p1', '{{ site.baseurl }}/assets/charts/1_confronto_Andalo_Cavedago.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


<div id="p2"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p2', '{{ site.baseurl }}/assets/charts/2_mappa_clusterk8_Leo.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

<div id="p3"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p3', '{{ site.baseurl }}/assets/charts/3_demografia_vecchiaia_natalita_per_cluster.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

<div id="p4"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p4', '{{ site.baseurl }}/assets/charts/4_Indicatori_clusterk8_italia_leo.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


<div id="p5"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p5', '{{ site.baseurl }}/assets/charts/5_Shap_clusterk8_italia_leo.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


<div id="p6"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#p6', '{{ site.baseurl }}/assets/charts/6_metriche_clusterK8_Leo.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>
---  

### I piccoli comuni d'Italia: profili a confronto


<div id="clusterItaliaGinevra"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#clusterItaliaGinevra', '{{ site.baseurl }}/assets/charts/clustering_italia.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Interpretazione dei cluster  


<style>
  .grid-cluster {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    margin: 20px 0;
  }
  .card-cluster {
    background: #faf8f2;
    border: 1px solid rgba(0, 0, 0, 0.08);
    border-radius: 8px;
    padding: 20px;
  }
  .card-cluster h5 {
    color: #6b5a3f;
    margin-top: 0;
    border-bottom: 2px solid #6b5a3f;
    padding-bottom: 8px;
  }
  .card-cluster ul {
    padding-left: 18px;
    margin-bottom: 12px;
  }
  .card-cluster p {
    font-style: italic;
    font-size: 0.95em;
    color: #555;
  }
</style>

<div class="grid-cluster">

  <div class="card-cluster">
    <h5>Gruppo 0 – Comuni accessibili</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 1.653</li>
      <li><strong>Altitudine media:</strong> 1,58</li>
      <li><strong>Tempo al primo hub (&gt;15.000 ab.):</strong> 18 min</li>
      <li><strong>Popolazione raggiungibile in 40 min:</strong> ~469.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 11</li>
      <li><strong>Prezzo medio:</strong> 739 €</li>
      <li><strong>Crescita dal 1992:</strong> stabile (−1%)</li>
      <li><strong>Delta frizione:</strong> 3,1 (rete stradale efficiente)</li>
    </ul>
    <p>Buona accessibilità e infrastrutture viarie relativamente efficienti. La presenza turistica è contenuta e i prezzi immobiliari sono bassi, suggerendo territori periferici ma ben collegati.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 1 – Destinazioni turistiche</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 144</li>
      <li><strong>Altitudine media:</strong> 2,83</li>
      <li><strong>Tempo al primo hub:</strong> 37 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~206.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 163</li>
      <li><strong>Prezzo medio:</strong> 2.873 €</li>
      <li><strong>Crescita dal 1992:</strong> stabile</li>
      <li><strong>Delta frizione:</strong> 11,8 (viabilità difficoltosa)</li>
    </ul>
    <p>Località montane con forte vocazione turistica. Pur essendo relativamente isolate e servite da una rete stradale meno efficiente, registrano prezzi immobiliari molto elevati e un'elevata concentrazione di strutture ricettive.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 2 – Comuni periferici</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 1.374</li>
      <li><strong>Altitudine media:</strong> 2,79 (montana)</li>
      <li><strong>Tempo al primo hub:</strong> 34 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~147.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 9</li>
      <li><strong>Prezzo medio:</strong> 631 €</li>
      <li><strong>Crescita dal 1992:</strong> −23%</li>
      <li><strong>Delta frizione:</strong> 6,6</li>
    </ul>
    <p>Territori montani periferici, con scarsa dotazione turistica e valori immobiliari bassi. La marcata diminuzione della popolazione suggerisce aree soggette a spopolamento.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 3 – Poli urbani</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 2</li>
      <li><strong>Altitudine media:</strong> 1,00 (pianura)</li>
      <li><strong>Tempo al primo hub:</strong> 31 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~222.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 4.649</li>
      <li><strong>Prezzo medio:</strong> 2.218 €</li>
      <li><strong>Crescita dal 1992:</strong> +10%</li>
      <li><strong>Delta frizione:</strong> 2,7 (rete molto efficiente)</li>
    </ul>
    <p>I principali centri urbani, caratterizzati dalla maggiore concentrazione di strutture ricettive, prezzi immobiliari elevati e buona qualità della rete stradale. La crescita demografica positiva conferma la loro attrattività.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 4 – Comuni periurbani in crescita</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 524</li>
      <li><strong>Altitudine media:</strong> 1,26 (pianura)</li>
      <li><strong>Tempo al primo hub:</strong> 12 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~1,79 milioni di abitanti</li>
      <li><strong>Strutture ricettive:</strong> 6</li>
      <li><strong>Prezzo medio:</strong> 1.191 €</li>
      <li><strong>Crescita dal 1992:</strong> +29%</li>
      <li><strong>Delta frizione:</strong> 8,3</li>
    </ul>
    <p>La maggiore accessibilità potenziale grazie alla vicinanza ai grandi poli urbani. Nonostante la scarsa presenza di strutture ricettive, mostra una forte crescita demografica, probabilmente legata a fenomeni di suburbanizzazione.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 5 – Comuni in espansione</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 891</li>
      <li><strong>Altitudine media:</strong> 2,02 (collina)</li>
      <li><strong>Tempo al primo hub:</strong> 18 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~520.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 18</li>
      <li><strong>Prezzo medio:</strong> 1.214 €</li>
      <li><strong>Crescita dal 1992:</strong> +32%</li>
      <li><strong>Delta frizione:</strong> 8,4</li>
    </ul>
    <p>Territori collinari con buona accessibilità e forte crescita demografica. Il mercato immobiliare è intermedio e la presenza turistica è moderata, indicando aree in fase di sviluppo residenziale e turistico.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 6 – Comuni isolati in declino</h5>
    <ul>
      <li><strong>Numero di comuni:</strong> 607</li>
      <li><strong>Altitudine media:</strong> 3,48 (montana)</li>
      <li><strong>Tempo al primo hub:</strong> 48 min</li>
      <li><strong>Popolazione raggiungibile:</strong> ~82.000 abitanti</li>
      <li><strong>Strutture ricettive:</strong> 17</li>
      <li><strong>Prezzo medio:</strong> 858 €</li>
      <li><strong>Crescita dal 1992:</strong> −16%</li>
      <li><strong>Delta frizione:</strong> 14,8 (rete stradale più penalizzante)</li>
    </ul>
    <p>Le aree più isolate del campione, con la minore accessibilità e la peggiore qualità della rete stradale. Nonostante una certa presenza di strutture ricettive, i prezzi immobiliari rimangono contenuti e la dinamica demografica è negativa.</p>
  </div>

</div>

---
#### Cosa spiega lo spopolamento nei piccoli comuni?
 

<div id="feature_imp_ginevra_it"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_it', '{{ site.baseurl }}/assets/charts/feature_importance_it.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


#### Prestazioni del Modello

**Accuracy:** 72%<br>
**Precision:** classe 0 - 75%; classe 1 - 68%<br>
**Recall:** classe 0 - 74%; classe 1 - 70%<br>

---

### I comuni alpini: profili a confronto
Clustering (K-means) sui comuni Alpini  + Modello classificatorio (Random Forest)

<style>
  .grid-cluster {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    margin: 20px 0;
  }
  .card-cluster {
    background: #faf8f2;
    border: 1px solid rgba(0, 0, 0, 0.08);
    border-radius: 8px;
    padding: 20px;
  }
  .card-cluster h5 {
    color: #6b5a3f;  /* tono tierra, coherente con tu paleta */
    margin-top: 0;
    border-bottom: 2px solid #6b5a3f;
    padding-bottom: 8px;
  }
  .card-cluster ul {
    padding-left: 18px;
    margin-bottom: 12px;
  }
  .card-cluster p {
    font-style: italic;
    font-size: 0.95em;
    color: #555;
  }
</style>

<div class="grid-cluster">

  <div class="card-cluster">
    <h5>Gruppo 0 – Piccole località montane periferiche</h5>
    <ul>
      <li><strong>Comuni:</strong> 164</li>
      <li><strong>Accessibilità:</strong> ridotta (41 min dal primo hub)</li>
      <li><strong>Strutture ricettive:</strong> poche (14 in media)</li>
      <li><strong>Prezzi immobiliari:</strong> contenuti</li>
      <li><strong>Demografia:</strong> calo marcato (−17% dal 1992)</li>
      <li><strong>Abitazioni non occupate:</strong> elevata</li>
    </ul>
    <p>Piccole destinazioni montane periferiche, con offerta turistica limitata e progressivo indebolimento demografico.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 1 – Montagna accessibile e residenziale</h5>
    <ul>
      <li><strong>Comuni:</strong> 94</li>
      <li><strong>Accessibilità:</strong> buona (21 min dal primo hub)</li>
      <li><strong>Prezzi immobiliari:</strong> medio-alto</li>
      <li><strong>Demografia:</strong> crescita positiva (+16%)</li>
      <li><strong>Abitazioni non occupate:</strong> bassa</li>
    </ul>
    <p>Comuni facilmente raggiungibili con funzione residenziale e turistica, che beneficiano della vicinanza ai centri urbani.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 2 – Montagna isolata con criticità infrastrutturali</h5>
    <ul>
      <li><strong>Comuni:</strong> 126</li>
      <li><strong>Accessibilità:</strong> molto bassa (53 min dal primo hub)</li>
      <li><strong>Delta frizione:</strong> elevato</li>
      <li><strong>Prezzi immobiliari:</strong> relativamente bassi</li>
      <li><strong>Demografia:</strong> calo moderato</li>
      <li><strong>Turismo:</strong> limitato</li>
    </ul>
    <p>Territori montani isolati, penalizzati dalle condizioni infrastrutturali e dalla distanza dai poli principali.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 3 – Località montane in trasformazione</h5>
    <ul>
      <li><strong>Comuni:</strong> 205</li>
      <li><strong>Accessibilità:</strong> intermedia</li>
      <li><strong>Strutture ricettive:</strong> ridotta</li>
      <li><strong>Prezzi immobiliari:</strong> contenuti</li>
      <li><strong>Demografia:</strong> sostanzialmente stabile</li>
      <li><strong>Perdite di innevamento:</strong> bassa</li>
    </ul>
    <p>Località montane meno elevate, dove la diminuzione dell'innevamento potrebbe incidere sulla competitività del turismo invernale.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 4 – Destinazioni sciistiche di pregio</h5>
    <ul>
      <li><strong>Comuni:</strong> 37</li>
      <li><strong>Accessibilità:</strong> limitata, compensata dall'attrattività</li>
      <li><strong>Quota altimetrica:</strong> molto elevata</li>
      <li><strong>Strutture ricettive:</strong> molto sviluppata (75 in media)</li>
      <li><strong>Prezzi immobiliari:</strong> elevati</li>
      <li><strong>Perdite di innevamento:</strong> relativamente contenute</li>
    </ul>
    <p>Principali destinazioni sciistiche, con mercato immobiliare di valore elevato e offerta turistica consolidata.</p>
  </div>

  <div class="card-cluster">
    <h5>Gruppo 5 – Grandi poli dello sci</h5>
    <ul>
      <li><strong>Comuni:</strong> 11</li>
      <li><strong>Accessibilità:</strong> comuni molto isolati</li>
      <li><strong>Strutture ricettive:</strong> oltre 440 in media</li>
      <li><strong>Prezzi immobiliari:</strong> molto elevati</li>
      <li><strong>Presenza seconde case:</strong> elevata</li>
    </ul>
    <p>Grandi comprensori sciistici nazionali. Nonostante l'isolamento, l'elevata specializzazione turistica sostiene un'importante offerta ricettiva.</p>
  </div>

</div>


---

`Clustering sui comuni Alpini su features (LEO??)` 
plot feature importance SHAP

---

#### Cosa spiega lo spopolamento nei comuni alpini?


<div id="feature_imp_ginevra_montani"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#feature_imp_ginevra_montani', '{{ site.baseurl }}/assets/charts/fi_montano.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>

#### Prestazioni del Modello

**Accuracy:** 76%<br>
**Precision:** classe 0 - 76%; classe 1 - 76%<br>
**Recall:** classe 0 - 64%; classe 1 - 85%<br>

---

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