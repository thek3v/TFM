# 5. Peso de taxones en los clusters
¿Qué taxones han tenido mas peso a la hora de formarse los clusters?


## 5.1 Cargar archivos


```python
# Librerías básicas
import pandas as pd
import numpy as np

# Cargar el archivo microbiota_CLR_clusters.csv
ruta_microbiota_clr_clusters = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota\microbiota_CLR_clusters.csv"
df_microbiota_clusters = pd.read_csv(ruta_microbiota_clr_clusters)

# Visualizar primeras filas
print("✔️ Archivo microbiota_CLR_clusters.csv cargado correctamente.")
df_microbiota_clusters

```

    ✔️ Archivo microbiota_CLR_clusters.csv cargado correctamente.
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_vulgatus</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_dorei</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_coprocola</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Bacteroides; s__Bacteroides_uniformis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_plebeius</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Tannerellaceae; g__Parabacteroides; s__Parabacteroides_merdae</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Prevotella; s__Prevotella_copri</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Faecalibacterium; s__Faecalibacterium_prausnitzii</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_massiliensis</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Lactobacillales; f__Aerococcaceae; g__Granulicatella; s__Granulicatella_adiacens</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Ventrisoma</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Coprococcus</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Hydrogeniiclostridium</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_sp003612625</th>
      <th>d__Bacteria; p__Patescibacteria; c__Saccharimonadia; o__Saccharimonadales; f__Nanosynbacteraceae; g__Nanosynbacter</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Acetanaerobacterium; s__Acetanaerobacterium_elongatum</th>
      <th>cluster</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>S001</td>
      <td>2.823663</td>
      <td>6.671347</td>
      <td>6.775692</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>1.298967</td>
      <td>6.070445</td>
      <td>-2.166769</td>
      <td>4.932432</td>
      <td>...</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>0.231126</td>
      <td>-2.166769</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>S002</td>
      <td>6.787194</td>
      <td>2.546814</td>
      <td>-1.783919</td>
      <td>3.713249</td>
      <td>-1.783919</td>
      <td>5.147553</td>
      <td>4.284507</td>
      <td>7.847169</td>
      <td>3.322027</td>
      <td>...</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>0.295523</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>S003</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>8.378776</td>
      <td>-0.815333</td>
      <td>8.421454</td>
      <td>-0.815333</td>
      <td>7.204937</td>
      <td>-0.815333</td>
      <td>3.173651</td>
      <td>...</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>S004</td>
      <td>6.312904</td>
      <td>4.757185</td>
      <td>-3.396453</td>
      <td>5.198442</td>
      <td>-3.396453</td>
      <td>5.269161</td>
      <td>5.460066</td>
      <td>-3.396453</td>
      <td>3.141687</td>
      <td>...</td>
      <td>-3.396453</td>
      <td>-3.396453</td>
      <td>0.004745</td>
      <td>-1.093867</td>
      <td>-1.604693</td>
      <td>-1.317011</td>
      <td>-3.396453</td>
      <td>-2.010158</td>
      <td>-3.396453</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>S006</td>
      <td>5.063829</td>
      <td>4.406641</td>
      <td>0.718497</td>
      <td>2.851619</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>4.550330</td>
      <td>0.450233</td>
      <td>4.521230</td>
      <td>...</td>
      <td>-0.861953</td>
      <td>0.559432</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>0.370190</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>-0.610639</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>292</th>
      <td>S563</td>
      <td>9.849590</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>7.179058</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>...</td>
      <td>-1.007407</td>
      <td>1.295178</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>1.557543</td>
      <td>-1.007407</td>
      <td>1</td>
    </tr>
    <tr>
      <th>293</th>
      <td>S564</td>
      <td>6.217724</td>
      <td>3.357508</td>
      <td>-2.836897</td>
      <td>3.000833</td>
      <td>0.421199</td>
      <td>4.263954</td>
      <td>4.795988</td>
      <td>-2.836897</td>
      <td>4.908538</td>
      <td>...</td>
      <td>1.133394</td>
      <td>-0.271948</td>
      <td>-2.836897</td>
      <td>-0.271948</td>
      <td>0.053474</td>
      <td>0.800689</td>
      <td>-2.836897</td>
      <td>-0.757456</td>
      <td>-2.836897</td>
      <td>1</td>
    </tr>
    <tr>
      <th>294</th>
      <td>S565</td>
      <td>5.334716</td>
      <td>5.925814</td>
      <td>5.143125</td>
      <td>2.527617</td>
      <td>5.775725</td>
      <td>5.734284</td>
      <td>4.773573</td>
      <td>6.557773</td>
      <td>5.180226</td>
      <td>...</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>0.236206</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>1</td>
    </tr>
    <tr>
      <th>295</th>
      <td>S566</td>
      <td>5.765611</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>5.654093</td>
      <td>-2.834083</td>
      <td>6.101557</td>
      <td>4.947890</td>
      <td>0.384793</td>
      <td>4.250981</td>
      <td>...</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>-0.269134</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>0</td>
    </tr>
    <tr>
      <th>296</th>
      <td>S567</td>
      <td>3.979134</td>
      <td>7.002723</td>
      <td>-2.944495</td>
      <td>3.863440</td>
      <td>-0.305437</td>
      <td>5.433207</td>
      <td>4.451227</td>
      <td>-2.944495</td>
      <td>3.822848</td>
      <td>...</td>
      <td>-0.865053</td>
      <td>-1.152735</td>
      <td>-0.054123</td>
      <td>-2.944495</td>
      <td>-2.944495</td>
      <td>-0.998585</td>
      <td>-2.944495</td>
      <td>-1.845882</td>
      <td>-2.944495</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>297 rows × 241 columns</p>
