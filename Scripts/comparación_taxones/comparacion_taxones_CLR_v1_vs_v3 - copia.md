# 4. Comparación taxones CLR V1 vs V3

## 4.1 Cargar archivos


```python
import pandas as pd
import os

# Ruta base
ruta = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota"

# Cargar microbiota_CLR (V1)
microbiota_CLR_path = os.path.join(ruta, "microbiota_CLR.csv")
microbiota_CLR = pd.read_csv(microbiota_CLR_path, index_col=0)
print("✔️ microbiota_CLR cargado:", microbiota_CLR.shape)

# Cargar microbiota_CLR_v3 (V3)
microbiota_CLR_v3_path = os.path.join(ruta, "microbiota_CLR_v3.csv")
microbiota_CLR_v3 = pd.read_csv(microbiota_CLR_v3_path, index_col=0)
print("✔️ microbiota_CLR_v3 cargado:", microbiota_CLR_v3.shape)

# Vista previa
microbiota_CLR
microbiota_CLR_v3


```

    ✔️ microbiota_CLR cargado: (297, 239)
    ✔️ microbiota_CLR_v3 cargado: (202, 226)
    




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
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_vulgatus</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_dorei</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_coprocola</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Bacteroides; s__Bacteroides_uniformis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_plebeius</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Tannerellaceae; g__Parabacteroides; s__Parabacteroides_merdae</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Prevotella; s__Prevotella_copri</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Faecalibacterium; s__Faecalibacterium_prausnitzii</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Agathobacter; s__Agathobacter_rectalis</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Peptostreptococcales; f__Anaerovoracaceae; g__Copromorpha; s__Copromorpha_sp900066305</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Erysipelotrichales; f__Erysipelotrichaceae; g__Dielma; s__Dielma_fastidiosa</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Acutalibacter</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Erysipelotrichales; f__Erysipelotrichaceae; g__Holdemania; s__Holdemania_sp900120005</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Phocea; s__Phocea_massiliensis</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_massiliensis</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Lactobacillales; f__Aerococcaceae; g__Granulicatella; s__Granulicatella_adiacens</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_sp003612625</th>
      <th>d__Bacteria; p__Patescibacteria; c__Saccharimonadia; o__Saccharimonadales; f__Nanosynbacteraceae; g__Nanosynbacter</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>3.631090</td>
      <td>6.719720</td>
      <td>6.410756</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>5.399860</td>
      <td>-1.251711</td>
      <td>3.895783</td>
      <td>5.472121</td>
      <td>...</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>1.744021</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>6.325070</td>
      <td>3.163727</td>
      <td>-1.313610</td>
      <td>2.711742</td>
      <td>-1.313610</td>
      <td>4.832719</td>
      <td>4.057028</td>
      <td>7.123457</td>
      <td>4.098036</td>
      <td>-1.313610</td>
      <td>...</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>0.632300</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>7.221278</td>
      <td>-1.621182</td>
      <td>7.960860</td>
      <td>1.017875</td>
      <td>7.808695</td>
      <td>-1.621182</td>
      <td>7.083320</td>
      <td>7.037858</td>
      <td>...</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>2.473162</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>3.725925</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>0.576042</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>6.445037</td>
      <td>4.675779</td>
      <td>-0.201959</td>
      <td>4.621543</td>
      <td>-2.910010</td>
      <td>4.995432</td>
      <td>4.883165</td>
      <td>0.385827</td>
      <td>5.152108</td>
      <td>4.339916</td>
      <td>...</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-1.118250</td>
      <td>-0.830568</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-1.118250</td>
      <td>-2.910010</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>4.719755</td>
      <td>3.724005</td>
      <td>1.895328</td>
      <td>2.194483</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>4.014360</td>
      <td>0.205848</td>
      <td>4.993339</td>
      <td>3.804681</td>
      <td>...</td>
      <td>-0.812722</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-0.812722</td>
      <td>-1.298230</td>
      <td>-0.199618</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-0.081834</td>
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
      <th>S308</th>
      <td>7.467611</td>
      <td>5.355384</td>
      <td>-2.784348</td>
      <td>5.984382</td>
      <td>-0.011760</td>
      <td>5.127342</td>
      <td>5.507699</td>
      <td>0.106024</td>
      <td>3.743610</td>
      <td>5.115176</td>
      <td>...</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>0.473748</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>2.898197</td>
      <td>5.767664</td>
      <td>-2.578266</td>
      <td>4.328488</td>
      <td>7.312491</td>
      <td>4.692047</td>
      <td>4.334477</td>
      <td>-2.578266</td>
      <td>3.515303</td>
      <td>3.740702</td>
      <td>...</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-0.968828</td>
      <td>-2.578266</td>
      <td>0.417466</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>5.091319</td>
      <td>1.346606</td>
      <td>5.407857</td>
      <td>4.458036</td>
      <td>6.681813</td>
      <td>3.504888</td>
      <td>-2.812277</td>
      <td>0.519928</td>
      <td>5.520993</td>
      <td>4.853945</td>
      <td>...</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
      <td>-1.425983</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
      <td>-0.104227</td>
      <td>-2.812277</td>
      <td>-0.247328</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>6.299240</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>3.282566</td>
      <td>-3.264219</td>
      <td>4.140668</td>
      <td>2.111059</td>
      <td>-3.264219</td>
      <td>3.302453</td>
      <td>5.330860</td>
      <td>...</td>
      <td>-0.128725</td>
      <td>2.280958</td>
      <td>1.300129</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-0.699270</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-1.318309</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>4.223714</td>
      <td>6.067820</td>
      <td>-2.886982</td>
      <td>6.665457</td>
      <td>-0.584397</td>
      <td>1.495044</td>
      <td>6.029255</td>
      <td>0.408855</td>
      <td>4.949387</td>
      <td>2.025673</td>
      <td>...</td>
      <td>-2.886982</td>
      <td>-0.941072</td>
      <td>-2.886982</td>
      <td>-2.886982</td>
      <td>0.057457</td>
      <td>-0.807541</td>
      <td>-2.886982</td>
      <td>-0.402076</td>
      <td>-0.941072</td>
      <td>-2.886982</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 226 columns</p>
</div>



### 4.1.2 Cargar los taxones diferenciales


```python
# Ruta al archivo con los resultados de FDR en V1
ruta_resultados = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\tablas_pvalores\v1"
archivo_taxones = os.path.join(ruta_resultados, "df_resultados_pvalor1_microbiota_fdr.csv")

# Cargar tabla de resultados
df_resultados_pvalor1_microbiota_fdr = pd.read_csv(archivo_taxones)
print("✔️ Resultados cargados:", df_resultados_pvalor1_microbiota_fdr.shape)

# Filtrar taxones con FDR significativo
taxones_135 = df_resultados_pvalor1_microbiota_fdr[
    df_resultados_pvalor1_microbiota_fdr["p_adj"] < 0.05
]["variable"].tolist()

print(f"✔️ Se han identificado {len(taxones_135)} taxones diferenciales con FDR < 0.05")

```

    ✔️ Resultados cargados: (239, 8)
    ✔️ Se han identificado 135 taxones diferenciales con FDR < 0.05
    

## 4.2 Filtrar matrices y alinear por pacientes

Este bloque:

Se asegura de trabajar solo con taxones válidos en ambas matrices, hay algunos taxones en v1 que probablemente no estén en v3 y por eso me daba key erro. De esta manera:

- Conserva la lógica original del paso 3

- Y previene el KeyError


```python
# Filtrar taxones que están presentes en ambas matrices
columnas_comunes = list(set(taxones_135) & set(microbiota_CLR.columns) & set(microbiota_CLR_v3.columns))

print(f"✔️ {len(columnas_comunes)} taxones están presentes en ambas matrices CLR")

# Filtrar matrices solo con esos taxones
microbiota_CLR_135 = microbiota_CLR[columnas_comunes]
microbiota_CLR_v3_135 = microbiota_CLR_v3[columnas_comunes]

# Alinear por pacientes comunes
ids_comunes = microbiota_CLR_135.index.intersection(microbiota_CLR_v3_135.index)
microbiota_CLR_135 = microbiota_CLR_135.loc[ids_comunes]
microbiota_CLR_v3_135 = microbiota_CLR_v3_135.loc[ids_comunes]

print("✔️ Matriz V1 filtrada:", microbiota_CLR_135.shape)
print("✔️ Matriz V3 filtrada:", microbiota_CLR_v3_135.shape)

microbiota_CLR_v3
```

    ✔️ 121 taxones están presentes en ambas matrices CLR
    ✔️ Matriz V1 filtrada: (202, 121)
    ✔️ Matriz V3 filtrada: (202, 121)
    




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
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_vulgatus</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_dorei</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_coprocola</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Bacteroides; s__Bacteroides_uniformis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_plebeius</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Tannerellaceae; g__Parabacteroides; s__Parabacteroides_merdae</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Prevotella; s__Prevotella_copri</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Faecalibacterium; s__Faecalibacterium_prausnitzii</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Agathobacter; s__Agathobacter_rectalis</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Peptostreptococcales; f__Anaerovoracaceae; g__Copromorpha; s__Copromorpha_sp900066305</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Erysipelotrichales; f__Erysipelotrichaceae; g__Dielma; s__Dielma_fastidiosa</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Acutalibacter</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Erysipelotrichales; f__Erysipelotrichaceae; g__Holdemania; s__Holdemania_sp900120005</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Phocea; s__Phocea_massiliensis</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_massiliensis</th>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Lactobacillales; f__Aerococcaceae; g__Granulicatella; s__Granulicatella_adiacens</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Ruminococcaceae; g__Anaerotruncus; s__Anaerotruncus_sp003612625</th>
      <th>d__Bacteria; p__Patescibacteria; c__Saccharimonadia; o__Saccharimonadales; f__Nanosynbacteraceae; g__Nanosynbacter</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>3.631090</td>
      <td>6.719720</td>
      <td>6.410756</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>5.399860</td>
      <td>-1.251711</td>
      <td>3.895783</td>
      <td>5.472121</td>
      <td>...</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>-1.251711</td>
      <td>1.744021</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>6.325070</td>
      <td>3.163727</td>
      <td>-1.313610</td>
      <td>2.711742</td>
      <td>-1.313610</td>
      <td>4.832719</td>
      <td>4.057028</td>
      <td>7.123457</td>
      <td>4.098036</td>
      <td>-1.313610</td>
      <td>...</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>0.632300</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
      <td>-1.313610</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>7.221278</td>
      <td>-1.621182</td>
      <td>7.960860</td>
      <td>1.017875</td>
      <td>7.808695</td>
      <td>-1.621182</td>
      <td>7.083320</td>
      <td>7.037858</td>
      <td>...</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>2.473162</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>3.725925</td>
      <td>-1.621182</td>
      <td>-1.621182</td>
      <td>0.576042</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>6.445037</td>
      <td>4.675779</td>
      <td>-0.201959</td>
      <td>4.621543</td>
      <td>-2.910010</td>
      <td>4.995432</td>
      <td>4.883165</td>
      <td>0.385827</td>
      <td>5.152108</td>
      <td>4.339916</td>
      <td>...</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-1.118250</td>
      <td>-0.830568</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-2.910010</td>
      <td>-1.118250</td>
      <td>-2.910010</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>4.719755</td>
      <td>3.724005</td>
      <td>1.895328</td>
      <td>2.194483</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>4.014360</td>
      <td>0.205848</td>
      <td>4.993339</td>
      <td>3.804681</td>
      <td>...</td>
      <td>-0.812722</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-0.812722</td>
      <td>-1.298230</td>
      <td>-0.199618</td>
      <td>-3.377671</td>
      <td>-3.377671</td>
      <td>-0.081834</td>
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
      <th>S308</th>
      <td>7.467611</td>
      <td>5.355384</td>
      <td>-2.784348</td>
      <td>5.984382</td>
      <td>-0.011760</td>
      <td>5.127342</td>
      <td>5.507699</td>
      <td>0.106024</td>
      <td>3.743610</td>
      <td>5.115176</td>
      <td>...</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
      <td>0.473748</td>
      <td>-2.784348</td>
      <td>-2.784348</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>2.898197</td>
      <td>5.767664</td>
      <td>-2.578266</td>
      <td>4.328488</td>
      <td>7.312491</td>
      <td>4.692047</td>
      <td>4.334477</td>
      <td>-2.578266</td>
      <td>3.515303</td>
      <td>3.740702</td>
      <td>...</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
      <td>-0.968828</td>
      <td>-2.578266</td>
      <td>0.417466</td>
      <td>-2.578266</td>
      <td>-2.578266</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>5.091319</td>
      <td>1.346606</td>
      <td>5.407857</td>
      <td>4.458036</td>
      <td>6.681813</td>
      <td>3.504888</td>
      <td>-2.812277</td>
      <td>0.519928</td>
      <td>5.520993</td>
      <td>4.853945</td>
      <td>...</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
      <td>-1.425983</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
      <td>-0.104227</td>
      <td>-2.812277</td>
      <td>-0.247328</td>
      <td>-2.812277</td>
      <td>-2.812277</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>6.299240</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>3.282566</td>
      <td>-3.264219</td>
      <td>4.140668</td>
      <td>2.111059</td>
      <td>-3.264219</td>
      <td>3.302453</td>
      <td>5.330860</td>
      <td>...</td>
      <td>-0.128725</td>
      <td>2.280958</td>
      <td>1.300129</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-0.699270</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-3.264219</td>
      <td>-1.318309</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>4.223714</td>
      <td>6.067820</td>
      <td>-2.886982</td>
      <td>6.665457</td>
      <td>-0.584397</td>
      <td>1.495044</td>
      <td>6.029255</td>
      <td>0.408855</td>
      <td>4.949387</td>
      <td>2.025673</td>
      <td>...</td>
      <td>-2.886982</td>
      <td>-0.941072</td>
      <td>-2.886982</td>
      <td>-2.886982</td>
      <td>0.057457</td>
      <td>-0.807541</td>
      <td>-2.886982</td>
      <td>-0.402076</td>
      <td>-0.941072</td>
      <td>-2.886982</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 226 columns</p>
</div>



## 4.3 Unir matrices CLR v1 y v3 por taxón

Este DataFrame df_comparacion será la base para aplicar los test de Wilcoxon y añadir las variables de grupo (dieta y/o cluster). Ese será el siguiente paso.


```python
# Crear un nuevo DataFrame vacío para contener los datos combinados
df_comparacion = pd.DataFrame(index=ids_comunes)

# Recorrer todos los taxones y añadir columnas V1 y V3
for taxon in columnas_comunes:
    df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]

print("✔️ Tabla combinada creada:", df_comparacion.shape)
df_comparacion.head(3)
df_comparacion

```

    ✔️ Tabla combinada creada: (202, 242)
    

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:6: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V1"] = microbiota_CLR_135[taxon]
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4242841907.py:7: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion[f"{taxon}_V3"] = microbiota_CLR_v3_135[taxon]
    




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
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V3</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__UBA644; g__UBA644; s__UBA644_sp002299265_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__UBA644; g__UBA644; s__UBA644_sp002299265_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus; s__Enterenecus_faecium_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus; s__Enterenecus_faecium_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>1.496792</td>
      <td>1.456339</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>0.605819</td>
      <td>-1.251711</td>
      <td>...</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>2.109897</td>
      <td>-1.251711</td>
      <td>1.661872</td>
      <td>-1.251711</td>
      <td>1.298967</td>
      <td>-1.251711</td>
      <td>5.244183</td>
      <td>-1.251711</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>1.583377</td>
      <td>1.777432</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>...</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>1.260603</td>
      <td>-1.313610</td>
      <td>5.147553</td>
      <td>4.832719</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>...</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>1.017875</td>
      <td>8.481735</td>
      <td>0.170577</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>-0.100616</td>
      <td>0.134513</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>4.850768</td>
      <td>4.709224</td>
      <td>1.157424</td>
      <td>-0.512114</td>
      <td>-3.396453</td>
      <td>0.616351</td>
      <td>...</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>-0.831503</td>
      <td>-0.345060</td>
      <td>1.493897</td>
      <td>2.780350</td>
      <td>5.269161</td>
      <td>4.995432</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>2.036324</td>
      <td>2.151758</td>
      <td>3.108339</td>
      <td>1.612761</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>0.881016</td>
      <td>0.233247</td>
      <td>2.819758</td>
      <td>-1.431761</td>
      <td>...</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>3.852892</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
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
      <th>S308</th>
      <td>0.079886</td>
      <td>-0.299442</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>0.079886</td>
      <td>0.511489</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>...</td>
      <td>-0.012487</td>
      <td>-2.784348</td>
      <td>1.436327</td>
      <td>0.547856</td>
      <td>-0.079179</td>
      <td>0.306694</td>
      <td>5.409902</td>
      <td>5.127342</td>
      <td>3.856022</td>
      <td>3.664541</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>-1.991110</td>
      <td>0.887470</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>3.179374</td>
      <td>3.271058</td>
      <td>0.088332</td>
      <td>-2.578266</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>...</td>
      <td>-1.991110</td>
      <td>0.679830</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>-1.991110</td>
      <td>-0.381042</td>
      <td>3.451308</td>
      <td>4.692047</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>0.492292</td>
      <td>0.519928</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>-1.713665</td>
      <td>0.117598</td>
      <td>-0.327370</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>...</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>1.450403</td>
      <td>4.593901</td>
      <td>3.504888</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>3.718323</td>
      <td>4.317500</td>
      <td>1.652611</td>
      <td>3.636511</td>
      <td>-2.354722</td>
      <td>0.667606</td>
      <td>...</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>-2.354722</td>
      <td>-0.045344</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>5.465316</td>
      <td>4.140668</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>0.507084</td>
      <td>1.980552</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>2.692544</td>
      <td>1.822548</td>
      <td>1.300315</td>
      <td>0.003389</td>
      <td>...</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>2.039982</td>
      <td>2.277804</td>
      <td>1.346835</td>
      <td>1.495044</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 242 columns</p>
</div>



## 4.4 Añadir el grupo dieta y el grupo cluster
En este apartado tuve varios problemas a la hora de unir tablas debido a la diversidad de claves que he ido poniendo entre tablas, de cara al futuro asegurar ese paso. Aqui he solucionado el problema con la creacion de una nueva columna llamada id_merge que me ha permitido unir todo bien entre las 3 tablas:
- df_comparacion
- df_visita3_final
- df_clinica_cluster1


```python
import pandas as pd
import os

# 1. Ya tengo df_comparacion construido justo en pasos anteriores

# 2. Cargar tabla con información de dieta (V3)
ruta_dieta = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_final"
df_visita3_final = pd.read_csv(os.path.join(ruta_dieta, "df_visita3_final.csv"))

# 3. Cargar tabla con cluster (V1)
ruta_cluster = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_unión\visita1_microbiota"
df_clusters_clinica1 = pd.read_csv(os.path.join(ruta_cluster, "df_clusters_clinica1.csv"))
df_visita3_final
```




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
      <th>id</th>
      <th>visita0</th>
      <th>fechanac</th>
      <th>sexo</th>
      <th>nivelestudios</th>
      <th>situacionlaboral</th>
      <th>horariolaboral</th>
      <th>numerohijos</th>
      <th>madobesidad</th>
      <th>maddiabetes</th>
      <th>...</th>
      <th>masagrasaandroidedxa3</th>
      <th>masagrasainoidedxa3</th>
      <th>masavatdxa3g</th>
      <th>volumenvatdxa3cm</th>
      <th>pas3_1</th>
      <th>pad3_1</th>
      <th>pas3_2</th>
      <th>pad3_2</th>
      <th>adh_v2_v3</th>
      <th>caloriasdietamant</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>11/11/2015</td>
      <td>1/26/1961</td>
      <td>mujer</td>
      <td>estudios primarios</td>
      <td>Tiempo completo</td>
      <td>Partido</td>
      <td>3.0</td>
      <td>No antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>2839.0</td>
      <td>5352.0</td>
      <td>1221.0</td>
      <td>1294.0</td>
      <td>122.0</td>
      <td>74.0</td>
      <td>126.0</td>
      <td>73.0</td>
      <td>2.00</td>
      <td>1400.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>11/16/2015</td>
      <td>3/6/1984</td>
      <td>hombre</td>
      <td>bachiller o FP</td>
      <td>Tiempo completo</td>
      <td>3 turnos</td>
      <td>0.0</td>
      <td>No antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>2648.0</td>
      <td>4568.0</td>
      <td>1022.0</td>
      <td>1084.0</td>
      <td>136.0</td>
      <td>74.0</td>
      <td>141.0</td>
      <td>68.0</td>
      <td>2.00</td>
      <td>2100.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>11/19/2015</td>
      <td>7/14/1962</td>
      <td>hombre</td>
      <td>estudios primarios</td>
      <td>Paro</td>
      <td>No procede</td>
      <td>2.0</td>
      <td>Si antecedentes</td>
      <td>Si antecedentes</td>
      <td>...</td>
      <td>3709.0</td>
      <td>4362.0</td>
      <td>1893.0</td>
      <td>2007.0</td>
      <td>156.0</td>
      <td>84.0</td>
      <td>141.0</td>
      <td>76.0</td>
      <td>NaN</td>
      <td>2000.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>11/18/2015</td>
      <td>5/12/1949</td>
      <td>hombre</td>
      <td>bachiller o FP</td>
      <td>Jubilado/a</td>
      <td>No procede</td>
      <td>3.0</td>
      <td>No antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>2947.0</td>
      <td>3538.0</td>
      <td>2587.0</td>
      <td>2743.0</td>
      <td>139.0</td>
      <td>73.0</td>
      <td>125.0</td>
      <td>68.0</td>
      <td>1.00</td>
      <td>1900.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>11/20/2015</td>
      <td>5/9/1963</td>
      <td>mujer</td>
      <td>estudios primarios</td>
      <td>A tiempo parcial</td>
      <td>No procede</td>
      <td>2.0</td>
      <td>Si antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
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
      <th>309</th>
      <td>314</td>
      <td>2/13/2017</td>
      <td>10/15/1966</td>
      <td>hombre</td>
      <td>Universidad</td>
      <td>Tiempo completo</td>
      <td>Partido</td>
      <td>1.0</td>
      <td>Si antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>1515.0</td>
      <td>2277.0</td>
      <td>564.0</td>
      <td>598.0</td>
      <td>123.0</td>
      <td>85.0</td>
      <td>116.0</td>
      <td>80.0</td>
      <td>0.50</td>
      <td>2000.0</td>
    </tr>
    <tr>
      <th>310</th>
      <td>315</td>
      <td>2/13/2017</td>
      <td>9/10/1990</td>
      <td>mujer</td>
      <td>bachiller o FP</td>
      <td>A tiempo parcial</td>
      <td>2 turnos</td>
      <td>0.0</td>
      <td>No antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>2908.0</td>
      <td>7272.0</td>
      <td>439.0</td>
      <td>466.0</td>
      <td>126.0</td>
      <td>88.0</td>
      <td>114.0</td>
      <td>73.0</td>
      <td>0.50</td>
      <td>2000.0</td>
    </tr>
    <tr>
      <th>311</th>
      <td>316</td>
      <td>2/14/2017</td>
      <td>7/24/1965</td>
      <td>hombre</td>
      <td>estudios primarios</td>
      <td>Tiempo completo</td>
      <td>Partido</td>
      <td>3.0</td>
      <td>No antecedentes</td>
      <td>Si antecedentes</td>
      <td>...</td>
      <td>3099.0</td>
      <td>4594.0</td>
      <td>2257.0</td>
      <td>2393.0</td>
      <td>125.0</td>
      <td>62.0</td>
      <td>116.0</td>
      <td>74.0</td>
      <td>0.00</td>
      <td>2100.0</td>
    </tr>
    <tr>
      <th>312</th>
      <td>317</td>
      <td>2/15/2017</td>
      <td>9/1/1976</td>
      <td>mujer</td>
      <td>bachiller o FP</td>
      <td>Tiempo completo</td>
      <td>Continuo</td>
      <td>2.0</td>
      <td>No antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>4019.0</td>
      <td>8324.0</td>
      <td>994.0</td>
      <td>1054.0</td>
      <td>146.0</td>
      <td>99.0</td>
      <td>149.0</td>
      <td>98.0</td>
      <td>0.50</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>313</th>
      <td>318</td>
      <td>2/15/2017</td>
      <td>8/6/1989</td>
      <td>mujer</td>
      <td>Universidad</td>
      <td>Paro</td>
      <td>No procede</td>
      <td>0.0</td>
      <td>Si antecedentes</td>
      <td>No antecedentes</td>
      <td>...</td>
      <td>3934.0</td>
      <td>7901.0</td>
      <td>1216.0</td>
      <td>1289.0</td>
      <td>117.0</td>
      <td>74.0</td>
      <td>112.0</td>
      <td>74.0</td>
      <td>2.75</td>
      <td>2200.0</td>
    </tr>
  </tbody>
</table>
<p>314 rows × 97 columns</p>
</div>




```python
# 1. Para la tabla principal con taxones
df_comparacion["ID_merge"] = range(1, len(df_comparacion) + 1)

# 2. Para la tabla con grupo de dieta
df_visita3_final["ID_merge"] = range(1, len(df_visita3_final) + 1)

# 3. Para la tabla con clusters
df_clusters_clinica1["ID_merge"] = range(1, len(df_clusters_clinica1) + 1)
df_comparacion



```

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\1820004926.py:2: PerformanceWarning: DataFrame is highly fragmented.  This is usually the result of calling `frame.insert` many times, which has poor performance.  Consider joining all columns at once using pd.concat(axis=1) instead. To get a de-fragmented frame, use `newframe = frame.copy()`
      df_comparacion["ID_merge"] = range(1, len(df_comparacion) + 1)
    




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
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V3</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__UBA644; g__UBA644; s__UBA644_sp002299265_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus; s__Enterenecus_faecium_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Enterenecus; s__Enterenecus_faecium_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V3</th>
      <th>ID_merge</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>1.496792</td>
      <td>1.456339</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>0.605819</td>
      <td>-1.251711</td>
      <td>...</td>
      <td>-1.251711</td>
      <td>2.109897</td>
      <td>-1.251711</td>
      <td>1.661872</td>
      <td>-1.251711</td>
      <td>1.298967</td>
      <td>-1.251711</td>
      <td>5.244183</td>
      <td>-1.251711</td>
      <td>1</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>1.583377</td>
      <td>1.777432</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>...</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>1.260603</td>
      <td>-1.313610</td>
      <td>5.147553</td>
      <td>4.832719</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>2</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>...</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>1.017875</td>
      <td>8.481735</td>
      <td>0.170577</td>
      <td>3</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>-0.100616</td>
      <td>0.134513</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>4.850768</td>
      <td>4.709224</td>
      <td>1.157424</td>
      <td>-0.512114</td>
      <td>-3.396453</td>
      <td>0.616351</td>
      <td>...</td>
      <td>-2.910010</td>
      <td>-0.831503</td>
      <td>-0.345060</td>
      <td>1.493897</td>
      <td>2.780350</td>
      <td>5.269161</td>
      <td>4.995432</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>4</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>2.036324</td>
      <td>2.151758</td>
      <td>3.108339</td>
      <td>1.612761</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>0.881016</td>
      <td>0.233247</td>
      <td>2.819758</td>
      <td>-1.431761</td>
      <td>...</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>3.852892</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>5</td>
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
      <th>S308</th>
      <td>0.079886</td>
      <td>-0.299442</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>0.079886</td>
      <td>0.511489</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>...</td>
      <td>-2.784348</td>
      <td>1.436327</td>
      <td>0.547856</td>
      <td>-0.079179</td>
      <td>0.306694</td>
      <td>5.409902</td>
      <td>5.127342</td>
      <td>3.856022</td>
      <td>3.664541</td>
      <td>198</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>-1.991110</td>
      <td>0.887470</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>3.179374</td>
      <td>3.271058</td>
      <td>0.088332</td>
      <td>-2.578266</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>...</td>
      <td>0.679830</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>-1.991110</td>
      <td>-0.381042</td>
      <td>3.451308</td>
      <td>4.692047</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>199</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>0.492292</td>
      <td>0.519928</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>-1.713665</td>
      <td>0.117598</td>
      <td>-0.327370</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>...</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>1.450403</td>
      <td>4.593901</td>
      <td>3.504888</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>200</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>3.718323</td>
      <td>4.317500</td>
      <td>1.652611</td>
      <td>3.636511</td>
      <td>-2.354722</td>
      <td>0.667606</td>
      <td>...</td>
      <td>-3.264219</td>
      <td>-2.354722</td>
      <td>-0.045344</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>5.465316</td>
      <td>4.140668</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>201</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>0.507084</td>
      <td>1.980552</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>2.692544</td>
      <td>1.822548</td>
      <td>1.300315</td>
      <td>0.003389</td>
      <td>...</td>
      <td>-2.886982</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>2.039982</td>
      <td>2.277804</td>
      <td>1.346835</td>
      <td>1.495044</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>202</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 243 columns</p>
</div>




```python
# 🔐 Guardar el índice original antes del merge
indices_originales = df_comparacion.index.copy()
# 🔁 Unir con la columna 'dieta' desde visita 3
df_comparacion = df_comparacion.merge(
    df_visita3_final[["ID_merge", "dieta"]],
    on="ID_merge",
    how="left"
)

# 🔁 Unir con la columna 'cluster' desde clusters
df_comparacion = df_comparacion.merge(
    df_clusters_clinica1[["ID_merge", "cluster"]],
    on="ID_merge",
    how="left"
)

# 🔄 Restaurar el índice original
df_comparacion.index = indices_originales

# ✅ Convertir 'dieta' textual a grupo numérico
df_comparacion["dieta"] = df_comparacion["dieta"].str.lower().str.normalize("NFKD")\
    .str.encode("ascii", errors="ignore").str.decode("utf-8")

df_comparacion["Grupo"] = df_comparacion["dieta"].map({
    "dieta 1 o hiperproteica": 1,
    "dieta 2 o hipolip�dica": 2,
    "dieta 2 o hipolipdica": 2,
    "dieta 2 o hipolipidica": 2
})

# ✅ Renombrar 'cluster' a 'Cluster' para consistencia
df_comparacion = df_comparacion.rename(columns={"cluster": "Cluster"})


```


```python
df_comparacion
```




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
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__CAG-95; s__CAG-95_sp900066375_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Barnesiellaceae; g__Barnesiella; s__Barnesiella_intestinihominis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Alphaproteobacteria; o__RF32; f__CAG-239; g__51-20; s__51-20_sp001917175_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA1417; s__UBA1417_sp003531055_V3</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__Clostridium; s__Clostridium_leptum_V3</th>
      <th>...</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V1</th>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Acutalibacteraceae; g__UBA737; s__UBA737_sp900547445_V3</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V1</th>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis_V3</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V1</th>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Sutterella; s__Sutterella_wadsworthensis_V3</th>
      <th>ID_merge</th>
      <th>dieta</th>
      <th>Cluster</th>
      <th>Grupo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>1.496792</td>
      <td>1.456339</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>-2.166769</td>
      <td>-1.251711</td>
      <td>0.605819</td>
      <td>-1.251711</td>
      <td>...</td>
      <td>1.661872</td>
      <td>-1.251711</td>
      <td>1.298967</td>
      <td>-1.251711</td>
      <td>5.244183</td>
      <td>-1.251711</td>
      <td>1</td>
      <td>dieta 1 o hiperproteica</td>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>1.583377</td>
      <td>1.777432</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>...</td>
      <td>1.260603</td>
      <td>-1.313610</td>
      <td>5.147553</td>
      <td>4.832719</td>
      <td>-1.783919</td>
      <td>-1.313610</td>
      <td>2</td>
      <td>dieta 2 o hipolipdica</td>
      <td>0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>...</td>
      <td>-0.815333</td>
      <td>-1.621182</td>
      <td>-0.815333</td>
      <td>1.017875</td>
      <td>8.481735</td>
      <td>0.170577</td>
      <td>3</td>
      <td>dieta 1 o hiperproteica</td>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>-0.100616</td>
      <td>0.134513</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>4.850768</td>
      <td>4.709224</td>
      <td>1.157424</td>
      <td>-0.512114</td>
      <td>-3.396453</td>
      <td>0.616351</td>
      <td>...</td>
      <td>1.493897</td>
      <td>2.780350</td>
      <td>5.269161</td>
      <td>4.995432</td>
      <td>-3.396453</td>
      <td>-2.910010</td>
      <td>4</td>
      <td>dieta 2 o hipolipdica</td>
      <td>0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>2.036324</td>
      <td>2.151758</td>
      <td>3.108339</td>
      <td>1.612761</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>0.881016</td>
      <td>0.233247</td>
      <td>2.819758</td>
      <td>-1.431761</td>
      <td>...</td>
      <td>-2.807863</td>
      <td>3.852892</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>-2.807863</td>
      <td>-3.377671</td>
      <td>5</td>
      <td>dieta 2 o hipolipdica</td>
      <td>0</td>
      <td>2.0</td>
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
      <th>S308</th>
      <td>0.079886</td>
      <td>-0.299442</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>0.079886</td>
      <td>0.511489</td>
      <td>-3.446475</td>
      <td>-2.784348</td>
      <td>...</td>
      <td>-0.079179</td>
      <td>0.306694</td>
      <td>5.409902</td>
      <td>5.127342</td>
      <td>3.856022</td>
      <td>3.664541</td>
      <td>198</td>
      <td>dieta 1 o hiperproteica</td>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>-1.991110</td>
      <td>0.887470</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>3.179374</td>
      <td>3.271058</td>
      <td>0.088332</td>
      <td>-2.578266</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>...</td>
      <td>-1.991110</td>
      <td>-0.381042</td>
      <td>3.451308</td>
      <td>4.692047</td>
      <td>-1.991110</td>
      <td>-2.578266</td>
      <td>199</td>
      <td>dieta 1 o hiperproteica</td>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>0.492292</td>
      <td>0.519928</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>-2.280297</td>
      <td>-1.713665</td>
      <td>0.117598</td>
      <td>-0.327370</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>...</td>
      <td>-2.280297</td>
      <td>1.450403</td>
      <td>4.593901</td>
      <td>3.504888</td>
      <td>-2.280297</td>
      <td>-2.812277</td>
      <td>200</td>
      <td>dieta 1 o hiperproteica</td>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>3.718323</td>
      <td>4.317500</td>
      <td>1.652611</td>
      <td>3.636511</td>
      <td>-2.354722</td>
      <td>0.667606</td>
      <td>...</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>5.465316</td>
      <td>4.140668</td>
      <td>-2.354722</td>
      <td>-3.264219</td>
      <td>201</td>
      <td>dieta 1 o hiperproteica</td>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>0.507084</td>
      <td>1.980552</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>2.692544</td>
      <td>1.822548</td>
      <td>1.300315</td>
      <td>0.003389</td>
      <td>...</td>
      <td>2.039982</td>
      <td>2.277804</td>
      <td>1.346835</td>
      <td>1.495044</td>
      <td>-2.437355</td>
      <td>-2.886982</td>
      <td>202</td>
      <td>dieta 1 o hiperproteica</td>
      <td>0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 246 columns</p>
