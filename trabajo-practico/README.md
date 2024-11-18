# Analisis de precios de alojamiento (plataforma Airnbnb Buenos Aires)
`¿Que es Airbnb?` Airbnb es una compañía que ofrece una plataforma digital dedicada a la oferta de alojamientos a particulares y turísticos (alquiler vacacional) mediante la cual los anfitriones pueden publicitar y contratar el arriendo de sus propiedades con sus huéspedes; anfitriones y huéspedes pueden valorarse mutuamente, como referencia para futuros usuarios.

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
