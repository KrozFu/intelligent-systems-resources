# Análisis de la base de datos — UCI Machine Learning Dataset

## Descripción del Proyecto

Este proyecto tiene como objetivo aplicar técnicas fundamentales de aprendizaje supervisado y no supervisado utilizando un dataset de clasificación proveniente de la UCI Machine Learning Repository.

El desarrollo se organiza en tres etapas principales:

1. 01_point: Entrenamiento de un árbol de decisión (CART o C4.5/ID3) para generar reglas explícitas de clasificación y evaluación del modelo mediante validación cruzada.

2. 02_point: Aplicación del algoritmo de clustering jerárquico con diferentes criterios de enlace (linkage) para agrupar los datos y analizar la estructura de los clústeres formados.

3. 03_point: Determinación del número óptimo de clústeres a partir del punto anterior y aplicación del algoritmo K-means, evaluando su desempeño con el criterio J4.

El propósito final es comparar los resultados obtenidos con los distintos enfoques y comprender cómo las técnicas de aprendizaje supervisado y no supervisado modelan los datos.

## Archivos del Proyecto

### 01_point.ipynb - Entrenamiento de CART/C4.5/ID3

- **Objetivo**:
  - Entrenar y evaluar un modelo de clasificación basado en árboles de decisión para identificar patrones y generar reglas interpretables a partir del dataset.
- **Técnicas aplicadas**:
  - Implementación de algoritmos CART, C4.5 o ID3.
  - División del dataset en conjuntos de entrenamiento y prueba.
  - Validación cruzada para estimar el desempeño del modelo.
  - Extracción e interpretación de reglas de decisión.
  
- **Dataset**:
  
- **Resultados**:
  - Árbol de decisión visualizado gráficamente.
  - Métricas de desempeño: accuracy, precision, recall y F1-score.
  - Conjunto de reglas de clasificación derivadas del árbol.
  
### 02_point.ipynb - Algoritmo de clustering jerárquico

- **Objetivo**:
  
- **Técnicas aplicadas**:
  
- **Dataset**:
  
- **Resultados**:

### 03_point.ipynb - Número óptimo de clusters

- **Objetivo**:
  
- **Técnicas aplicadas**:
  
- **Dataset**:
  
- **Resultados**:
