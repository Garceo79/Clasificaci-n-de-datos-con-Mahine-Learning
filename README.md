# Análisis y Clasificación de Churn de Clientes

Este proyecto realiza un análisis exploratorio y la construcción de modelos de clasificación para predecir la probabilidad de churn de clientes utilizando un conjunto de datos de ejemplo.

## 1. Obtención y Exploración de Datos

Se cargan los datos del archivo `churn.csv`, se verifica la presencia de valores nulos y se elimina la columna `id_cliente`.

Se realiza un análisis exploratorio de los datos:
- Visualización de variables categóricas (`pais`, `sexo_biologico`, `servicios_adquiridos`, `tiene_tarjeta_credito`, `miembro_activo`) utilizando histogramas agrupados por la variable objetivo `churn`.
- Visualización de variables numéricas (`score_credito`, `edad`, `años_de_cliente`, `saldo`, `salario_estimado`) utilizando boxplots.

## 2. Transformación de Datos

- Se separan las variables explicativas (`X`) de la variable objetivo (`y`).
- Se transforman las variables categóricas en las variables explicativas a un formato numérico utilizando `OneHotEncoder`.
- Se transforma la variable objetivo `churn` a un formato numérico utilizando `LabelEncoder`.

## 3. Ajuste de Modelos

- Se dividen los datos en conjuntos de entrenamiento y prueba de forma estratificada (`train_test_split`).
- Se establece un modelo de referencia (baseline) utilizando `DummyClassifier`.
- Se entrena un modelo de Árbol de Decisión (`DecisionTreeClassifier`) con `max_depth=4`.
- Se evalúa el rendimiento de los modelos en los datos de prueba.
- Se visualiza el árbol de decisión entrenado.

## 4. Selección y Serialización de Modelos

- Se normalizan las variables numéricas de los conjuntos de entrenamiento y prueba utilizando `MinMaxScaler`.
- Se entrena un modelo K-Nearest Neighbors (`KNeighborsClassifier`) con los datos normalizados.
- Se comparan las precisiones de los modelos (`DummyClassifier`, `DecisionTreeClassifier`, `KNeighborsClassifier`).
- El modelo con mejor rendimiento (`DecisionTreeClassifier` en este caso) y el transformador `OneHotEncoder` se serializan utilizando `pickle` para su uso futuro.

## Uso

El notebook contiene el código paso a paso para replicar el análisis y la construcción de modelos. Los modelos guardados (`modelo_champion.pkl` y `modelo_onehotcoder.pkl`) pueden ser cargados para realizar predicciones sobre nuevos datos.
