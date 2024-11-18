# Analisis de precios de alojamiento (plataforma Airnbnb Buenos Aires)
`¿Que es Airbnb?` Airbnb es una compañía que ofrece una plataforma digital dedicada a la oferta de alojamientos a particulares y turísticos (alquiler vacacional) mediante la cual los anfitriones pueden publicitar y contratar el arriendo de sus propiedades con sus huéspedes; anfitriones y huéspedes pueden valorarse mutuamente, como referencia para futuros usuarios.

`Descripción` Este proyecto tiene como objetivo predecir el precio por noche de un alojamiento utilizando diferentes características del inmueble, tales como el número de baños, la capacidad del alojamiento, el puntaje de las reseñas, entre otros. Se utiliza un modelo de Regresión Lineal para hacer predicciones y se evalúa su rendimiento usando métricas como el Error Cuadrático Medio (MSE), Coeficiente de Determinación (R²) y Error Absoluto Medio (MAE).
## Descripción de los Datos
El dataset contiene varias características de los alojamientos, incluyendo:

- Precio_Noche: El precio por noche del alojamiento (variable objetivo).
- Cant_Baños: El número de baños en el alojamiento.
- Capacidad_Alojamiento: La capacidad máxima de huéspedes que el alojamiento puede recibir.
- Score_Rating: El puntaje promedio de las reseñas del alojamiento.
- Amenidades_Numerico: Un indicador numérico de las amenidades del alojamiento.
- Tipo_Propiedad: El tipo de propiedad (por ejemplo, departamento, casa, etc.).
- Barrio_Alojamiento: El barrio donde se encuentra el alojamiento.


## Análisis exploratorio 
1. Inspección inicial de datos
    - Revisión de las primeras filas del conjunto de datos (.head)
    - Comprobar la dimensión del dataset (.shape)
    - Identificar tipos de variables (.dtypes)
2. Resumen estadístico básico
    - Resumen numérico de las columnas numéricas (.describe())
    - Para variables categoricas .value_counts() 
3. Detección de datos faltantes
    - Verificar si hay valores nulos o NaN (usando .isnull().sum()).
4. Visualización de datos
    - Distribución de variables (boxplots - Gráficos de barras)
5. Gráficos de barras
    - Calcular la correlación entre variables numéricas usando la matriz de correlación (.corr)
6. Detección de valores atípicos
    - boxplots para identificar valores atípicos.
7. Transformación de datos
    - Codificación de variables categóricas (One-Hot Encoding).

## Regresión Lineal
### Entrenamiento del Modelo 
- Se dividieron los datos en dos conjuntos: entrenamiento (80%) y prueba (20%).
- Se entrenó un modelo de Regresión Lineal utilizando las características seleccionadas para predecir el precio por noche de los alojamientos.
### Evaluación del Modelo
Se evaluó el rendimiento del modelo utilizando las siguientes métricas:
- Error Cuadrático Medio (MSE): Mide la diferencia promedio al cuadrado entre los valores predichos y los valores reales.
- Coeficiente de Determinación (R²): Mide la proporción de la varianza de los datos que es explicada por el modelo. Un valor de 1 indica que el modelo predice perfectamente, mientras que un valor de 0 indica que el modelo no explica nada de la varianza.
- Error Absoluto Medio (MAE): Mide la diferencia absoluta promedio entre las predicciones y los valores reales.
- Validación Cruzada: Se realizó una validación cruzada de 5 pliegues para obtener una medida más robusta de la precisión del modelo. El MSE promedio a través de los pliegues fue calculado.

### Gráficos de Diagnóstico
Se realizaron los siguientes gráficos para evaluar visualmente el rendimiento del modelo:

- Gráfico de Residuos vs. Predicciones: Muestra los residuos (diferencia entre los valores predichos y los reales) en función de las predicciones del modelo. Idealmente, los residuos deberían distribuirse aleatoriamente alrededor de cero.

- Gráfico de Dispersión: Muestra las predicciones frente a los valores reales, permitiendo visualizar la capacidad del modelo para predecir correctamente los precios.

## Resultados Obtenidos
Las métricas obtenidas durante el análisis son las siguientes:

- Error Cuadrático Medio (MSE): 1372.17
- Coeficiente de Determinación (R²): 0.38
- Error Absoluto Medio (MAE): 19.20
- MSE Promedio de Validación Cruzada (Mean Cross-Validated MSE): 1.65e+19

## Interpretación de los Resultados
- R² = 0.38: Esto indica que aproximadamente el 38% de la varianza en los precios de los alojamientos es explicada por el modelo. Este valor es relativamente bajo, lo que sugiere que el modelo tiene un poder predictivo limitado y que podrían ser necesarios más o mejores datos o un modelo diferente para mejorar el rendimiento.

- MSE = 1372.17: Esta es una medida del error cuadrático promedio en las predicciones del modelo. Un valor más bajo indica un mejor ajuste del modelo, pero este valor aún sugiere que el modelo tiene un margen de mejora.

- MAE = 19.20: Este es el error promedio absoluto, lo que significa que, en promedio, el modelo se desvía 19.20 unidades del valor real en su predicción. Aunque es un valor relativamente bajo, no es perfecto.

- MSE Promedio de Validación Cruzada: Un valor muy alto indica que el modelo podría estar sobreajustado o que no está generalizando bien a otros subconjuntos de datos.

## Conclusión
El modelo de Regresión Lineal utilizado en este análisis proporciona una predicción razonable de los precios por noche de los alojamientos, pero su capacidad predictiva es limitada. Existen varias formas de mejorar el rendimiento, como:

Utilizar modelos más complejos, como los árboles de decisión, Random Forest, o XGBoost.
Obtener más datos o incorporar nuevas características que podrían mejorar el modelo.
Realizar una mejor ingeniería de características y explorar otras técnicas de preprocesamiento, como la normalización de datos o el manejo de valores atípicos.