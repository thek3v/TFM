# 3. Modelado abundancias v3

# 3.1 Cargar y transformar la tabla abundancias v3


```python
import pandas as pd

# 1. Cargar tabla original de la visita 3
ruta_microbiota_v3 = r"C:\Users\randy\Desktop\MC2\TFM\data\MICROBIOTA\V3\AbundanciasOB2G_HM202_gg2_V3.csv"
microbiota_abundancias_v3 = pd.read_csv(ruta_microbiota_v3, sep=";")

# Establecer la columna '#NAME' como índice
microbiota_abundancias_v3 = microbiota_abundancias_v3.set_index('#NAME')

# Confirmar carga por si acaso
print("✔️ Tabla V3 cargada:", microbiota_abundancias_v3.shape)

# Mostrar parte superior para revisión
microbiota_abundancias_v3.head()
microbiota_abundancias_v3

```

    ✔️ Tabla V3 cargada: (22890, 202)
    




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
      <th>S001</th>
      <th>S002</th>
      <th>S003</th>
      <th>S004</th>
      <th>S006</th>
      <th>S007</th>
      <th>S008</th>
      <th>S009</th>
      <th>S011</th>
      <th>S013</th>
      <th>...</th>
      <th>S297</th>
      <th>S298</th>
      <th>S299</th>
      <th>S300</th>
      <th>S305</th>
      <th>S308</th>
      <th>S309</th>
      <th>S314</th>
      <th>S315</th>
      <th>S316</th>
    </tr>
    <tr>
      <th>#NAME</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_vulgatus</th>
      <td>131</td>
      <td>2076</td>
      <td>0</td>
      <td>11556</td>
      <td>3285</td>
      <td>1947</td>
      <td>17985</td>
      <td>3766</td>
      <td>1865</td>
      <td>635</td>
      <td>...</td>
      <td>0</td>
      <td>1326</td>
      <td>5812</td>
      <td>1055</td>
      <td>848</td>
      <td>28337</td>
      <td>238</td>
      <td>2706</td>
      <td>14234</td>
      <td>1224</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_dorei</th>
      <td>2896</td>
      <td>87</td>
      <td>0</td>
      <td>1969</td>
      <td>1213</td>
      <td>566</td>
      <td>266</td>
      <td>0</td>
      <td>8520</td>
      <td>5539</td>
      <td>...</td>
      <td>2973</td>
      <td>1507</td>
      <td>0</td>
      <td>0</td>
      <td>3788</td>
      <td>3427</td>
      <td>4212</td>
      <td>63</td>
      <td>0</td>
      <td>7744</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_coprocola</th>
      <td>2126</td>
      <td>0</td>
      <td>6921</td>
      <td>14</td>
      <td>194</td>
      <td>2970</td>
      <td>0</td>
      <td>911</td>
      <td>12</td>
      <td>5188</td>
      <td>...</td>
      <td>0</td>
      <td>1794</td>
      <td>0</td>
      <td>6799</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3714</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Bacteroides; s__Bacteroides_uniformis</th>
      <td>0</td>
      <td>55</td>
      <td>0</td>
      <td>1865</td>
      <td>262</td>
      <td>1206</td>
      <td>52311</td>
      <td>0</td>
      <td>2797</td>
      <td>144</td>
      <td>...</td>
      <td>1837</td>
      <td>4141</td>
      <td>2052</td>
      <td>1771</td>
      <td>1265</td>
      <td>6429</td>
      <td>998</td>
      <td>1436</td>
      <td>696</td>
      <td>14078</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_plebeius</th>
      <td>0</td>
      <td>0</td>
      <td>14501</td>
      <td>0</td>
      <td>0</td>
      <td>4972</td>
      <td>33</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>13</td>
      <td>0</td>
      <td>5325</td>
      <td>14660</td>
      <td>5</td>
      <td>15</td>
      <td>19746</td>
      <td>13280</td>
      <td>0</td>
      <td>9</td>
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
      <th>d__Bacteria; p__Firmicutes; c__Dehalobacteriia; o__Dehalobacteriales; f__Dehalobacteriaceae</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Ramlibacter; s__Caenimonas_terrae</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Christensenellales; f__CAG-74</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Staphylococcales; f__Staphylococcaceae; g__Staphylococcus</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Lachnospirales; f__Lachnospiraceae</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>22890 rows × 202 columns</p>
</div>