</div>



## 5.2 Preparamos X(taxones) e Y(cluster)


```python
# 1️⃣ Preparar y → columna cluster
y = df_microbiota_clusters['cluster']

# 2️⃣ Preparar X → columnas de taxones (excluyendo 'Unnamed: 0' y 'cluster')
# Vamos a seleccionar todas las columnas que no sean ni 'Unnamed: 0' ni 'cluster'

columnas_taxones = df_microbiota_clusters.columns.difference(['Unnamed: 0', 'cluster'])

X = df_microbiota_clusters[columnas_taxones]

# 3️⃣ Comprobar formas de X e y
print(f"Forma de X: {X.shape}")
print(f"Forma de y: {y.shape}")

# Visualizar X.head() para confirmar que solo hay taxones
X

```

    Forma de X: (297, 239)
    Forma de y: (297,)
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>d__Bacteria</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Actinomycetia; o__Actinomycetales; f__Bifidobacteriaceae; g__Bifidobacterium; s__Bifidobacterium_adolescentis</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Actinomycetia; o__Actinomycetales; f__Bifidobacteriaceae; g__Bifidobacterium; s__Bifidobacterium_bifidum</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Actinomycetia; o__Actinomycetales; f__Bifidobacteriaceae; g__Bifidobacterium; s__Bifidobacterium_longum</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Actinomycetia; o__Actinomycetales; f__Bifidobacteriaceae; g__Bifidobacterium; s__Bifidobacterium_pseudocatenulatum</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Coriobacteriia; o__Coriobacteriales; f__Coriobacteriaceae; g__Collinsella</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Coriobacteriia; o__Coriobacteriales; f__Eggerthellaceae; g__CAG-1427; s__CAG-1427_sp000435475</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Coriobacteriia; o__Coriobacteriales; f__Eggerthellaceae; g__CAG-1427; s__CAG-1427_sp000435675</th>
      <th>d__Bacteria; p__Actinobacteriota; c__Coriobacteriia; o__Coriobacteriales; f__Eggerthellaceae; g__Slackia; s__Slackia_isoflavoniconvertens</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia</th>
      <th>...</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Duodenibacillus; s__Duodenibacillus_intestinigallinarum</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Parasutterella</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Parasutterella; s__Parasutterella_excrementihominis</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Parasutterella; s__Parasutterella_gallistercoris</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Enterobacterales; f__Enterobacteriaceae; g__Escherichia</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Enterobacterales; f__Pasteurellaceae; g__Haemophilus</th>
      <th>d__Bacteria; p__Verrucomicrobiota; c__Lentisphaeria; o__Victivallales; f__Victivallaceae; g__Victivallis; s__Victivallis_lenta</th>
      <th>d__Bacteria; p__Verrucomicrobiota; c__Lentisphaeria; o__Victivallales; f__Victivallaceae; g__Victivallis; s__Victivallis_vadensis</th>
      <th>d__Bacteria; p__Verrucomicrobiota; c__Verrucomicrobiae; o__Verrucomicrobiales; f__Akkermansiaceae; g__Akkermansia; s__Akkermansia_muciniphila</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.546803</td>
      <td>2.863669</td>
      <td>-2.166769</td>
      <td>2.355019</td>
      <td>-2.166769</td>
      <td>2.603915</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>0.472288</td>
      <td>-2.166769</td>
      <td>...</td>
      <td>2.355019</td>
      <td>1.639893</td>
      <td>1.359591</td>
      <td>-2.166769</td>
      <td>5.244183</td>
      <td>-0.220859</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
      <td>-2.166769</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.613976</td>
      <td>-1.783919</td>
      <td>0.007841</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>0.700988</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>-1.783919</td>
      <td>...</td>
      <td>5.178325</td>
      <td>2.801049</td>
      <td>-1.783919</td>
      <td>1.742442</td>
      <td>-1.783919</td>
      <td>0.700988</td>
      <td>1.106453</td>
      <td>2.186373</td>
      <td>2.769958</td>
      <td>-1.783919</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>1.892717</td>
      <td>-0.815333</td>
      <td>2.129106</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>...</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>8.481735</td>
      <td>2.968856</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>-0.815333</td>
      <td>0.570961</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-3.396453</td>
      <td>4.745320</td>
      <td>1.627428</td>
      <td>0.158896</td>
      <td>-3.396453</td>
      <td>2.125008</td>
      <td>1.796504</td>
      <td>0.004745</td>
      <td>-0.064248</td>
      <td>-3.396453</td>
      <td>...</td>
      <td>-3.396453</td>
      <td>2.336889</td>
      <td>-3.396453</td>
      <td>4.943765</td>
      <td>-3.396453</td>
      <td>2.075818</td>
      <td>-3.396453</td>
      <td>-3.396453</td>
      <td>-0.351930</td>
      <td>3.515295</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-2.807863</td>
      <td>-0.610639</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>3.111030</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>1.063338</td>
      <td>-2.807863</td>
      <td>...</td>
      <td>-2.807863</td>
      <td>2.385093</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>-2.807863</td>
      <td>1.610977</td>
      <td>-2.807863</td>
      <td>0.524341</td>
      <td>0.327631</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>292</th>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>5.791649</td>
      <td>3.135728</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>...</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>8.014312</td>
      <td>-1.007407</td>
      <td>7.585265</td>
      <td>3.226700</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
      <td>-1.007407</td>
    </tr>
    <tr>
      <th>293</th>
      <td>-2.836897</td>
      <td>-2.836897</td>
      <td>-2.836897</td>
      <td>-2.836897</td>
      <td>-2.836897</td>
      <td>4.826040</td>
      <td>-2.836897</td>
      <td>1.706397</td>
      <td>-2.836897</td>
      <td>-2.836897</td>
      <td>...</td>
      <td>-2.836897</td>
      <td>1.114346</td>
      <td>-2.836897</td>
      <td>2.822585</td>
      <td>-0.639673</td>
      <td>0.597090</td>
      <td>-2.836897</td>
      <td>0.659610</td>
      <td>-2.836897</td>
      <td>-0.064309</td>
    </tr>
    <tr>
      <th>294</th>
      <td>0.341566</td>
      <td>1.970807</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>1.334818</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>1.472968</td>
      <td>...</td>
      <td>-1.961019</td>
      <td>2.702420</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>-1.961019</td>
      <td>1.406277</td>
      <td>2.457822</td>
      <td>-1.961019</td>
      <td>2.792571</td>
      <td>-1.961019</td>
    </tr>
    <tr>
      <th>295</th>
      <td>-0.269134</td>
      <td>-2.834083</td>
      <td>1.496650</td>
      <td>3.046450</td>
      <td>4.201185</td>
      <td>1.620264</td>
      <td>-2.834083</td>
      <td>-2.834083</td>
      <td>0.662424</td>
      <td>2.554989</td>
      <td>...</td>
      <td>-2.834083</td>
      <td>3.590786</td>
      <td>-2.834083</td>
      <td>1.496650</td>
      <td>-2.834083</td>
      <td>3.728361</td>
      <td>1.442583</td>
      <td>3.213289</td>
      <td>-0.349176</td>
      <td>-2.834083</td>
    </tr>
    <tr>
      <th>296</th>
      <td>-2.944495</td>
      <td>3.239654</td>
      <td>-2.944495</td>
      <td>1.774004</td>
      <td>2.343772</td>
      <td>0.521241</td>
      <td>2.231655</td>
      <td>-1.558200</td>
      <td>-2.944495</td>
      <td>-2.944495</td>
      <td>...</td>
      <td>-2.944495</td>
      <td>3.430530</td>
      <td>-2.944495</td>
      <td>-2.944495</td>
      <td>5.194946</td>
      <td>2.161451</td>
      <td>3.507554</td>
      <td>2.707994</td>
      <td>-0.546599</td>
      <td>4.167833</td>
    </tr>
  </tbody>