</div>



## 4.5  Comparar V1 vs V3 por taxón usando el test de Wilcoxon pareado

- En toda la cohorte

- Separado por Grupo (dieta 1 y 2)

- Separado por Cluster (0 y 1)


```python
from scipy.stats import wilcoxon
import pandas as pd

# Extraer la lista de taxones desde las columnas que terminan en '_V1'
taxones = [col.replace("_V1", "") for col in df_comparacion.columns if col.endswith("_V1")]

# Función para comparar pares y devolver resultados
def comparar_grupos(df, grupo=None):
    resultados = []

    # Filtrar si hay grupo específico
    if grupo is not None:
        df = df[df["Grupo"] == grupo]

    for taxon in taxones:
        col_v1 = f"{taxon}_V1"
        col_v3 = f"{taxon}_V3"

        try:
            stat, p = wilcoxon(df[col_v1], df[col_v3])
            media_v1 = df[col_v1].mean()
            media_v3 = df[col_v3].mean()
            resultados.append({
                "taxon": taxon,
                "media_V1": media_v1,
                "media_V3": media_v3,
                "p_value": p,
                "test": "wilcoxon"
            })
        except:
            pass  # Evita errores si el test no puede aplicarse (valores constantes, etc.)

    return pd.DataFrame(resultados)

# 🔸 Parte A: toda la cohorte
df_resultados_total = comparar_grupos(df_comparacion)

# 🔸 Parte B: Grupo 1 (hiperproteica)
df_resultados_grupo1 = comparar_grupos(df_comparacion, grupo=1)

# 🔸 Parte C: Grupo 2 (hipolipídica)
df_resultados_grupo2 = comparar_grupos(df_comparacion, grupo=2)

# ✔️ Mostrar resultados
print("✔️ Comparación total:", df_resultados_total.shape)
print("✔️ Comparación Grupo 1:", df_resultados_grupo1.shape)
print("✔️ Comparación Grupo 2:", df_resultados_grupo2.shape)
df_resultados_total

```

    ✔️ Comparación total: (121, 5)
    ✔️ Comparación Grupo 1: (121, 5)
    ✔️ Comparación Grupo 2: (121, 5)
    




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
      <th>taxon</th>
      <th>media_V1</th>
      <th>media_V3</th>
      <th>p_value</th>
      <th>test</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.180785</td>
      <td>-1.079533</td>
      <td>0.204921</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>1</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>-0.709418</td>
      <td>-0.693076</td>
      <td>0.328104</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>2</th>
      <td>d__Bacteria; p__Proteobacteria; c__Alphaproteo...</td>
      <td>-0.532190</td>
      <td>-0.365364</td>
      <td>0.555426</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>3</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.032081</td>
      <td>-0.084339</td>
      <td>0.255194</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>4</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.281504</td>
      <td>-1.366053</td>
      <td>0.286561</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>116</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.362723</td>
      <td>-1.290360</td>
      <td>0.608153</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>117</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.342484</td>
      <td>-1.265621</td>
      <td>0.567582</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>118</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-0.280761</td>
      <td>-0.215448</td>
      <td>0.827283</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>119</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>3.920863</td>
      <td>3.487904</td>
      <td>0.000005</td>
      <td>wilcoxon</td>
    </tr>
    <tr>
      <th>120</th>
      <td>d__Bacteria; p__Proteobacteria; c__Gammaproteo...</td>
      <td>-0.218425</td>
      <td>-0.350601</td>
      <td>0.048324</td>
      <td>wilcoxon</td>
    </tr>
  </tbody>
</table>
<p>121 rows × 5 columns</p>
</div>



## 4.6 Guardar tabla df_comparación y resultados hasta aqui


```python
# Ruta para guardar df_comparacion
ruta_comparacion = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_unión\comparación_taxones_CLR_v1_v3"
df_comparacion.to_csv(os.path.join(ruta_comparacion, "df_comparacion.csv"), index=True)

# Ruta para guardar los resultados de Wilcoxon
ruta_resultados = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\comparación_taxones_CLR_v1_v3"

df_resultados_total.to_csv(os.path.join(ruta_resultados, "df_resultados_total.csv"), index=False)
df_resultados_grupo1.to_csv(os.path.join(ruta_resultados, "df_resultados_grupo1.csv"), index=False)
df_resultados_grupo2.to_csv(os.path.join(ruta_resultados, "df_resultados_grupo2.csv"), index=False)

```

## 4.7 Aplicar FDR de nuevo a df_comparación


```python
from statsmodels.stats.multitest import multipletests
import os

# Función para aplicar FDR y añadir columna p_adj
def aplicar_fdr(df_resultados):
    df_resultados = df_resultados.copy()
    reject, p_adj, _, _ = multipletests(df_resultados["p_value"], method="fdr_bh")
    df_resultados["p_adj"] = p_adj
    df_resultados["significativo"] = reject  # True si pasa FDR
    return df_resultados

# Aplicar FDR
df_resultados_total_fdr = aplicar_fdr(df_resultados_total)
df_resultados_grupo1_fdr = aplicar_fdr(df_resultados_grupo1)
df_resultados_grupo2_fdr = aplicar_fdr(df_resultados_grupo2)

df_resultados_total_fdr



```




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
      <th>taxon</th>
      <th>media_V1</th>
      <th>media_V3</th>
      <th>p_value</th>
      <th>test</th>
      <th>p_adj</th>
      <th>significativo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.180785</td>
      <td>-1.079533</td>
      <td>0.204921</td>
      <td>wilcoxon</td>
      <td>0.476836</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>-0.709418</td>
      <td>-0.693076</td>
      <td>0.328104</td>
      <td>wilcoxon</td>
      <td>0.558421</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>d__Bacteria; p__Proteobacteria; c__Alphaproteo...</td>
      <td>-0.532190</td>
      <td>-0.365364</td>
      <td>0.555426</td>
      <td>wilcoxon</td>
      <td>0.782769</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>0.032081</td>
      <td>-0.084339</td>
      <td>0.255194</td>
      <td>wilcoxon</td>
      <td>0.532388</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.281504</td>
      <td>-1.366053</td>
      <td>0.286561</td>
      <td>wilcoxon</td>
      <td>0.535639</td>
      <td>False</td>
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
    </tr>
    <tr>
      <th>116</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.362723</td>
      <td>-1.290360</td>
      <td>0.608153</td>
      <td>wilcoxon</td>
      <td>0.808643</td>
      <td>False</td>
    </tr>
    <tr>
      <th>117</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-1.342484</td>
      <td>-1.265621</td>
      <td>0.567582</td>
      <td>wilcoxon</td>
      <td>0.782769</td>
      <td>False</td>
    </tr>
    <tr>
      <th>118</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>-0.280761</td>
      <td>-0.215448</td>
      <td>0.827283</td>
      <td>wilcoxon</td>
      <td>0.924603</td>
      <td>False</td>
    </tr>
    <tr>
      <th>119</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>3.920863</td>
      <td>3.487904</td>
      <td>0.000005</td>
      <td>wilcoxon</td>
      <td>0.000092</td>
      <td>True</td>
    </tr>
    <tr>
      <th>120</th>
      <td>d__Bacteria; p__Proteobacteria; c__Gammaproteo...</td>
      <td>-0.218425</td>
      <td>-0.350601</td>
      <td>0.048324</td>
      <td>wilcoxon</td>
      <td>0.188618</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>121 rows × 7 columns</p>
</div>




```python
# Ruta final de guardado
ruta_fdr = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\comparación_taxones_CLR_v1_v3\fdr"

# Guardar CSVs
df_resultados_total_fdr.to_csv(os.path.join(ruta_fdr, "df_resultados_total_fdr.csv"), index=False)
df_resultados_grupo1_fdr.to_csv(os.path.join(ruta_fdr, "df_resultados_grupo1_fdr.csv"), index=False)
df_resultados_grupo2_fdr.to_csv(os.path.join(ruta_fdr, "df_resultados_grupo2_fdr.csv"), index=False)

```

## 4.8 Gráficos
Siguiente pasos a seguir en orden: 
- Barplot de top taxones con p_adj < 0.05 (por grupo y total)
Veremos qué taxones son más significativos visualmente.

- Boxplots pareados por grupo (dieta 1 y 2) para taxones concretos.
Comparación directa de valores CLR V1 vs V3 en individuos del grupo.

- Tabla comparativa resumen entre total, grupo 1 y grupo 2

### 4.8.1 Boxplots de top taxones del tota, grupo 1 y grupo 2


```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Función para crear barplot de top taxones significativos
def barplot_top_taxones(df_resultados, titulo, color):
    # Filtrar solo los significativos tras FDR
    df_sig = df_resultados[df_resultados["p_adj"] < 0.05].copy()
    df_sig["-log10(p_adj)"] = -np.log10(df_sig["p_adj"])
    
    # Ordenar por significancia
    df_sig = df_sig.sort_values("p_adj").head(20)  # top 20
    plt.figure(figsize=(8, 10))
    sns.barplot(
        data=df_sig,
        y="taxon",
        x="-log10(p_adj)",
        palette=color
    )
    plt.title(titulo)
    plt.xlabel("-log10(p_adj)")
    plt.ylabel("Taxón")
    plt.tight_layout()
    plt.gca().invert_yaxis()
    plt.show()

# 🟦 Barplot para toda la cohorte
barplot_top_taxones(df_resultados_total_fdr, "Top taxones significativos - TODA COHORTE", "Blues")

# 🟩 Barplot para grupo 1
barplot_top_taxones(df_resultados_grupo1_fdr, "Top taxones significativos - GRUPO 1 (Hiperproteica)", "Greens")

# 🟥 Barplot para grupo 2
barplot_top_taxones(df_resultados_grupo2_fdr, "Top taxones significativos - GRUPO 2 (Hipolipídica)", "Reds")

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:14: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:23: UserWarning: Tight layout not applied. The left and right margins cannot be made large enough to accommodate all Axes decorations.
      plt.tight_layout()
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_23_1.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:14: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:23: UserWarning: Tight layout not applied. The left and right margins cannot be made large enough to accommodate all Axes decorations.
      plt.tight_layout()
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_23_3.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:14: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(
    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\3178164945.py:23: UserWarning: Tight layout not applied. The left and right margins cannot be made large enough to accommodate all Axes decorations.
      plt.tight_layout()
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_23_5.png)
    


### 4.8.2 Boxplots pareados por grupo


```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

# Función para generar un boxplot pareado V1 vs V3
def boxplot_taxon(df, taxon, grupo=None):
    col_v1 = f"{taxon}_V1"
    col_v3 = f"{taxon}_V3"

    # Filtrar por grupo si se especifica
    if grupo is not None:
        df_plot = df[df["Grupo"] == grupo].copy()
    else:
        df_plot = df.copy()

    # Preparar en formato largo para seaborn
    df_largo = pd.melt(
        df_plot[[col_v1, col_v3]],
        value_vars=[col_v1, col_v3],
        var_name="Visita",
        value_name="CLR"
    )

    df_largo["Visita"] = df_largo["Visita"].str.extract(r"_(V\d)")

    # Plot
    plt.figure(figsize=(6, 5))
    sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    sns.stripplot(data=df_largo, x="Visita", y="CLR", color='black', size=4, alpha=0.5, jitter=True)
    
    titulo = f"{taxon}\nGrupo: {'Todos' if grupo is None else grupo}"
    plt.title(titulo)
    plt.tight_layout()
    plt.show()

```


```python
# Con esta función puedo elegir que taxones mirar detalladamente por grupo (preguntar fermin y paula si quieren ver uno en especifico)
# Ejemplo: Visualizar un taxón significativo en grupo 1
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Blautia; s__Blautia_massiliensis", grupo=1)

# Otro ejemplo: Ver el mismo taxón en grupo 2
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Blautia; s__Blautia_massiliensis", grupo=2)

# Para toda la cohorte
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae; g__Blautia; s__Blautia_massiliensis")

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_26_1.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_26_3.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_26_5.png)
    



```python
# voy a visualizar 2 taxones mas
# Taxón 1 – Faecalibacterium prausnitzii (muy común en microbiota saludable)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis", grupo=1)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis", grupo=2)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Rikenellaceae; g__Alistipes; s__Alistipes_putredinis")

# Taxón 2 – Ruminococcus torques (sensible a dieta, asociado a metabolismo)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Lawsonibacter", grupo=1)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Lawsonibacter", grupo=2)
boxplot_taxon(df_comparacion, "d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Lawsonibacter")

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_1.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_3.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_5.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_7.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_9.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\4135762373.py:28: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df_largo, x="Visita", y="CLR", palette="Set2")
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_27_11.png)
    


### 4.8.3 Tabla comparativa



```python
# Extraer taxones con p_adj < 0.05 en cada grupo
set_total = set(df_resultados_total_fdr[df_resultados_total_fdr["p_adj"] < 0.05]["taxon"])
set_g1 = set(df_resultados_grupo1_fdr[df_resultados_grupo1_fdr["p_adj"] < 0.05]["taxon"])
set_g2 = set(df_resultados_grupo2_fdr[df_resultados_grupo2_fdr["p_adj"] < 0.05]["taxon"])

# Unir todos los taxones significativos en al menos uno
taxones_union = sorted(set_total | set_g1 | set_g2)

# Crear DataFrame resumen
resumen = pd.DataFrame({
    "taxon": taxones_union,
    "Total_sig": [taxon in set_total for taxon in taxones_union],
    "Grupo1_sig": [taxon in set_g1 for taxon in taxones_union],
    "Grupo2_sig": [taxon in set_g2 for taxon in taxones_union]
})

# Convertir booleanos a símbolos visuales
resumen = resumen.replace({True: "✅", False: "❌"})

# Mostrar resumen
import pandas as pd
from IPython.display import display
display(resumen.head(20))  # muestra los primeros 20
# Guardar matriz CLR transformada
ruta_salida_resumen = r'C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\comparación_taxones_CLR_v1_v3\resumen.csv'
resumen.to_csv(ruta_salida_resumen)
resumen