```python
# 2. Eliminar duplicados del índice en V3
microbiota_abundancias_v3 = microbiota_abundancias_v3[~microbiota_abundancias_v3.index.duplicated(keep='first')]

print("✔️ Tabla V3 sin duplicados:", microbiota_abundancias_v3.shape)

# Vista rápida
microbiota_abundancias_v3.head()
microbiota_abundancias_v3
```

    ✔️ Tabla V3 sin duplicados: (1439, 202)
    




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
      <th>S001</th>
      <th>S002</th>
      <th>S003</th>
      <th>S004</th>
      <th>S006</th>
      <th>S007</th>
      <th>S008</th>
      <th>S009</th>
      <th>S011</th>
      <th>S013</th>
      <th>...</th>
      <th>S297</th>
      <th>S298</th>
      <th>S299</th>
      <th>S300</th>
      <th>S305</th>
      <th>S308</th>
      <th>S309</th>
      <th>S314</th>
      <th>S315</th>
      <th>S316</th>
    </tr>
    <tr>
      <th>#NAME</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_vulgatus</th>
      <td>131</td>
      <td>2076</td>
      <td>0</td>
      <td>11556</td>
      <td>3285</td>
      <td>1947</td>
      <td>17985</td>
      <td>3766</td>
      <td>1865</td>
      <td>635</td>
      <td>...</td>
      <td>0</td>
      <td>1326</td>
      <td>5812</td>
      <td>1055</td>
      <td>848</td>
      <td>28337</td>
      <td>238</td>
      <td>2706</td>
      <td>14234</td>
      <td>1224</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_dorei</th>
      <td>2896</td>
      <td>87</td>
      <td>0</td>
      <td>1969</td>
      <td>1213</td>
      <td>566</td>
      <td>266</td>
      <td>0</td>
      <td>8520</td>
      <td>5539</td>
      <td>...</td>
      <td>2973</td>
      <td>1507</td>
      <td>0</td>
      <td>0</td>
      <td>3788</td>
      <td>3427</td>
      <td>4212</td>
      <td>63</td>
      <td>0</td>
      <td>7744</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_coprocola</th>
      <td>2126</td>
      <td>0</td>
      <td>6921</td>
      <td>14</td>
      <td>194</td>
      <td>2970</td>
      <td>0</td>
      <td>911</td>
      <td>12</td>
      <td>5188</td>
      <td>...</td>
      <td>0</td>
      <td>1794</td>
      <td>0</td>
      <td>6799</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3714</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Bacteroides; s__Bacteroides_uniformis</th>
      <td>0</td>
      <td>55</td>
      <td>0</td>
      <td>1865</td>
      <td>262</td>
      <td>1206</td>
      <td>52311</td>
      <td>0</td>
      <td>2797</td>
      <td>144</td>
      <td>...</td>
      <td>1837</td>
      <td>4141</td>
      <td>2052</td>
      <td>1771</td>
      <td>1265</td>
      <td>6429</td>
      <td>998</td>
      <td>1436</td>
      <td>696</td>
      <td>14078</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Bacteroidaceae; g__Phocaeicola; s__Phocaeicola_plebeius</th>
      <td>0</td>
      <td>0</td>
      <td>14501</td>
      <td>0</td>
      <td>0</td>
      <td>4972</td>
      <td>33</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>13</td>
      <td>0</td>
      <td>5325</td>
      <td>14660</td>
      <td>5</td>
      <td>15</td>
      <td>19746</td>
      <td>13280</td>
      <td>0</td>
      <td>9</td>
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
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__UBA738</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Firmicutes; c__Bacilli; o__Bacillales; f__Planococcaceae; g__Planococcus</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Bacteroidota; c__Bacteroidia; o__Bacteroidales; f__Muribaculaceae; g__Paramuribaculum</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Firmicutes; c__Clostridia; o__Oscillospirales; f__Oscillospiraceae; g__Sporobacter; s__Sporobacter_termitidis</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>d__Bacteria; p__Proteobacteria; c__Gammaproteobacteria; o__Burkholderiales; f__Burkholderiaceae; g__Ramlibacter; s__Caenimonas_terrae</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>1439 rows × 202 columns</p>
</div>




