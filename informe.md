<style>
/* Estils globals del document */
body {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 9pt;
  text-align: justify;
  line-height: 1.4;
}

/* Paràgrafs justificats */
p {
  text-align: justify;
  font-size: 9pt;
}

/* Estils per a les llistes amb la mateixa mida que el text normal */
ul, ol, code {
  font-size: 9pt;
  line-height: 1.4;
}

li {
  font-size: 9pt;
  line-height: 1.4;
}

/* Títols més petits */
h1 {
  font-size: 13pt;
  text-align: left;
}

h2 {
  font-size: 12pt;
  text-align: left;
  font-weight: bold;
}

h3 {
  font-size: 11pt;
  text-align: left;
  font-weight: bold;
}

h4 {
  font-size: 9pt;
  text-align: left;
}

h5{
  font-size: 9pt;
  text-align: left;
  text-decoration: underline;
}

/* CORRECCIONS PER A BLOCS DE CODI */
pre {
  max-width: 100%;
  overflow-x: auto;
  white-space: pre-wrap;
  word-wrap: break-word;
  overflow-wrap: break-word;
  background-color: #f5f5f5;
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 3px;
  font-size: 8pt;
  line-height: 1.4;
  min-width: 0;
}

code {
  font-size: 8pt;
  overflow-wrap: break-word;
  word-wrap: break-word;
  word-break: break-word;
  white-space: pre-wrap;
  font-style: monospace;
}

/* Contenidor principal */
.image-row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;       /* Espai entre imatges */
  margin-top: 1rem;
  margin-bottom: 1rem;
  align-items: flex-start;
  width: 100%;
}

/* MODIFICAT: Reduïm la base (flex-basis) a 180px perquè hi capiguin 3 en una fila */
.image-column {
  flex: 1 1 180px; /* Abans 280px. Amb 180px, 3 imatges sumen ~540px + marges, que hi cap perfecte */
  max-width: 320px; /* Mida màxima per evitar que es facin gegants si n'hi ha poques */
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: border-box;
}

/* Regla específica: Si només hi ha UNA imatge, la deixem ser més gran */
.image-row:has(.image-column:only-child) .image-column {
  max-width: 480px;
  flex: 0 1 auto;
}

/* Imatges */
.image-column img {
  width: 100%;
  max-height: 280px; /* Limitem l'alçada */
  height: auto;
  display: block;
  object-fit: contain;
}

/* Peu de foto */
.image-column .caption {
  margin-top: 0.5rem;
  font-size: 8pt;
  text-align: center;
  color: #555;
  width: 100%;
}

/* ============================================
    CONTENIDOR GRID 2x2 PER A IMATGES
    ============================================ */
.image-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.8rem;
  margin-top: 1rem;
  margin-bottom: 1rem;
  width: 100%;
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;
}

/* Cada cel·la del grid */
.image-grid .grid-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: border-box;
}

/* Imatges dins del grid 2x2 */
.image-grid .grid-item img {
  width: 100%;
  max-width: 360px;
  max-height: 320px;
  height: auto;
  display: block;
  object-fit: contain;
}

/* Peu de foto per a cada imatge del grid */
.image-grid .grid-item .caption {
  margin-top: 0.5rem;
  font-size: 8pt;
  text-align: center;
  color: #555;
  width: 100%;
}

/* Peu de figura general (opcional, per sota de tot el grid) */
.image-grid-caption {
  margin-top: 0.8rem;
  font-size: 8pt;
  text-align: center;
  color: #555;
  font-style: italic;
}

/* Estil per a la separació de pàgines en PDF */
.page-break {
  page-break-before: always;
  break-before: page;
}

/* Bloc imatge-esquerra / text-dreta */
.media-row {
  display: flex;
  gap: 1.5rem;
  align-items: flex-start;
  margin: 1rem 0;
  min-width: 0;
}

