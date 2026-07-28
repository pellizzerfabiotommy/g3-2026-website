---
layout: default
title: "Casi Studio"
permalink: /casi-studio/
---

# Alcuni esempi 

Nella sezione **Risultati** abbiamo individuato, attraverso tecniche di machine learning , sette profili territoriali che descrivono le diverse traiettorie dei comuni montani italiani — dai territori resilienti a quelli più vulnerabili. In questa sezione selezioniamo alcuni casi concreti, per raccontare attraverso dati e testimonianze dirette cosa significano queste dinamiche sul territorio.

[← Torna ai Risultati]({{ '/risultati/' | relative_url }})

## Analisi Territoriali

### Area o nome comune

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
<div id="p1"></div>
</div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
vegaEmbed('#p1', '{{ site.baseurl }}/assets/charts/1_confronto_Andalo_Cavedago.json')
    .catch(err => console.error('Errore rendering grafico:', err));
</script>


 ---

...Piazza al serchio - periferici in declino
Cortina – turismo, si spopola di residenti
Ziano di fiemme: turismo, in forte crescita
Cimone: corridoio accessibilità, forte crescita