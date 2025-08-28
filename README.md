# TFM
TFM: Análisis de microbiota intestinal en el estudio OBEKIT. Identificación de taxones diferenciales, clústeres microbianos y su relación con parámetros clínicos y metabólicos bajo intervenciones dietéticas.

# Biomarcadores metabolómicos y de microbiota en relación con dieta y enfermedad metabólica

Este repositorio contiene el código, resultados y documentación del **Trabajo de Fin de Máster (TFM)** en el Máster en Ciencia de Datos para Ciencias Experimentales (Universidad de Navarra).  
El objetivo del proyecto es **evaluar el papel de la microbiota intestinal en la respuesta clínica y metabólica a una intervención dietética** en sujetos con sobrepeso y obesidad de la cohorte OBEKIT.

## Contenido
- **/data/** → Datos clínicos y de microbiota procesados (no se incluyen datos brutos por confidencialidad).  
- **/notebooks/** → Jupyter Notebooks con el análisis de microbiota, clustering, diversidad y comparaciones clínicas.  
- **/results/** → Tablas de resultados (taxones diferenciales, diversidad alfa/beta, evolución clínica).  
- **/figures/** → Figuras utilizadas en la memoria del TFM (boxplots, PCA, clustering, etc.).  
- **/docs/** → Documento final del TFM en PDF y material complementario.  

## Metodología
- Preprocesamiento de datos de microbiota (filtrado, pseudoconteo, transformación CLR).  
- Análisis de **clustering (K-Means)** y explicación con **Random Forest**.  
- Cálculo de **diversidad alfa y beta** (Shannon, Simpson, Chao1, Richness; Bray–Curtis, PCoA, PERMANOVA).  
- Comparaciones clínicas y bioquímicas entre clústeres y entre visitas (V1 vs V3).  
- Integración con variables dietéticas para evaluar interacción **microbiota–dieta–fenotipo clínico**.  

## Resultados principales
- Identificación de dos **microbiotipos diferenciados** (clusters).  
- **Taxones clave**: *Lawsonibacter*, *Vescimonas*, *Blautia massiliensis*.  
- Diferencias en cronotipo, edad y antecedentes cardiovasculares entre clusters.  
- Evolución clínica heterogénea tras la dieta: el cluster 1 mostró descensos más marcados en leptina, TSH y grasa ginecoide.  
- La respuesta a la intervención dietética estuvo condicionada por el microbiotipo basal.  

## Autoría
- **Autor**: Kevin Randy Vargas Castro  
- **Directores**: Fermín Milagro y Paula Aranaz  
- **Institución**: Universidad de Navarra  
- **Año**: 2025  

## Citas
Si utilizas este repositorio como referencia, por favor cita el TFM:  
*"Biomarcadores metabolómicos y de microbiota en relación con dieta y enfermedad metabólica", Kevin Vargas, Universidad de Navarra, 2025.*
