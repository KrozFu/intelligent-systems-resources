# Recomendaciones

¿Qué puedes y qué no puedes usar?
✅ SÍ puedes usar librerías para:
Modelos de clasificación: GaussianNB de sklearn, funciones de numpy para implementar clasificadores

Manipulación de datos: pandas para cargar y manejar datos, numpy para cálculos matemáticos

Dataset: Usar la base local de iris.csv o load_iris() de sklearn para cargar los datos

Métricas: accuracy_score, confusion_matrix para evaluar resultados

Visualizaciones: matplotlib, seaborn para gráficos

❌ NO puedes usar para validación:
cross_val_score() de sklearn

KFold() de sklearn

train_test_split() de sklearn

Cualquier función automática que divida los datos o haga validación cruzada
