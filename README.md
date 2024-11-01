
# Taller #3 - Machine Learning 2: Predicción de la Tasa Representativa del Mercado (TRM)

Este proyecto forma parte del Taller #3 para la asignatura **Machine Learning 2** en la especialización de *Machine Learning*, donde se aplican técnicas de redes neuronales para predecir valores de la Tasa Representativa del Mercado (TRM) de Colombia. La base de datos utilizada fue obtenida del [Banco de la República de Colombia](https://www.banrep.gov.co/es/estadisticas/trm), con registros diarios de la TRM desde el 31 de octubre de 2021 hasta el 31 de octubre de 2024. El objetivo de este taller es construir y evaluar un modelo que permita predecir los valores futuros de la TRM, aplicando redes neuronales tipo LSTM (Long Short-Term Memory), las cuales son especialmente útiles para secuencias de datos temporales.

## Estructura del Proyecto

El proyecto está dividido en las siguientes secciones:

### 1. **Carga y Preprocesamiento de los Datos**

- **Fuente de Datos**: Los datos de la TRM fueron descargados del Banco de la República.
- **Limpieza de Datos**: Transformación de la columna de fecha en un índice `datetime` y conversión de la columna `TRM` a formato `float`. Esta estructuración permite una manipulación precisa de datos temporales y facilita la preparación de secuencias para el modelo de predicción.

### 2. **Visualización de los Datos**

- Generación de gráficos que muestran la evolución de la TRM en el tiempo, permitiendo una interpretación visual de las tendencias.

### 3. **Preprocesamiento para el Modelo**

- Escalado de los datos a un rango entre 0 y 1 utilizando `MinMaxScaler` para mejorar el rendimiento de la red neuronal.
- Creación de secuencias de datos temporales (ventanas deslizantes) que permiten capturar la dependencia temporal en los datos, necesarias para la entrada de la red LSTM.

### 4. **Construcción y Entrenamiento del Modelo LSTM**

- Implementación de un modelo secuencial con capas LSTM y capas densas (`Dense`) en Keras.
- Uso de `EarlyStopping` para evitar el sobreajuste, deteniendo el entrenamiento cuando la pérdida de validación deja de mejorar.
- Visualización del proceso de entrenamiento para observar la convergencia del modelo.

### 5. **Evaluación del Modelo**

- Predicción de la TRM en el conjunto de prueba.
- Medición de la efectividad del modelo mediante métricas como el **Error Absoluto Medio (MAE)**, el **Error Cuadrático Medio (MSE)**, y el **Error Cuadrático Medio de Raíz (RMSE)**.
- Cálculo del coeficiente de determinación **R²** para medir el ajuste del modelo con un valor entre 0 y 1, indicando qué tan bien el modelo captura las variaciones en los datos reales.

### 6. **Visualización de Resultados**

- Comparación gráfica entre los valores reales de la TRM y las predicciones realizadas por el modelo.

### 7. **Guardado del Modelo Entrenado**

- Almacenamiento del modelo entrenado en formato `.h5`, permitiendo su reutilización para futuras predicciones sin necesidad de reentrenar.

## Resultados y Conclusiones

La implementación del modelo LSTM mostró su efectividad al predecir tendencias en la TRM, aunque existen factores externos que pueden afectar la precisión de las predicciones. Este taller demostró la utilidad de las redes neuronales recurrentes para series temporales y sirvió como un ejercicio práctico en la implementación y evaluación de modelos de aprendizaje profundo para predicción de valores financieros.

## Requisitos

- Python 3.x
- Librerías: `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `tensorflow`