```


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
      <th>taxon</th>
      <th>Total_sig</th>
      <th>Grupo1_sig</th>
      <th>Grupo2_sig</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>d__Bacteria; p__Actinobacteriota; c__Actinomyc...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>1</th>
      <td>d__Bacteria; p__Actinobacteriota; c__Coriobact...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>2</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>3</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>❌</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>4</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>5</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>6</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>7</th>
      <td>d__Bacteria; p__Desulfobacterota; c__Desulfovi...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>8</th>
      <td>d__Bacteria; p__Firmicutes; c__Bacilli; o__Lac...</td>
      <td>✅</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>9</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>10</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>11</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>12</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>13</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>14</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>15</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>16</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>17</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>18</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>19</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
  </tbody>
</table>
</div>





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
      <th>taxon</th>
      <th>Total_sig</th>
      <th>Grupo1_sig</th>
      <th>Grupo2_sig</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>d__Bacteria; p__Actinobacteriota; c__Actinomyc...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>1</th>
      <td>d__Bacteria; p__Actinobacteriota; c__Coriobact...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>2</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>3</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>❌</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>4</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>5</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>6</th>
      <td>d__Bacteria; p__Bacteroidota; c__Bacteroidia; ...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>7</th>
      <td>d__Bacteria; p__Desulfobacterota; c__Desulfovi...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>8</th>
      <td>d__Bacteria; p__Firmicutes; c__Bacilli; o__Lac...</td>
      <td>✅</td>
      <td>✅</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>9</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>10</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>11</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>12</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>13</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>14</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>15</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>16</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>17</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>18</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>✅</td>
    </tr>
    <tr>
      <th>19</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>20</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>21</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>22</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
    <tr>
      <th>23</th>
      <td>d__Bacteria; p__Firmicutes; c__Clostridia; o__...</td>
      <td>✅</td>
      <td>❌</td>
      <td>❌</td>
    </tr>
  </tbody>
</table>
</div>



# ANÁLISIS DE RESULTADOS DE TAXONES


### 🔎 Análisis de los taxones significativos en la cohorte TOTAL (V1 vs V3)

El gráfico de barras muestra los 20 taxones más significativos tras aplicar el test de Wilcoxon pareado y la corrección por FDR (q < 0.05), analizados en el conjunto total de individuos sin distinción de dieta.

#### Observaciones clave:

- **Blautia massiliensis** es el taxón con mayor significancia estadística (`-log10(p_adj) ≈ 8`), lo que indica un cambio muy robusto entre V1 y V3 en esta especie.
- Muchos de los taxones pertenecen a los **filos Firmicutes y Bacteroidota**, especialmente dentro de las familias:
  - Lachnospiraceae (`g__Blautia`, `g__Roseburia`, `g__Ruminococcus`)
  - Oscillospiraceae (`g__Lawsonibacter`, `g__Faecalibacterium`)
  - Bacteroidaceae (`g__Bacteroides`)
- Aparecen también algunos taxones menos comunes como:
  - `Bilophila wadsworthia` (asociado a procesos inflamatorios)
  - `Parabacteroides distasonis` y `merdae`, conocidos por su papel en metabolismo de ácidos biliares.

#### Interpretación general:
- Estos resultados sugieren que la intervención entre V1 y V3 (sea temporal o por dieta) **genera una remodelación significativa de la microbiota intestinal**, con cambios en bacterias relevantes para la salud metabólica.
- Muchos de los taxones destacados han sido reportados previamente en estudios relacionados con **pérdida de peso, dieta, obesidad o inflamación**.

---


### 🧪 Análisis de los taxones significativos en el Grupo 1 (Dieta hiperproteica)

Este gráfico representa los taxones cuyo valor CLR cambió significativamente entre V1 y V3 (FDR < 0.05) dentro del grupo que siguió una dieta hiperproteica.

#### Observaciones clave:

- Aunque hay menos taxones significativos que en la cohorte completa, destacan cambios específicos en bacterias de interés metabólico.
- **Bacteroides stercoris** y **Parabacteroides merdae** presentan los cambios más significativos. Ambas especies pertenecen al filo **Bacteroidota**, comúnmente asociado a funciones digestivas y al metabolismo de carbohidratos.
- También destacan cambios en miembros del filo **Firmicutes**, incluyendo:
  - `Anaerobutyricum` (productor de butirato)
  - `Blautia massiliensis`, también detectado en la cohorte total, lo que sugiere un patrón robusto de cambio.
  - `Streptococcus thermophilus`, una especie típica de microbiota láctica, posiblemente influenciada por la dieta rica en proteínas lácteas.

#### Interpretación:
- Este patrón sugiere que la dieta hiperproteica impacta selectivamente sobre bacterias del metabolismo proteico y del ácido butírico.
- El hecho de que taxones como `Collinsella` y `Alistipes putredinis` también estén presentes sugiere una modulación compleja, con posibles implicaciones en inflamación o permeabilidad intestinal.

---


### 🧬 Análisis de los taxones significativos en el Grupo 2 (Dieta hipolipídica)

El gráfico muestra los taxones que cambiaron significativamente entre la visita 1 (V1) y la visita 3 (V3) en los participantes asignados a la dieta hipolipídica.

#### Observaciones clave:

- El taxón más destacado en este grupo es **Blautia massiliensis**, con una significancia estadística muy elevada (`-log10(p_adj) > 5`). Este resultado refuerza su importancia como posible biomarcador transversal, ya que también fue significativo en el grupo 1 y en la cohorte completa.
- Aparecen otros miembros del género **Blautia** y la familia **Lachnospiraceae**, lo cual indica una alta sensibilidad de esta familia a los cambios inducidos por la dieta baja en lípidos.
- **Agathobaculum butyriciproducens** (productor de butirato) y **Ruminococcus** también muestran cambios, lo que sugiere una posible mejora del perfil fermentativo de la microbiota.
- La presencia de **Bifidobacterium longum** sugiere un enriquecimiento de especies beneficiosas con la intervención.
- Se mantienen patrones similares a los observados en grupo 1, como los cambios en **Parabacteroides distasonis** y **Parabacteroides merdae**, pero con mayor significancia relativa.

#### Interpretación general:
- La dieta hipolipídica parece inducir cambios significativos en bacterias fermentadoras y moduladoras del metabolismo de lípidos.
- La presencia consistente de ciertos taxones sugiere que podrían actuar como **biomarcadores sensibles al tipo de dieta**, siendo relevantes para estudios posteriores de predicción de respuesta.

---



## Comparativa de taxones significativos (V1 vs V3) – Total vs Grupo 1 vs Grupo 2

Este resumen compara los resultados obtenidos tras aplicar el test de Wilcoxon pareado con corrección por FDR (`q < 0.05`) en tres grupos distintos: toda la cohorte, grupo 1 (dieta hiperproteica) y grupo 2 (dieta hipolipídica).

---

### Coincidencias entre grupos

| Taxón | Presente en | Observaciones |
|-------|-------------|---------------|
| **Blautia massiliensis** | ✅ Total, ✅ Grupo 1, ✅ Grupo 2 | Biomarcador muy robusto. Cambia significativamente en todos los grupos. |
| **Parabacteroides merdae** | ✅ Total, ✅ Grupo 1, ✅ Grupo 2 | Asociado al metabolismo lipídico. Aparece en todas las comparaciones. |
| **Bifidobacterium longum** | ✅ Total, ❌ Grupo 1, ✅ Grupo 2 | Ligado a la dieta hipolipídica. No aparece en grupo 1. |
| **Anaerobutyricum** | ❌ Total, ✅ Grupo 1, ✅ Grupo 2 | Efecto sensible a la dieta, no significativo en el total. |
| **Collinsella** | ✅ Total, ❌ Grupo 1, ✅ Grupo 2 | Cambios principalmente en dieta hipolipídica. |
| **Alistipes putredinis** | ✅ Total, ✅ Grupo 1, ❌ Grupo 2 | Más afectado por la dieta hiperproteica. |

---

### Taxones exclusivos por grupo

#### Solo en Grupo 1 (Hiperproteica)
- **Streptococcus thermophilus** – típico de fermentación láctica.
- **Bacteroides stercoris** – asociado a metabolismo proteico.

#### Solo en Grupo 2 (Hipolipídica)
- **Agathobaculum butyriciproducens**
- **Ruminococcus**
- **Parabacteroides distasonis**

---

### Conclusiones clave

- Existen **taxones núcleo** que cambian en todos los grupos → probablemente relacionados con el tiempo o el protocolo.
- Otros taxones **son específicos de la dieta** → posibles biomarcadores de respuesta diferencial.
- Casos como **Anaerobutyricum** son significativos sólo al separar los grupos, lo que sugiere que **el efecto se diluye en el análisis global**.

---

### Claves

Este análisis comparativo es muy útil para:

- Localizar biomarcadores robustos (`Blautia massiliensis`, `Parabacteroides merdae`).
- Estudiar mecanismos diferenciales entre dietas.
- Construir modelos predictivos de respuesta futura.



# ANÁLISIS DE BOXPLOTS PAREADOS


## Análisis específico de *Blautia massiliensis* (V1 vs V3)

###  1. Cohorte Total

📉 El gráfico muestra una **clara disminución del valor CLR** de *Blautia massiliensis* entre V1 y V3.

- **Mediana V1**: ~3.3  
- **Mediana V3**: ~2.5  
- La distribución es más **compacta** en V3.

Esto confirma que la intervención global del estudio (sin distinguir dietas) **reduce significativamente** este taxón.

➡️ Corrobora el resultado del **test de Wilcoxon**, donde *B. massiliensis* fue el taxón más significativo (`-log10(p_adj) ≈ 8`).

---

### 2. Grupo 1 – Dieta hiperproteica

📉 También se observa una **reducción clara del CLR**:

- **V1**: mayor mediana (~3.6)  
- **V3**: mediana más baja (~2.7)

El patrón es similar al total, aunque **menos pronunciado**. Esto sugiere que la dieta hiperproteica también contribuye a la reducción de *B. massiliensis*, aunque el efecto podría estar **parcialmente diluido** por otros factores (e.g., adherencia, microbiotipos iniciales).

---

### 3. Grupo 2 – Dieta hipolipídica

Se observa una **reducción más marcada aún** que en el Grupo 1:

- **V1**: mediana ~3.1–3.2  
- **V3**: mediana ~2.3

Además, se observa un **mayor número de outliers por debajo de 0 en V3**, lo que sugiere que en algunos individuos *B. massiliensis* **prácticamente desaparece** o sufre una **caída brusca**.

Esto concuerda con que este taxón fue también **altamente significativo en Grupo 2**, y podría estar **especialmente sensible a la dieta baja en grasas**.

---

### Conclusión Integrada

- *Blautia massiliensis* se reduce de forma significativa entre V1 y V3 en:
  - 🔹 Toda la cohorte
  - 🔹 Grupo 1 (dieta hiperproteica)
  - 🔹 Grupo 2 (dieta hipolipídica)

- Es un **biomarcador transversal** que responde al paso del tiempo y/o a los cambios dietéticos comunes.

- En el Grupo 2, la reducción parece **más intensa**, lo que sugiere una **modulación más potente por dieta hipolipídica**.


## 4.9 Análisis de diversidades
Hoja de ruta: Diversidad alfa y beta.
Paso 1 – Diversidad alfa
Calcularemos estos índices por paciente:

- Índice	Descripción
- Shannon	Entropía (riqueza + equitatividad)
- Simpson	Probabilidad de dominancia
- Chao1	Estimador de riqueza no observada
- Richness	Número de taxones presentes (sin contar ceros)

🔸 Compararemos Grupo 1 vs Grupo 2 usando test no paramétricos (Mann–Whitney U).

Paso 2 – Diversidad beta
U- saremos la matriz CLR de microbiota (V3) para calcular la distancia Bray–Curtis o Euclidiana.

- Visualización con PCoA o UMAP.

- Comparación con PERMANOVA (adonis) para ver si las dietas generan microbiotipos distintos

### Parte 1


```python
# VAMOS A CREAR EL CODIGO PARA LOS DIFERENTES TEST
import pandas as pd
import numpy as np
from skbio.diversity import alpha_diversity
from scipy.stats import mannwhitneyu

