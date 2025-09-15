# Análisis de la base de datos IRIS con Clasificadores

## Descripción del Proyecto

Este proyecto implementa y compara tres clasificadores de aprendizaje de máquina sobre el dataset Iris, cumpliendo con las restricciones específicas del examen académico.

## Archivos del Proyecto

### 01_point.ipynb - Validación Cruzada

- **Objetivo**: Implementar validación cruzada de 10 particiones para clasificadores bayesiano y geométrico
- **Clasificadores evaluados**:
  - Clasificador Bayesiano Gaussiano (usando GaussianNB de sklearn)
  - Clasificador Geométrico por Mínimos Cuadrados (implementación manual)
- **Dataset**: Iris (solo clases setosa y versicolor, todas las características)
- **Resultados**: Ambos clasificadores alcanzaron 100% de precisión en todas las particiones
- **Restricciones cumplidas**: Validación cruzada implementada manualmente sin usar KFold de sklearn

### 02_point.ipynb - Clasificador K-NN con Bootstrapping

- **Objetivo**: Implementar K-NN y evaluar su desempeño mediante bootstrapping
- **Clasificador**: K-NN implementado desde cero con distancia euclidiana
- **Dataset**: Iris completo (4 características, 3 clases)
- **Método de evaluación**: Bootstrapping manual (50 iteraciones)
- **Rango de k evaluado**: 1 a 20 vecinos
- **Mejor k encontrado**: k=2 (accuracy: 0.9833 ± 0.0075)
- **Estrategia de selección**: Desarrollada metodología práctica considerando accuracy y estabilidad

### 03_point.ipynb - Comparación de Clasificadores

- **Objetivo**: Comparar y contrastar los tres clasificadores según criterios específicos
- **Clasificadores comparados**:
  1. **Bayesiano Gaussiano**: Independencia condicional, distribución gaussiana
  2. **Geométrico (Mínimos Cuadrados)**: Separabilidad lineal, errores normales
  3. **K-NN**: Continuidad local, sin suposiciones de distribución

#### Criterios de Comparación

**1. Suposiciones de cada modelo:**

- **Bayesiano**: Independencia condicional, distribución gaussiana, linealidad
- **Geométrico**: Separabilidad lineal, errores normales, homocedasticidad
- **K-NN**: Continuidad local, distancia euclidiana apropiada, sin distribuciones específicas

**2. Requerimientos de entrenamiento:**

- **Bayesiano**: O(n×d) tiempo, O(d×c) memoria, O(d×c) predicción
- **Geométrico**: O(d³) tiempo, O(d²) memoria, O(d) predicción
- **K-NN**: O(1) tiempo, O(n×d) memoria, O(n×d) predicción

**3. Comportamiento con aumento de dimensiones:**

- **Bayesiano**: Sufre moderadamente, mantiene eficiencia O(n×d)
- **Geométrico**: Sufre severamente por O(d³), inestable en alta dimensionalidad
- **K-NN**: Sufre más severamente, distancia euclidiana pierde significado

**4. Ejemplos de aplicación (Contexto colombiano y personal):**

- **Bayesiano**: Diagnóstico médico cardiovascular, filtrado de spam
- **Geométrico**: Clasificación de créditos bancarios, recomendación de películas
- **K-NN**: Clasificación de cultivos con imágenes satelitales, reconocimiento de música

## Restricciones del Examen

### ✅ Librerías Permitidas

- Modelos: GaussianNB de sklearn, funciones de numpy
- Datos: pandas, numpy, load_iris() de sklearn
- Métricas: accuracy_score, confusion_matrix
- Visualizaciones: matplotlib, seaborn

### ❌ Librerías Prohibidas

- cross_val_score() de sklearn
- KFold() de sklearn
- train_test_split() de sklearn
- Cualquier función automática de validación cruzada

## Resultados Principales

1. **Punto 1**: Ambos clasificadores (bayesiano y geométrico) mostraron precisión perfecta (100%) en validación cruzada
2. **Punto 2**: K-NN con k=2 mostró el mejor balance entre accuracy (98.33%) y estabilidad
3. **Punto 3**: El clasificador bayesiano gaussiano demostró ser el más equilibrado para aplicaciones generales

## Conclusiones

- **Para sistemas en tiempo real**: Bayesiano Gaussiano
- **Para decisiones interpretables**: Geométrico (Mínimos Cuadrados)
- **Para patrones complejos**: K-NN
- **Para alta dimensionalidad**: Bayesiano Gaussiano
- **Para datasets pequeños**: Geométrico o Bayesiano
- **Para datasets grandes**: Bayesiano Gaussiano

## Tecnologías Utilizadas

- **Python 3.11.2**
- **Jupyter Notebook**
- **Librerías**: numpy, pandas, matplotlib, seaborn, scikit-learn
- **Entorno**: Virtual environment (venv)