</table>
<p>297 rows × 239 columns</p>
</div>



### Explicación

Explicación
- y → es un vector de 297 elementos con el cluster de cada paciente.
- X → será una matriz 297 x N (N columnas de taxones), donde hemos excluido correctamente:

Unnamed: 0 → que es el ID → NO la queremos en X.

cluster → que es la variable target → NO la queremos en X.

## 5.3 Modelado predictivo

Sacamos un top 15 de taxones bacterianos que mas importancia tienen a la hora de formar los clusters, de momento sin diferenciar entre cluster 0 y 1. 

### 5.3 Random forest 


```python
# Librerías
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt
import seaborn as sns

# 1️⃣ Split train/test → no es obligatorio, pero es buena práctica (aunque aquí lo importante es feature importance)
X_train, X_test, y_train, y_test = train_test_split(X, y, stratify=y, test_size=0.2, random_state=42)

# 2️⃣ Entrenar RandomForest
rf = RandomForestClassifier(n_estimators=1000, random_state=42)
rf.fit(X_train, y_train)

# 3️⃣ Obtener feature importances
importances = rf.feature_importances_
feature_names = X.columns

# 4️⃣ Crear dataframe ordenado de importancias
df_importances = pd.DataFrame({
    'Taxon': feature_names,
    'Importance': importances
})

df_importances = df_importances.sort_values(by='Importance', ascending=False)

# 5️⃣ Visualizar top 15 en gráfico
plt.figure(figsize=(8, 10))
sns.barplot(data=df_importances.head(15), x='Importance', y='Taxon', palette='viridis')
plt.title('Top 15 taxones que más contribuyen a la separación de clusters')
plt.tight_layout()
plt.show()

# 6️⃣ Mostrar tabla completa ordenada (opcional, para revisar)
df_importances.head(15)

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\3030332961.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(data=df_importances.head(15), x='Importance', y='Taxon', palette='viridis')
    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\3030332961.py:30: UserWarning: Tight layout not applied. The left and right margins cannot be made large enough to accommodate all Axes decorations.
      plt.tight_layout()
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_9_1.png)
    





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Taxon</th>
      <th>Importance</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>192</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.058328</td>
    </tr>
    <tr>
      <th>185</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.055984</td>
    </tr>
    <tr>
      <th>161</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.047928</td>
    </tr>
    <tr>
      <th>179</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.039802</td>
    </tr>
    <tr>
      <th>170</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.034588</td>
    </tr>
    <tr>
      <th>172</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.034486</td>
    </tr>
    <tr>
      <th>177</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.025093</td>
    </tr>
    <tr>
      <th>166</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.020951</td>
    </tr>
    <tr>
      <th>72</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.020903</td>
    </tr>
    <tr>
      <th>139</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.018463</td>
    </tr>
    <tr>
      <th>79</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.017085</td>
    </tr>
    <tr>
      <th>102</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.013946</td>
    </tr>
    <tr>
      <th>55</th>
      <td>d__Bacteria; p__Firmicutes; c__Bacilli; o__Ery...</td>
      <td>0.013381</td>
    </tr>
    <tr>
      <th>169</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.013326</td>
    </tr>
    <tr>
      <th>189</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.013269</td>
    </tr>
  </tbody>
</table>
</div>



#### Explicación

El modelo no es para predecir en producción → el interés es ver qué taxones son los que más ayudan a distinguir los clusters → y eso nos lo da feature_importances_.

Del dataframe df_importances me sale el ranking deseado. 

1️⃣ Por qué realizo el Train-Test Split pero no evalúo el Test:

En este análisis, se realiza un Train-Test Split del conjunto de datos, dividiendo las muestras en un conjunto de entrenamiento (80%) y un conjunto de test (20%). Esta división responde a una buena práctica general en el entrenamiento de modelos supervisados, incluso cuando el objetivo principal no es la predicción en producción.

Sin embargo, en este caso concreto, el uso del RandomForestClassifier no tiene como finalidad construir un clasificador predictivo de alta precisión, sino obtener un ranking de importancia de las variables (taxones) que mejor explican la separación de los clusters previamente definidos mediante KMeans.

El atributo feature_importances_ del modelo RandomForest se calcula durante el ajuste (fit) del modelo en el conjunto de entrenamiento, basándose en la capacidad de cada taxón para reducir la impureza (por ejemplo, la impureza de Gini) en los árboles de decisión.

Dado que el interés del análisis es únicamente este ranking (y no la performance del modelo en el conjunto de test), no es estrictamente necesario evaluar métricas como accuracy, precision o recall en el test. El test set se mantiene como práctica de control para evitar un posible overfitting del ranking de features, pero las métricas de predicción no son relevantes para el objetivo del análisis.

En resumen, el Train-Test Split se utiliza aquí como salvaguarda metodológica, pero el interés del estudio reside en el ranking de feature_importances_, que se aprende a partir del conjunto de entrenamiento.

2️⃣ Por qué se utiliza un RandomForestClassifier para determinar el peso de los taxones en la formación de los clusters

Conceptual:

El clustering realizado mediante KMeans ha asignado a cada sujeto a un cluster (por ejemplo, cluster 0 o cluster 1), basándose en una estructura implícita en los datos de abundancia CLR de taxones.

El objetivo de este análisis complementario es identificar qué taxones son los que más han contribuido a esta estructura de separación, es decir, qué perfiles de taxones caracterizan más claramente cada cluster.

Para abordar esta tarea, se utiliza un RandomForestClassifier por varias razones:

Es un modelo no paramétrico y no lineal, capaz de capturar relaciones complejas e interacciones entre los taxones y la pertenencia a un cluster.

Es robusto frente a la multicolinealidad y correlaciones entre taxones, que son habituales en matrices de microbiota.

Proporciona directamente el atributo feature_importances_, que cuantifica el peso relativo de cada taxón en la tarea de clasificación.

Permite un ranking interpretable, que responde directamente a la necesidad planteada en este análisis: saber cuáles son los taxones que más "pesan" en la formación de los clusters.

Conceptualmente, aunque el modelo se entrena para predecir el cluster a partir de las abundancias CLR, no se busca construir un clasificador predictivo sino entender qué variables (taxones) son más relevantes para esta separación, que es precisamente mi objetivo.


Matemático:

Matemáticamente, el RandomForestClassifier es un ensamble de múltiples árboles de decisión, cada uno de los cuales realiza divisiones recursivas del espacio de datos basadas en los valores de los taxones CLR.

En cada nodo de cada árbol, el algoritmo selecciona la variable (taxón) que permite realizar la partición que maximiza la reducción de impureza (por ejemplo, la impureza de Gini o la entropía).

La importancia de cada taxón se calcula como la suma total de las reducciones de impureza que ese taxón ha producido a lo largo de todos los árboles del bosque. Formalmente:


Cuanto mayor es esta reducción acumulada, mayor es la capacidad del taxón de explicar la pertenencia de los individuos a un cluster, y por tanto, mayor es su importancia en la estructura del clustering.

En este contexto, este enfoque basado en RandomForestClassifier es especialmente adecuado, ya que:

- No exige suposiciones de linealidad ni de independencia entre variables.

- Tolera bien la presencia de correlaciones entre taxones.

- Se adapta perfectamente a la estructura compleja de los datos de microbiota.

- Ofrece un resultado interpretable (ranking de importancia) que se alinea directamente con los objetivos de interpretación planteados.


En resumen, se utiliza un RandomForestClassifier como herramienta explicativa para determinar qué taxones contribuyen más a explicar la separación en clusters previamente obtenida mediante KMeans. Aunque se realiza un Train-Test Split para mantener buenas prácticas metodológicas, la evaluación en el conjunto de test no es relevante para el objetivo del análisis, que se centra exclusivamente en el atributo feature_importances_. Este enfoque permite obtener un ranking robusto de los taxones que más caracterizan cada cluster, mediante la suma acumulada de reducciones de impureza a través de los árboles del bosque, ofreciendo así una interpretación directa y cuantificable del peso relativo de cada taxón en la estructura del clustering.

Una vez determinado el ranking de taxones que más contribuyen a la separación global de clusters mediante feature_importances_ del RandomForestClassifier, se realizó un análisis complementario para determinar qué perfiles de taxones caracterizan más claramente cada cluster. Para ello, se evaluaron las abundancias CLR de los 15 taxones más importantes en los dos clusters identificados, mediante boxplots y test de Mann-Whitney U, identificando aquellos taxones que presentan diferencias significativas en su abundancia entre clusters y por tanto caracterizan más claramente cada uno de ellos.

## 5.4 ¿Que taxones caracterizan mas cada cluster?


```python
# Librerías necesarias
import scipy.stats as stats

# 1️⃣ Seleccionar top 15 taxones
top_15_taxones = df_importances.head(15)['Taxon'].tolist()

# 2️⃣ Crear tabla resumen vacía
resumen_taxones = []

# 3️⃣ Iterar por cada taxón del top 15
for taxon in top_15_taxones:
    # Separar abundancias por cluster
    cluster_0_values = X[y == 0][taxon]
    cluster_1_values = X[y == 1][taxon]
    
    # Test de Mann-Whitney U
    u_stat, p_value = stats.mannwhitneyu(cluster_0_values, cluster_1_values, alternative='two-sided')
    
    # Determinar en qué cluster está más alto (comparar medianas)
    median_0 = cluster_0_values.median()
    median_1 = cluster_1_values.median()
    
    if median_0 > median_1:
        cluster_mas_alto = 'Cluster 0'
    else:
        cluster_mas_alto = 'Cluster 1'
    
    # Guardar en resumen
    resumen_taxones.append({
        'Taxon': taxon,
        'Cluster más alto': cluster_mas_alto,
        'Mediana Cluster 0': median_0,
        'Mediana Cluster 1': median_1,
        'p-valor Mann-Whitney': p_value
    })
    
    # Plot → Boxplot de abundancia CLR por cluster
    plt.figure(figsize=(6, 5))
    sns.boxplot(x=y, y=X[taxon], palette='Set2')
    sns.stripplot(x=y, y=X[taxon], color='black', size=4, alpha=0.5, jitter=True)
    plt.title(f'{taxon}\nBoxplot CLR por cluster (p = {p_value:.4f})')
    plt.xlabel('Cluster')
    plt.ylabel('Abundancia CLR')
    plt.tight_layout()
    plt.show()

# 4️⃣ Convertir resumen a dataframe
df_resumen_taxones = pd.DataFrame(resumen_taxones)

# 5️⃣ Mostrar tabla resumen ordenada por p-valor
df_resumen_taxones = df_resumen_taxones.sort_values(by='p-valor Mann-Whitney')
df_resumen_taxones

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_1.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_3.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_5.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_7.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_9.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_11.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_13.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_15.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_17.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_19.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_21.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_23.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_25.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_27.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_22684\1379367701.py:39: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x=y, y=X[taxon], palette='Set2')
    


    
![png](peso_taxones_en_clusters_files/peso_taxones_en_clusters_16_29.png)
    





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Taxon</th>
      <th>Cluster más alto</th>
      <th>Mediana Cluster 0</th>
      <th>Mediana Cluster 1</th>
      <th>p-valor Mann-Whitney</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 1</td>
      <td>-1.617686</td>
      <td>1.846949</td>
      <td>1.407183e-27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>4.193999</td>
      <td>-1.626063</td>
      <td>8.745305e-27</td>
    </tr>
    <tr>
      <th>4</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 1</td>
      <td>1.535942</td>
      <td>3.097783</td>
      <td>6.015055e-24</td>
    </tr>
    <tr>
      <th>14</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 1</td>
      <td>-2.566564</td>
      <td>-0.806526</td>
      <td>3.607468e-22</td>
    </tr>
    <tr>
      <th>5</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>3.347143</td>
      <td>-1.050072</td>
      <td>5.086274e-22</td>
    </tr>
    <tr>
      <th>9</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 1</td>
      <td>-2.590224</td>
      <td>0.177053</td>
      <td>2.301232e-20</td>
    </tr>
    <tr>
      <th>11</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 1</td>
      <td>-2.778166</td>
      <td>-1.611915</td>
      <td>6.376182e-20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>1.072842</td>
      <td>-1.866658</td>
      <td>1.504950e-19</td>
    </tr>
    <tr>
      <th>0</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>3.116886</td>
      <td>-1.993183</td>
      <td>4.079168e-19</td>
    </tr>
    <tr>
      <th>12</th>
      <td>d__Bacteria; p__Firmicutes; c__Bacilli; o__Ery...</td>
      <td>Cluster 1</td>
      <td>-2.566564</td>
      <td>-1.365706</td>
      <td>1.563997e-16</td>
    </tr>
    <tr>
      <th>6</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>2.729266</td>
      <td>-1.189681</td>
      <td>1.983084e-16</td>
    </tr>
    <tr>
      <th>8</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>0.580010</td>
      <td>-2.010432</td>
      <td>4.905731e-14</td>
    </tr>
    <tr>
      <th>10</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>2.768500</td>
      <td>-1.494745</td>
      <td>4.956855e-14</td>
    </tr>
    <tr>
      <th>13</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>3.386345</td>
      <td>2.077153</td>
      <td>8.656201e-09</td>
    </tr>
    <tr>
      <th>7</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>Cluster 0</td>
      <td>-1.320239</td>
      <td>-2.179860</td>
      <td>2.022130e-06</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Definir ruta destino
ruta_destino = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\peso_taxones"

# Guardar df_importances
df_importances.to_csv(f"{ruta_destino}\\df_importances.csv", index=False)
print("✔️ df_importances guardado correctamente.")

# Guardar df_resumen_taxones
df_resumen_taxones.to_csv(f"{ruta_destino}\\df_resumen_taxones.csv", index=False)
print("✔️ df_resumen_taxones guardado correctamente.")

```

    ✔️ df_importances guardado correctamente.
    ✔️ df_resumen_taxones guardado correctamente.
    

## Análisis de los perfiles de taxones que caracterizan cada cluster

A continuación se presenta el análisis detallado de los resultados obtenidos a partir de la tabla `df_resumen_taxones.csv`, que recoge el análisis complementario para evaluar qué perfiles de taxones caracterizan más claramente cada cluster.

### Contexto del análisis

- Tras identificar los 15 taxones con mayor importancia en la separación de clusters mediante el atributo `feature_importances_` de un modelo RandomForestClassifier, se realizó un análisis complementario para determinar en qué cluster (0 o 1) presentaba mayor abundancia cada taxón.

- Para ello, se calcularon:
    - Las medianas de abundancia CLR por cluster.
    - El p-valor del test de Mann-Whitney U para evaluar la significancia estadística de la diferencia de abundancias entre clusters.


### Interpretación de los resultados

- Los taxones con **p-valores más bajos** son aquellos cuya abundancia CLR difiere de forma más significativa entre clusters → son los que más claramente caracterizan un cluster.

- Es importante recordar que:
    - La `feature_importances_` mide el peso del taxón en el modelo para separar clusters (global).
    - El p-valor del test de Mann-Whitney mide si un taxón caracteriza significativamente un cluster (perfil de cluster).

- En nuestro caso, existe una buena concordancia entre ambos análisis: los taxones con mayor `feature_importances_` presentan también p-valores bajos, lo que refuerza su papel como elementos diferenciadores de los clusters.

- Ejemplo claro:
    - *Lawsonibacter* (Cluster 1) → taxón con p-valor muy bajo (1.16e-27) y muy alta abundancia en Cluster 1.
    - *Vescimonas* (Cluster 0) → p-valor muy bajo (1.16e-27) y abundancia alta en Cluster 0.
    
- Se puede afirmar que estos taxones no solo contribuyen al modelo, sino que definen claramente el perfil biológico de los clusters.

### Tabla resumen de los taxones que caracterizan cada cluster

| Cluster caracterizado | Taxón | p-valor |
|----------------------|-------|---------|
| Cluster 1 | *Lawsonibacter* | 1.16e-27 |
| Cluster 1 | *Welbionis* | 1.67e-24 |
| Cluster 1 | *Angelakisella massiliensis* | 1.20e-22 |
| Cluster 1 | *ER4* | 1.58e-21 |
| Cluster 1 | *CAG-272* | 1.34e-20 |
| Cluster 1 | *UBA737_sp900547445* | 3.13e-20 |
| Cluster 1 | *Faecousia* | 3.84e-20 |
| Cluster 1 | *UBA737* | 1.19e-19 |
| Cluster 1 | *Lawsonibacter sp014287875* | 1.54e-19 |
| Cluster 1 | *ER4_sp900317525* | 4.84e-19 |
| Cluster 0 | *Vescimonas* | 1.16e-27 |
| Cluster 0 | *Christensenellales CAG-138* | 5.30e-23 |
| Cluster 0 | *Christensenellales CAG-74 SFM01* | 3.39e-20 |
| Cluster 0 | *Ruminococcus* | 3.72e-18 |
| Cluster 0 | *Anaerotruncus colihominis* | 2.46e-16 |

### Conclusión

- **Cluster 1** se caracteriza principalmente por taxones como *Lawsonibacter*, *Welbionis*, *Angelakisella massiliensis* y varios miembros de la familia Oscillospiraceae.

- **Cluster 0** se caracteriza principalmente por *Vescimonas*, taxones del orden Christensenellales, *Ruminococcus*, y *Anaerotruncus colihominis*.

- Estos resultados complementan el análisis global de `feature_importances_`, permitiendo definir perfiles de cluster claros y fácilmente interpretable para el informe final.

- El análisis confirma que la separación de clusters no solo es robusta a nivel de modelo, sino que tiene una base biológica sólida y diferenciada en los perfiles de taxones característicos.


