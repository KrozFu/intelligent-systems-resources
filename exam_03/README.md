# Examen 03 - Análisis de Datasets con Aprendizaje Supervisado y No Supervisado

Aplicación de técnicas de aprendizaje supervisado (árboles de decisión) sobre el dataset Letter Recognition y no supervisado (clustering jerárquico y K-Means) sobre el dataset Seeds de UCI.

## Tabla de Contenidos

- [Dataset](#-dataset)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Notebooks](#-notebooks)
- [Orden de Ejecución](#-orden-de-ejecución)
- [Resultados Esperados](#-resultados-esperados)
- [Referencias](#-referencias)

## Datasets

### Letter Recognition Dataset

- **Fuente**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/59/letter+recognition)
- **Instancias**: 20,000 ejemplos
- **Características**: 16 atributos numéricos (estadísticas de primitivas de imagen)
- **Clases**: 26 letras mayúsculas del alfabeto inglés (A-Z)
- **Tipo de datos**: Atributos enteros derivados de imágenes de letras

### Seeds Dataset

- **Fuente**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/236/seeds)
- **Instancias**: 210
- **Características**: 7 atributos numéricos (medidas geométricas de granos de trigo)
- **Clases**: 3 (Kama, Rosa, Canadian)
- **Tipo de datos**: Atributos reales

### Características del Dataset

Los 16 atributos representan estadísticas de las primitivas de imagen extraídas de las imágenes de letras:

1. x-box: posición horizontal del recuadro
2. y-box: posición vertical del recuadro
3. width: ancho del recuadro
4. high: alto del recuadro
5. onpix: número total de píxeles activados
6. x-bar: posición x promedio de los píxeles activados
7. y-bar: posición y promedio de los píxeles activados
8. x2bar: varianza de x
9. y2bar: varianza de y
10. xybar: correlación x-y
11. x2ybr: correlación x²-y
12. xy2br: correlación x-y²
13. x-ege: número de bordes horizontales
14. xegvy: correlación de bordes horizontales
15. y-ege: número de bordes verticales
16. yegvx: correlación de bordes verticales

## Requisitos

- **Python**: 3.10 o superior
- **Librerías principales**:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `scikit-learn`
  - `scipy`
  - `jupyter`

## Estructura del Proyecto

```
exam_03/
├── README.md             # Este archivo
├── 01_point.ipynb        # Árboles de decisión
├── 02_point.ipynb        # Clustering jerárquico
└── 03_point.ipynb        # K-Means y evaluación
```

## Notebooks

| Notebook | Técnica | Objetivo Principal | Herramientas |
|----------|---------|-------------------|--------------|
| **01_point.ipynb** | Árboles de Decisión | Clasificación supervisada y extracción de reglas | CART/C4.5/ID3, Validación cruzada |
| **02_point.ipynb** | Clustering Jerárquico | Agrupamiento no supervisado | Dendrogramas, Linkage methods |
| **03_point.ipynb** | K-Means | Determinación de clusters óptimos | Método del codo, Silueta, J4 |

### 01_point.ipynb - Clasificación con Árboles de Decisión

**Objetivo**: Entrenar un modelo de clasificación basado en árboles de decisión para identificar letras y generar reglas interpretables.

**Técnicas aplicadas**:

- Implementación de algoritmos: CART, C4.5 o ID3
- División de datos: train/test split
- Validación cruzada (k-fold)
- Extracción de reglas de decisión
- Visualización del árbol

**Métricas de evaluación**:

- Accuracy (precisión global)
- Precision (por clase)
- Recall (sensibilidad)
- F1-score (media armónica)
- Matriz de confusión

### 02_point.ipynb - Clustering Jerárquico

**Objetivo**: Explorar relaciones naturales entre diferentes variedades de semillas de trigo usando agrupamiento jerárquico.

**Técnicas aplicadas**:

- Normalización/estandarización de datos
- Métricas de distancia:
  - Euclidiana
  - Manhattan
- Criterios de enlace (linkage):
  - Single linkage (vecino más cercano)
  - Complete linkage (vecino más lejano)
  - Average linkage (promedio)
  - Ward linkage (minimiza varianza)
- Visualización con dendrogramas

**Análisis**:

- Identificación de puntos de corte en dendrogramas
- Comparación de diferentes criterios de enlace
- Estimación preliminar del número óptimo de clusters

### 03_point.ipynb - K-Means y Evaluación

**Objetivo**: Determinar el número óptimo de clusters y aplicar K-Means para agrupar las letras.

**Técnicas aplicadas**:

- Método del codo (elbow method)
- Análisis de silueta (silhouette score)
- Algoritmo K-Means
- Evaluación con criterio J4
- Comparación: clustering jerárquico vs K-Means

**Métricas de evaluación**:

- Inercia (within-cluster sum of squares)
- Coeficiente de silueta
- Criterio J4 (índice de validación)
- Índice de Davies-Bouldin (opcional)

## Orden de Ejecución

Se recomienda ejecutar los notebooks en el siguiente orden:

1. **01_point.ipynb**: Comenzar con la clasificación supervisada para entender la estructura y separabilidad de las clases en el dataset.

2. **02_point.ipynb**: Aplicar clustering jerárquico para explorar agrupamientos naturales sin usar las etiquetas. Observar los dendrogramas para estimar el número de clusters.

3. **03_point.ipynb**: Validar el número óptimo de clusters mediante métodos cuantitativos y aplicar K-Means. Comparar resultados con los obtenidos previamente.

> **Nota**: Aunque los notebooks están diseñados para ejecutarse de forma independiente, seguir este orden permite una mejor comprensión del análisis completo.

## Resultados Esperados

### Punto 01 - Árboles de Decisión

- ✅ Árbol de decisión visualizado gráficamente
- ✅ Accuracy esperado: 85-95% (dependiendo de la profundidad y poda)
- ✅ Conjunto de reglas de clasificación interpretables
- ✅ Matriz de confusión 26x26
- ✅ Análisis de características más importantes

### Punto 02 - Clustering Jerárquico

- ✅ Dendrogramas para cada criterio de enlace en el dataset Seeds
- ✅ Comparación visual entre single, complete, average y ward
- ✅ Identificación de estructuras jerárquicas en los datos de las semillas
- ✅ Propuesta preliminar del número de clusters (k=3)

### Punto 03 - K-Means

- ✅ Gráfico del método del codo
- ✅ Análisis de silueta para diferentes valores de k
- ✅ Visualización de clusters formados (PCA/t-SNE para reducción dimensional)
- ✅ Métricas J4 para evaluar calidad de agrupamiento
- ✅ Tabla comparativa: jerárquico vs K-Means

## Referencias

- [UCI Machine Learning Repository - Letter Recognition](https://archive.ics.uci.edu/dataset/59/letter+recognition)
- [Scikit-learn Documentation - Decision Trees](https://scikit-learn.org/stable/modules/tree.html)
- [Scikit-learn Documentation - Clustering](https://scikit-learn.org/stable/modules/clustering.html)
- Breiman, L., et al. (1984). *Classification and Regression Trees*. Wadsworth.
- Quinlan, J. R. (1993). *C4.5: Programs for Machine Learning*. Morgan Kaufmann.
- MacQueen, J. (1967). *Some methods for classification and analysis of multivariate observations*.
