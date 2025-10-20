# Análisis de la base de datos UCI Machine Learning dataset Gallstone

## Descripción del Proyecto

Este proyecto impementara la parte de entrenamiento de modelos de inteligencia artificial

Dataset a utilizar [Website Phishing](https://archive.ics.uci.edu/dataset/379/website+phishing)

## Archivos del Proyecto

### 00_point.ipynb - Balanceo de dataset Website Phishing

- **Objetivo**:
  - Analizar el balance de clases del dataset Website Phishing
  - Aplicar técnicas de balanceo (SMOTE) si el dataset está desbalanceado
  - Preparar el dataset balanceado para entrenamiento de modelos
- **Técnicas aplicadas**:
  - Análisis de distribución de clases
  - SMOTE (Synthetic Minority Oversampling Technique)
  - SMOTE + Tomek Links (combinación de oversampling y undersampling)
  - Random Undersampling (alternativa)
- **Dataset**:
  - Website Phishing (UCI Machine Learning Repository)
  - Análisis de ratio de desbalance
  - Generación de dataset balanceado
- **Resultados**:
  - Dataset balanceado guardado como 'phishing_balanced.csv'
  - Comparación visual antes/después del balanceo
  - Métricas de balance de clases

### 01_point.ipynb - Entrenar máquina de vectores de soporte (SVM)

- **Objetivo**:
  - Entrenar una máquina de vectores de soporte (SVM) sobre el dataset Website Phishing balanceado.
  - Validación cruzada para determinar el desempeño del clasificador.
  - Probar diferentes kernels y parámetros del kernel.
- **Clasificadores evaluados**:
  - SVM con kernel lineal, RBF, polinomial y sigmoide
  - Optimización de hiperparámetros con GridSearchCV
  - Validación cruzada (cv=5) para todas las configuraciones
- **Dataset**:
  - Website Phishing balanceado (archivo: phishing_balanced.csv)
  - Preprocesamiento: StandardScaler para normalización
- **Resultados**:
  - Mejor kernel y parámetros optimizados
  - Precisión de validación cruzada
  - Comparación de rendimiento entre kernels
- **Restricciones cumplidas**:
  - ✓ Entrenamiento de SVM sobre el dataset especificado
  - ✓ Validación cruzada para determinar desempeño
  - ✓ Prueba de diferentes kernels y parámetros

### 02_point.ipynb - Entrenar una red neuronal (ANN)

- **Objetivo**:
  - Entrenar una red neuronal artificial (ANN) feedforward sobre el dataset Website Phishing balanceado.
  - Validación cruzada para determinar el desempeño del clasificador.
  - Probar diferentes arquitecturas (número de capas y neuronas por capa).
  - Evaluar diferentes funciones de activación (relu, tanh, logistic, identity).
  - Optimizar hiperparámetros usando GridSearchCV.
- **Clasificadores evaluados**:
  - MLPClassifier con 11 arquitecturas diferentes (1-4 capas ocultas, 16-128 neuronas)
  - 4 funciones de activación evaluadas
  - Validación cruzada (cv=5) para todas las configuraciones
- **Dataset**:
  - Website Phishing balanceado (archivo: phishing_balanced.csv)
  - Preprocesamiento: StandardScaler para normalización
- **Resultados**:
  - Mejor arquitectura: Optimizada mediante GridSearchCV
  - Mejor función de activación: Determinada experimentalmente
  - Precisión CV: Resultado del modelo optimizado
  - Comparación con SVM del punto 1
- **Restricciones cumplidas**:
  - ✓ Entrenamiento de ANN feedforward sobre el dataset especificado
  - ✓ Validación cruzada para determinar desempeño
  - ✓ Prueba de diferentes arquitecturas (número de capas y neuronas)
  - ✓ Evaluación de diferentes funciones de activación
  - ✓ Optimización de hiperparámetros
  - ✓ Comparación con modelo SVM

### 03_point.ipynb - Análisis de Componentes Principales (PCA)

- **Objetivo**:
  - Aplicar PCA (Análisis de Componentes Principales) al dataset Website Phishing balanceado
  - Entrenar las mejores configuraciones de SVM y ANN con datos reducidos por PCA
  - Comparar el rendimiento antes y después de la reducción de dimensionalidad
  - Analizar el impacto de PCA en el rendimiento de los modelos
- **Técnicas aplicadas**:
  - PCA con diferentes números de componentes (2-9)
  - Análisis de varianza explicada
  - Comparación de rendimiento con y sin PCA
  - Visualización de resultados comparativos
- **Dataset**:
  - Website Phishing balanceado (archivo: phishing_balanced.csv)
  - Datos reducidos dimensionalmente con PCA
- **Resultados**:
  - Número óptimo de componentes principales
  - Comparación de rendimiento SVM vs ANN con PCA
  - Análisis del impacto de la reducción de dimensionalidad
  - Recomendaciones específicas para el dataset
- **Restricciones cumplidas**:
  - ✓ Aplicación de PCA al dataset Website Phishing balanceado
  - ✓ Entrenamiento de mejores configuraciones de SVM con PCA
  - ✓ Entrenamiento de mejores configuraciones de ANN con PCA
  - ✓ Comparación de rendimiento antes y después de PCA
  - ✓ Análisis del impacto de la reducción de dimensionalidad
  - ✓ Conclusiones específicas para el dataset utilizado