# 1. Cargar tabla de abundancias V3 ya filtrada (pacientes como filas, taxones como columnas)
ruta = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota\microbiota_filtrada_v3_t.csv"
microbiota_v3 = pd.read_csv(ruta, index_col=0)

# 2. Añadir pseudo-conteo para evitar ceros
microbiota_v3_safe = microbiota_v3 + 1e-9

# 3. Calcular índices de diversidad alfa
shannon = alpha_diversity('shannon', microbiota_v3_safe.values, ids=microbiota_v3_safe.index)
simpson = alpha_diversity('simpson', microbiota_v3_safe.values, ids=microbiota_v3_safe.index)

# Chao1 requiere conteos enteros
microbiota_counts = np.floor(microbiota_v3_safe.values).astype(int)
chao1 = alpha_diversity('chao1', microbiota_counts, ids=microbiota_v3_safe.index)

# Richness: número de taxones con abundancia > 0
richness = (microbiota_v3_safe > 0).sum(axis=1)

# 4. Crear DataFrame con los índices
df_diversidad = pd.DataFrame({
    "Shannon": shannon,
    "Simpson": simpson,
    "Chao1": chao1,
    "Richness": richness
}, index=microbiota_v3_safe.index)

# Vista rápida
print("✔️ Diversidad alfa calculada:", df_diversidad.shape)
df_diversidad.head()

```

    ✔️ Diversidad alfa calculada: (202, 4)
    




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
      <th>Shannon</th>
      <th>Simpson</th>
      <th>Chao1</th>
      <th>Richness</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>S001</th>
      <td>3.188111</td>
      <td>0.924630</td>
      <td>61.0</td>
      <td>226</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>2.734111</td>
      <td>0.829544</td>
      <td>77.0</td>
      <td>226</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>3.132730</td>
      <td>0.926272</td>
      <td>62.0</td>
      <td>226</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>3.721708</td>
      <td>0.950184</td>
      <td>138.0</td>
      <td>226</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>3.779114</td>
      <td>0.950779</td>
      <td>147.0</td>
      <td>226</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Guardar matriz CLR transformada
ruta_salida_diversidad = r'C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\resultados\comparación_taxones_CLR_v1_v3\df_diversidad.csv'
df_diversidad.to_csv(ruta_salida_diversidad)
```


```python
# EN ESTE BLOQUE VOY A CREAR EL CODIGO PARA REALIZAR LA COMPARACION ENTRE GRUPOS USANDO MANN WHITNEY
import pandas as pd
from scipy.stats import mannwhitneyu

# 1. Cargar las tablas

# 2. Crear columna 'Grupo' numérica si no existe
df_visita3_final["dieta"] = df_visita3_final["dieta"].str.lower().str.normalize("NFKD")\
    .str.encode("ascii", errors="ignore").str.decode("utf-8")

df_visita3_final["Grupo"] = df_visita3_final["dieta"].map({
    "dieta 1 o hiperproteica": 1,
    "dieta 2 o hipolipdica": 2,
    "dieta 2 o hipolipidica": 2,
    "dieta 2 o hipolip�dica": 2
})

# 3. Añadir Grupo a la tabla de diversidad
df_diversidad["Grupo"] = df_diversidad.index.map(
    lambda x: df_visita3_final.set_index("id").loc[int(x[1:]), "Grupo"] if x[1:].isdigit() else None
)

# 4. Comparar cada índice de diversidad
resultados_mw = []

for indice in ["Shannon", "Simpson", "Chao1", "Richness"]:
    grupo1 = df_diversidad[df_diversidad["Grupo"] == 1][indice]
    grupo2 = df_diversidad[df_diversidad["Grupo"] == 2][indice]

    stat, p = mannwhitneyu(grupo1, grupo2, alternative='two-sided')
    resultados_mw.append({
        "Índice": indice,
        "Media Grupo 1": grupo1.mean(),
        "Media Grupo 2": grupo2.mean(),
        "p-value": p
    })

# 5. Mostrar resultados
df_mw = pd.DataFrame(resultados_mw)
print(df_mw)

```

         Índice  Media Grupo 1  Media Grupo 2   p-value
    0   Shannon       3.406340       3.389521  0.680070
    1   Simpson       0.921686       0.921576  0.896391
    2     Chao1     114.463158     109.607477  0.142863
    3  Richness     226.000000     226.000000  1.000000
    


```python
# AHORA VAMOS A GENERAR BOX PLOTS
import seaborn as sns
import matplotlib.pyplot as plt

# Crear una copia para graficar
df_plot = df_diversidad.reset_index().rename(columns={'index': 'ID'})

# Convertir Grupo a categoría
df_plot['Grupo'] = df_plot['Grupo'].astype(str)

# Estilo gráfico
sns.set(style="whitegrid")

# Graficar cada índice
for indice in ['Shannon', 'Simpson', 'Chao1', 'Richness']:
    plt.figure(figsize=(7, 5))
    sns.boxplot(x='Grupo', y=indice, data=df_plot, palette='Set2')
    sns.stripplot(x='Grupo', y=indice, data=df_plot, color='black', alpha=0.3, jitter=0.15)
    plt.title(f'Diversidad {indice} por Grupo de Dieta')
    plt.xlabel("Grupo de Dieta")
    plt.ylabel(f"Índice {indice}")
    plt.tight_layout()
    plt.show()

```

    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\1792302261.py:17: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x='Grupo', y=indice, data=df_plot, palette='Set2')
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_42_1.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\1792302261.py:17: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x='Grupo', y=indice, data=df_plot, palette='Set2')
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_42_3.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\1792302261.py:17: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x='Grupo', y=indice, data=df_plot, palette='Set2')
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_42_5.png)
    


    C:\Users\randy\AppData\Local\Temp\ipykernel_26356\1792302261.py:17: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(x='Grupo', y=indice, data=df_plot, palette='Set2')
    


    
![png](comparacion_taxones_CLR_v1_vs_v3%20-%20copia_files/comparacion_taxones_CLR_v1_vs_v3%20-%20copia_42_7.png)
    