```python
# 3. Crear tabla binaria: 1 si hay al menos 4 unidades
microbiota_binaria_v3 = (microbiota_abundancias_v3 >= 4).astype(int)

# 4. Calcular prevalencia por bacteria (% de sujetos en los que aparece)
prevalencia_v3 = microbiota_binaria_v3.sum(axis=1) / microbiota_binaria_v3.shape[1] * 100

# 5. Seleccionar bacterias con prevalencia ≥ 20%
bacterias_filtradas_v3 = prevalencia_v3[prevalencia_v3 >= 20].index.tolist()

# 6. Filtrar realmente la tabla
microbiota_filtrada_v3 = microbiota_abundancias_v3.loc[bacterias_filtradas_v3]

# 7. Transponer para tener sujetos como filas
microbiota_filtrada_v3_t = microbiota_filtrada_v3.T

# Confirmación
print(f"✔️ Bacterias seleccionadas tras filtro de prevalencia ≥20%: {len(bacterias_filtradas_v3)}")
print("✔️ Nueva forma de la tabla V3 transpuesta:", microbiota_filtrada_v3_t.shape)

# 4. Guardar matriz CLR transformada
ruta_salida_v3_t = r"C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota\microbiota_filtrada_v3_t.csv"
microbiota_filtrada_v3_t.to_csv(ruta_salida_v3_t)

# Vista rápida
microbiota_filtrada_v3_t.head()
microbiota_filtrada_v3_t


```

    ✔️ Bacterias seleccionadas tras filtro de prevalencia ≥20%: 226
    ✔️ Nueva forma de la tabla V3 transpuesta: (202, 226)
    




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
      <th>#NAME</th>
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
      <td>131</td>
      <td>2896</td>
      <td>2126</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>773</td>
      <td>0</td>
      <td>171</td>
      <td>831</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>19</td>
    </tr>
    <tr>
      <th>S002</th>
      <td>2076</td>
      <td>87</td>
      <td>0</td>
      <td>55</td>
      <td>0</td>
      <td>466</td>
      <td>214</td>
      <td>4614</td>
      <td>223</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>S003</th>
      <td>0</td>
      <td>0</td>
      <td>6921</td>
      <td>0</td>
      <td>14501</td>
      <td>13</td>
      <td>12454</td>
      <td>0</td>
      <td>6029</td>
      <td>5761</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>59</td>
      <td>0</td>
      <td>0</td>
      <td>209</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>S004</th>
      <td>11556</td>
      <td>1969</td>
      <td>14</td>
      <td>1865</td>
      <td>0</td>
      <td>2711</td>
      <td>2423</td>
      <td>26</td>
      <td>3171</td>
      <td>1407</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>7</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
    </tr>
    <tr>
      <th>S006</th>
      <td>3285</td>
      <td>1213</td>
      <td>194</td>
      <td>262</td>
      <td>0</td>
      <td>0</td>
      <td>1622</td>
      <td>35</td>
      <td>4319</td>
      <td>1315</td>
      <td>...</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>12</td>
      <td>7</td>
      <td>23</td>
      <td>0</td>
      <td>0</td>
      <td>26</td>
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
      <td>28337</td>
      <td>3427</td>
      <td>0</td>
      <td>6429</td>
      <td>15</td>
      <td>2728</td>
      <td>3991</td>
      <td>17</td>
      <td>683</td>
      <td>2695</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>25</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>S309</th>
      <td>238</td>
      <td>4212</td>
      <td>0</td>
      <td>998</td>
      <td>19746</td>
      <td>1436</td>
      <td>1004</td>
      <td>0</td>
      <td>442</td>
      <td>554</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>19</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>S314</th>
      <td>2706</td>
      <td>63</td>
      <td>3714</td>
      <td>1436</td>
      <td>13280</td>
      <td>553</td>
      <td>0</td>
      <td>27</td>
      <td>4159</td>
      <td>2134</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>14</td>
      <td>0</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>S315</th>
      <td>14234</td>
      <td>0</td>
      <td>0</td>
      <td>696</td>
      <td>0</td>
      <td>1643</td>
      <td>215</td>
      <td>0</td>
      <td>710</td>
      <td>5404</td>
      <td>...</td>
      <td>22</td>
      <td>255</td>
      <td>95</td>
      <td>0</td>
      <td>0</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>S316</th>
      <td>1224</td>
      <td>7744</td>
      <td>0</td>
      <td>14078</td>
      <td>9</td>
      <td>79</td>
      <td>7451</td>
      <td>26</td>
      <td>2530</td>
      <td>135</td>
      <td>...</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>18</td>
      <td>7</td>
      <td>0</td>
      <td>11</td>
      <td>6</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>202 rows × 226 columns</p>
</div>



### 3.1.1 CLR


```python
import numpy as np
import pandas as pd

# 1. Evitar ceros sumando +1 para evitar log(0)
microbiota_ready_v3 = microbiota_filtrada_v3_t + 1

# 2. Definir función CLR
def clr_transform(df):
    log_df = np.log(df)
    geometric_mean = log_df.mean(axis=1)
    clr_values = log_df.subtract(geometric_mean, axis=0)
    return clr_values

# 3. Aplicar transformación CLR
microbiota_clr_v3 = clr_transform(microbiota_ready_v3)

print("✔️ CLR aplicado correctamente en V3:", microbiota_clr_v3.shape)

# 4. Guardar matriz CLR transformada
ruta_salida_v3 = r'C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota\microbiota_CLR_v3.csv'
microbiota_clr_v3.to_csv(ruta_salida_v3)

print(f"✔️ Matriz CLR V3 guardada en {ruta_salida_v3}")
microbiota_clr_v3.head()
microbiota_clr_v3
```

    ✔️ CLR aplicado correctamente en V3: (202, 226)
    ✔️ Matriz CLR V3 guardada en C:\Users\randy\Desktop\MC2\TFM\data\tablas_generadas\procesadas\procesadas_microbiota\microbiota_CLR_v3.csv
    




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
      <th>#NAME</th>
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