.media-image {
  flex: 0 0 38%;
  max-width: 240px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.media-image img {
  width: 100%;
  height: auto;
  display: block;
}

.media-image .caption {
  margin-top: 0.5rem;
  font-size: 8pt;
  text-align: center;
  color: #555;
}

.media-text {
  flex: 1 1 0;
  min-width: 240px;
}

/* ============================================
    CONTENIDOR DE TAULES AMB PEU DE TAULA
    ============================================ */
.table-container {
  width: 100%;
  margin: 1.5rem 0;
  overflow-x: auto;
  page-break-inside: avoid;
}

/* Estils per a les taules */
.table-container table {
  width: 100%;
  max-width: 100%;
  border-collapse: collapse;
  font-size: 7pt;
  margin: 0 auto;
  background-color: #fff;
}

/* Capçalera de taula */
.table-container thead {
  background-color: #e0e0e0;
  font-weight: bold;
}

.table-container th {
  padding: 8px 6px;
  text-align: center;
  border: 1px solid #888;
  font-size: 7pt;
}

/* Files de dades */
.table-container td {
  padding: 6px 5px;
  text-align: center;
  border: 1px solid #aaa;
  font-size: 7pt;
}

.table-container td code {
  font-size: 7pt;
}

/* Files alternades (zebra striping) */
.table-container tbody tr:nth-child(even) {
  background-color: #f5f5f5;
}

/* Peu de taula (caption) */
.table-container .table-caption {
  margin-top: 0.5rem;
  font-size: 8pt;
  text-align: center;
  color: #555;
  font-style: italic;
}

/* Estil alternatiu: caption sobre la taula */
.table-container .table-title {
  margin-bottom: 0.5rem;
  font-size: 9pt;
  text-align: center;
  font-weight: bold;
  color: #333;
}

/* Millores per a impressió/PDF */
@media print {
  .table-container {
    page-break-inside: avoid;
  }

  .table-container table {
    border: 1px solid #000;
  }

  .table-container th,
  .table-container td {
    border: 1px solid #666;
  }

  .image-column {
    page-break-inside: avoid;
  }

  /* Límits més restrictius per a PDF */
  .image-column img {
    max-height: 280px;
  }

  .image-row:has(.image-column:only-child) .image-column img {
    max-height: 360px;
  }

  /* Grid 2x2 en impressió */
  .image-grid {
    page-break-inside: avoid;
  }

  .image-grid .grid-item img {
    max-height: 280px;
  }

  pre {
    page-break-inside: avoid;
    overflow: visible;
    white-space: pre-wrap;
  }
}

@page {
  @bottom-center {
    content: "Pàgina " counter(page) " de " counter(pages);
    font-size: 8pt;
    color: #555;
    font-family: Helvetica, Arial, sans-serif;
  }
}
</style>

## 0. Taula de continguts

- [0. Taula de continguts](#0-taula-de-continguts)
- [1. Introducció](#1-introducció)
- [2. Informació del problema](#2-informació-del-problema)
- [3. Anàlisi exploratori descriptiu](#3-anàlisi-exploratori-descriptiu)
  - [3.1 Anàlisi de les variables](#31-anàlisi-de-les-variables)
  - [3.2 Desbalanceig de la classe objectiu](#32-desbalanceig-de-la-classe-objectiu)
  - [3.3 Valors perduts](#33-valors-perduts)
  - [3.4 *Outliers*](#34-outliers)
  - [3.5 Variables categòriques](#35-variables-categòriques)
  - [3.6 Particionat de les dades](#36-particionat-de-les-dades)
  - [3.7 Estudi de dimensionalitat](#37-estudi-de-dimensionalitat)
- [4. Ajustament de models](#4-ajustament-de-models)
  - [4.1 SVM](#41-svm)
    - [4.1.1 Preprocessament](#411-preprocessament)
    - [4.1.2 Ajustament del model](#412-ajustament-del-model)
    - [4.1.3 Resultat final](#413-resultat-final)
  - [4.2 XGBoost](#42-xgboost)
    - [4.2.1 Preprocessament](#421-preprocessament)
    - [4.2.2 Ajustament del model](#422-ajustament-del-model)
    - [4.2.3 Resultat final](#423-resultat-final)
  - [4.3 Regressió logística personalitzada](#43-regressió-logística-personalitzada)
    - [4.3.1 Preprocessament](#431-preprocessament)
    - [4.3.2 Ajustament del model](#432-ajustament-del-model)
    - [4.3.3 Resultat final](#433-resultat-final)
- [5. Model final](#5-model-final)
- [6. Model Card](#6-model-card)
- [7. Conclusions](#7-conclusions)

<div class="page-break"></div>

## 1. Introducció

## 2. Informació del problema

## 3. Anàlisi exploratori descriptiu

En aquesta secció es presenta l'anàlisi exploratori descriptiu (AED) realitzat sobre el conjunt de dades proporcionat per al problema de predicció clínica. L'objectiu principal d'aquesta anàlisi és comprendre millor les característiques de les dades, identificar possibles problemes com valors perduts o *outliers*, i preparar les dades per a l'ajustament dels models predictius.

### 3.1 Anàlisi de les variables

Observem primer de tot la taula de dades per tenir una visió general de les variables disponibles i la seva tipologia. L'obtenim amb la comanda `df.describe().T`, que ens proporciona estadístiques descriptives per a les variables numèriques i categòriques. El resultat ha estat:

<div class="table-container">
  <table style="border-collapse: collapse; width: 100%;">
    <thead>
      <tr>
        <th style="text-align:left; padding: 3px 5px; border-bottom: 2px solid #ddd;">Variable</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">N</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">Mean (SD)</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">Min</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">25%</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">Median</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">75%</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">Max</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd;">Missing (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Age</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">26.04 (10.01)</td>
        <td style="padding: 2px 5px;">13.00</td>
        <td style="padding: 2px 5px;">19.00</td>
        <td style="padding: 2px 5px;">25.00</td>
        <td style="padding: 2px 5px;">31.00</td>
        <td style="padding: 2px 5px;">64.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Sex (0=F, 1=M)</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.58 (0.49)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">BMI</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">28.11 (5.43)</td>
        <td style="padding: 2px 5px;">15.00</td>
        <td style="padding: 2px 5px;">24.40</td>
        <td style="padding: 2px 5px;">28.00</td>
        <td style="padding: 2px 5px;">31.70</td>
        <td style="padding: 2px 5px;">49.60</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Duration Untreated Psychosis</td>
        <td style="padding: 2px 5px;">8872</td>
        <td style="padding: 2px 5px;">19.22 (19.55)</td>
        <td style="padding: 2px 5px;">0.30</td>
        <td style="padding: 2px 5px;">6.40</td>
        <td style="padding: 2px 5px;">12.50</td>
        <td style="padding: 2px 5px;">24.30</td>
        <td style="padding: 2px 5px;">125.00</td>
        <td style="padding: 2px 5px;">1.42%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Family History</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.12 (0.32)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Initial Response</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">41.84 (30.16)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">10.10</td>
        <td style="padding: 2px 5px;">38.20</td>
        <td style="padding: 2px 5px;">72.30</td>
        <td style="padding: 2px 5px;">100.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Prior Antipsychotics</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.41 (0.67)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">2.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">TRS (Target)</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.32 (0.46)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Lymphocyte count</td>
        <td style="padding: 2px 5px;">7009</td>
        <td style="padding: 2px 5px;">1.80 (0.60)</td>
        <td style="padding: 2px 5px;">0.50</td>
        <td style="padding: 2px 5px;">1.38</td>
        <td style="padding: 2px 5px;">1.80</td>
        <td style="padding: 2px 5px;">2.20</td>
        <td style="padding: 2px 5px;">4.02</td>
        <td style="padding: 2px 5px;">22.12%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Neutrophil count</td>
        <td style="padding: 2px 5px;">7015</td>
        <td style="padding: 2px 5px;">5.01 (1.47)</td>
        <td style="padding: 2px 5px;">1.50</td>
        <td style="padding: 2px 5px;">4.01</td>
        <td style="padding: 2px 5px;">5.02</td>
        <td style="padding: 2px 5px;">6.01</td>
        <td style="padding: 2px 5px;">9.96</td>
        <td style="padding: 2px 5px;">22.06%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Triglycerides</td>
        <td style="padding: 2px 5px;">6547</td>
        <td style="padding: 2px 5px;">152.01 (61.10)</td>
        <td style="padding: 2px 5px;">40.00</td>
        <td style="padding: 2px 5px;">108.05</td>
        <td style="padding: 2px 5px;">151.10</td>
        <td style="padding: 2px 5px;">194.60</td>
        <td style="padding: 2px 5px;">394.60</td>
        <td style="padding: 2px 5px;">27.26%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Glucose</td>
        <td style="padding: 2px 5px;">6381</td>
        <td style="padding: 2px 5px;">95.86 (18.31)</td>
        <td style="padding: 2px 5px;">65.00</td>
        <td style="padding: 2px 5px;">82.20</td>
        <td style="padding: 2px 5px;">95.50</td>
        <td style="padding: 2px 5px;">108.30</td>
        <td style="padding: 2px 5px;">159.60</td>
        <td style="padding: 2px 5px;">29.10%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Alkaline Phosphatase</td>
        <td style="padding: 2px 5px;">6062</td>
        <td style="padding: 2px 5px;">85.17 (24.83)</td>
        <td style="padding: 2px 5px;">30.00</td>
        <td style="padding: 2px 5px;">68.20</td>
        <td style="padding: 2px 5px;">84.70</td>
        <td style="padding: 2px 5px;">101.90</td>
        <td style="padding: 2px 5px;">179.30</td>
        <td style="padding: 2px 5px;">32.64%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">IL-17A</td>
        <td style="padding: 2px 5px;">8999</td>
        <td style="padding: 2px 5px;">2.66 (0.80)</td>
        <td style="padding: 2px 5px;">-0.20</td>
        <td style="padding: 2px 5px;">2.12</td>
        <td style="padding: 2px 5px;">2.65</td>
        <td style="padding: 2px 5px;">3.21</td>
        <td style="padding: 2px 5px;">5.38</td>
        <td style="padding: 2px 5px;">0.01%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">CCL23</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">3.78 (1.05)</td>
        <td style="padding: 2px 5px;">-0.20</td>
        <td style="padding: 2px 5px;">3.08</td>
        <td style="padding: 2px 5px;">3.78</td>
        <td style="padding: 2px 5px;">4.49</td>
        <td style="padding: 2px 5px;">7.69</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">TWEAK</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">4.19 (1.24)</td>
        <td style="padding: 2px 5px;">-0.54</td>
        <td style="padding: 2px 5px;">3.37</td>
        <td style="padding: 2px 5px;">4.19</td>
        <td style="padding: 2px 5px;">5.04</td>
        <td style="padding: 2px 5px;">8.92</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">HLA-DRB1*04:02</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.02 (0.15)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">HLA-B*15:02</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.03 (0.18)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">HLA-A*31:01</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.05 (0.21)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Polygenic Risk Score</td>
        <td style="padding: 2px 5px;">8999</td>
        <td style="padding: 2px 5px;">0.030 (0.14)</td>
        <td style="padding: 2px 5px;">-0.44</td>
        <td style="padding: 2px 5px;">-0.07</td>
        <td style="padding: 2px 5px;">0.02</td>
        <td style="padding: 2px 5px;">0.11</td>
        <td style="padding: 2px 5px;">0.58</td>
        <td style="padding: 2px 5px;">0.01%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Del 22q11.2</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.009 (0.09)</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">0.00</td>
        <td style="padding: 2px 5px;">1.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Ki Whole Striatum</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.0130 (0.002)</td>
        <td style="padding: 2px 5px;">0.0080</td>
        <td style="padding: 2px 5px;">0.0113</td>
        <td style="padding: 2px 5px;">0.0129</td>
        <td style="padding: 2px 5px;">0.0145</td>
        <td style="padding: 2px 5px;">0.0200</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">Ki Associative Striatum</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">0.0130 (0.002)</td>
        <td style="padding: 2px 5px;">0.0071</td>
        <td style="padding: 2px 5px;">0.0113</td>
        <td style="padding: 2px 5px;">0.0128</td>
        <td style="padding: 2px 5px;">0.0146</td>
        <td style="padding: 2px 5px;">0.0210</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">SUVRc Whole Striatum</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">1.18 (0.27)</td>
        <td style="padding: 2px 5px;">0.80</td>
        <td style="padding: 2px 5px;">0.97</td>
        <td style="padding: 2px 5px;">1.16</td>
        <td style="padding: 2px 5px;">1.36</td>
        <td style="padding: 2px 5px;">2.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px;">SUVRc Assoc. Striatum</td>
        <td style="padding: 2px 5px;">9000</td>
        <td style="padding: 2px 5px;">1.18 (0.27)</td>
        <td style="padding: 2px 5px;">0.80</td>
        <td style="padding: 2px 5px;">0.96</td>
        <td style="padding: 2px 5px;">1.16</td>
        <td style="padding: 2px 5px;">1.37</td>
        <td style="padding: 2px 5px;">2.00</td>
        <td style="padding: 2px 5px;">0.00%</td>
      </tr>
    </tbody>
  </table>
  <div class="table-caption">Taula 1: Resum estadístic de totes les variables numèriques i categòriques del conjunt d'entrenament. Es mostra el recompte (N), mitjana i desviació estàndard, quartils i percentatge de valors perduts.</div>
</div>

Obeservem que el conjunt de dades conté un total de 9000 mostres i diverses variables predictives, així com la variable objectiu `TRS (Target)`. Algunes variables presenten valors perduts, especialment les mèdiques com el recompte de limfòcits i neutròfils, triglicèrids, glucosa i fosfatasa alcalina, que gestionarem més endavant a la [secció 3.3](#33-valors-perduts).

Pel que fa les distribucions de les variables, la majoria semblen tenir una distribució aproximadament normal, o de combinacions de normals, com per exemple:

<div class="image-grid">
  <div class="grid-item">
    <img src="images/1.png" alt="Distribució de l'edat">
    <div class="caption">Figura 1: Distribució de <code>Neutrophil count</code>.</div>
  </div>
  <div class="grid-item">
    <img src="images/2.png" alt="Distribució del BMI">
    <div class="caption">Figura 2: Distribució de <code>TWEAK</code>.</div>
  </div>
  <div class="grid-item">
    <img src="images/3.png" alt="Distribució de la resposta inicial">
    <div class="caption">Figura 3: Distribució de <code>Alkaline phosphatase</code></div>
  </div>
  <div class="grid-item">
    <img src="images/4.png" alt="Distribució de la variable objectiu TRS">
    <div class="caption">Figura 4: Distribució de <code>Initial response</code>.</div>
  </div>
</div>

Aquestes variables es poden utilitzar directament en els models predictius, ja que no requereixen transformacions addicionals per a la seva normalització. No obstant això, algunes variables com el `Duration_Untreated_Psychosis` o `Age` mostren una distribució més asimètrica:

<div class="image-row">
  <div class="image-column">
    <img src="images/5.png" alt="Distribució asimètrica de Duration_Untreated_Psychosis">
    <div class="caption">Figura 5: Distribució de <code>Duration_Untreated_Psychosis</code>.</div>
  </div>
  <div class="image-column">
    <img src="images/6.png" alt="Distribució asimètrica de Age">
    <div class="caption">Figura 6: Distribució de <code>Age</code>.</div>
  </div>
</div>

En aquest cas podem veure unes cues llargues cap a la dreta, indicant la presència d'alguns valors extrems. Comprovem ràpidament amb el skewness que aquestes variables no són normals. Si tenen un skewness major a 1 o menor a -1, es consideren altament asimètriques. Comprovem:

```bash
ANÀLISI D'ASIMETRIA (SKEWNESS):
--------------------------------------------------------------------------------
                    Variable  Skewness  Kurtosis                                    Estat
Duration_untreated_psychosis  2.150479  5.323006 🔴 MOLT ASIMÈTRICA (Requereix Log/BoxCox)
                         Age  1.258793  2.065980 🔴 MOLT ASIMÈTRICA (Requereix Log/BoxCox)
  SUVRc_associative_striatum  0.457536 -0.422680                     🟢 NORMAL (Simètrica)
        SUVRc_whole_striatum  0.434121 -0.408815                     🟢 NORMAL (Simètrica)
        Polygenic_risk_score  0.405186  0.323084                     🟢 NORMAL (Simètrica)
     Ki_associative_striatum  0.328552 -0.022675                     🟢 NORMAL (Simètrica)
...
```

Aquest desequilibri en la distribució de les dades pot afectar el rendiment dels models predictius, especialment aquells que assumeixen normalitat en les variables. Per tant, considerarem aplicar transformacions com el logaritme o Box-Cox a aquestes variables abans de l'ajustament dels models.

Mirem la correlació entre les variables numèriques per identificar possibles relacions lineals que puguin ser útils per a la predicció. Utilitzem un mapa de calor per visualitzar aquestes correlacions:

<div class="image-row">
  <div class="image-column">
    <img src="./images/7.png" alt="Matriu de Correlació de Pearson">
    <div class="caption">Figura 7. Matriu de Correlació de Pearson</div>
  </div>
</div>

Veiem que en termes generals, les correlacions entre les variables molt baixes o pràcticament 0, amb algunes excepcions:

Aquesta imatge mostra una **matriu de correlació de Pearson** (heatmap), que mesura la relació lineal entre diferents variables numèriques del teu dataset. Els valors van de **-1** (blau fosc, correlació negativa perfecta) a **+1** (vermell fosc, correlació positiva perfecta), passant per **0** (gris/blanc, sense correlació).

Aquí tens la interpretació detallada dels patrons més rellevants:

1. Redundància a les Variables avall dreta (Vermell Fosc)
   Aquest és el grup més destacat de la gràfica. Les variables relacionades amb l'estriat (*striatum*) mostren correlacions extremadament altes.
   - **``Ki_whole_striatum``** vs. **``Ki_associative_striatum``:** 0.96
   - **``Ki``** vs. **``SUVRc``**: ~0.70 - 0.73

2. Clúster Metabòlic (Vermell Mig):

   - **``Triglycerides``** vs. **``Glucose``**: 0.62
   - **``Glucose``** vs. **``BMI``**: 0.39

3. Relació entre no tratament i resposta inicial (Blau Fosc):
   - **``Duration_untreated_psychosis``** vs. **``Initial_response``**: -0.30

Aquestes correlacions suggereixen que certes variables estan fortament relacionades i podrien ser redundants en els models predictius. Gestionarem aquestes relacions en la fase de selecció de característiques per optimitzar el rendiment dels models.

### 3.2 Desbalanceig de la classe objectiu

La variable objectiu és `TRS`, que indica si un pacient desenvolupa resistència als tractaments antipsicòtics. La proporció de pacients la mirem executant `ratio_trs = df['TRS'].value_counts(normalize=True)`. El resultat és que el percentatge d'individus a la dataset que desenvolupa TRS és aproximadament del 31.5%, mentre que el 68.4% restant no desenvolupa resistència. Això indica un desbalanceig en les classes, que haurem de gestionar a l'hora de modelar. Aquest desbalanceig es denota en les variables categòriques:

<div class="image-row">
  <div class="image-column">
    <img src="images/8.png" alt="Distribució de la variable objectiu TRS">
    <div class="caption">Figura 8: Distribució de la variable objectiu <code>TRS</code> </div>
  </div>
  <div class="image-column">
    <img src="images/9.png" alt="Distribució de la variable categòrica TRS">
    <div class="caption">Figura 9: Distribució de la variable objectiu <code>TRS</code> </div>
  </div>
</div>

Veiem no hi ha cap biaix que provoqui el desbalanceig, ja que la distribució de les altres variables categòriques és força equilibrada. Per tant, per gestionar aquest desbalanceig en la fase d'ajustament dels models, considerarem tècniques com assignar pesos a les classes.

### 3.3 Valors perduts

Com podem veure a la Taula 1, algunes variables tenen un percentatge significatiu de valors perduts. Veiem-ho en més detall:

<div class="table-container">
  <table style="border-collapse: collapse; width: 100%;">
    <thead>
      <tr>
        <th style="text-align:left; padding: 3px 5px; border-bottom: 2px solid #ddd; background-color: #333; color: white;">Variable</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd; background-color: #333; color: white;">Total Missings</th>
        <th style="padding: 3px 5px; border-bottom: 2px solid #ddd; background-color: #333; color: white;">Percentatge (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Alkaline_phosphatase</td>
        <td style="padding: 2px 5px; background-color: #67000d; color: white;">2938</td>
        <td style="padding: 2px 5px; background-color: #67000d; color: white;">32.64%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Glucose</td>
        <td style="padding: 2px 5px; background-color: #a50f15; color: white;">2619</td>
        <td style="padding: 2px 5px; background-color: #a50f15; color: white;">29.10%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Triglycerides</td>
        <td style="padding: 2px 5px; background-color: #cb181d; color: white;">2453</td>
        <td style="padding: 2px 5px; background-color: #cb181d; color: white;">27.26%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Lymphocyte_count</td>
        <td style="padding: 2px 5px; background-color: #ef3b2c; color: white;">1991</td>
        <td style="padding: 2px 5px; background-color: #ef3b2c; color: white;">22.12%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Neutrophil_count</td>
        <td style="padding: 2px 5px; background-color: #fb6a4a; color: white;">1985</td>
        <td style="padding: 2px 5px; background-color: #fb6a4a; color: white;">22.06%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Duration_untreated_psychosis</td>
        <td style="padding: 2px 5px; background-color: #fff5f0; color: black;">128</td>
        <td style="padding: 2px 5px; background-color: #fff5f0; color: black;">1.42%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">Polygenic_risk_score</td>
        <td style="padding: 2px 5px; background-color: #ffffff; color: black;">1</td>
        <td style="padding: 2px 5px; background-color: #ffffff; color: black;">0.01%</td>
      </tr>
      <tr>
        <td style="text-align:left; padding: 2px 5px; background-color: #333; color: #ccc;">IL_17A</td>
        <td style="padding: 2px 5px; background-color: #ffffff; color: black;">1</td>
        <td style="padding: 2px 5px; background-color: #ffffff; color: black;">0.01%</td>
      </tr>
    </tbody>
  </table>
  <div class="table-caption">Taula 2: Heatmap de valors perduts per variable.</div>
</div>

Experimentalment he provat d'imputar els valors perduts amb diferents tècniques, com la mitjana, mediana, KNN i regressió. Després d'avaluar el rendiment dels models amb aquestes diferents imputacions, he observat que la imputació mitjançant KNN amb k=5 ofereix els millors resultats en termes de precisió i robustesa del model. Per tant, he decidit utilitzar aquesta tècnica per gestionar els valors perduts en les variables mèdiques.

### 3.4 *Outliers*

### 3.5 Variables categòriques

### 3.6 Particionat de les dades

### 3.7 Estudi de dimensionalitat

## 4. Ajustament de models

### 4.1 SVM

#### 4.1.1 Preprocessament

#### 4.1.2 Ajustament del model

#### 4.1.3 Resultat final

### 4.2 XGBoost

#### 4.2.1 Preprocessament

#### 4.2.2 Ajustament del model

#### 4.2.3 Resultat final

### 4.3 Regressió logística personalitzada

#### 4.3.1 Preprocessament

#### 4.3.2 Ajustament del model

#### 4.3.3 Resultat final

## 5. Model final

## 6. Model Card

## 7. Conclusions
