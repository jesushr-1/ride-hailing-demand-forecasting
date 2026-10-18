## Pronóstico de la demanda de servicios de transporte

Análisis de series temporales | Aprendizaje automático (Machine Learning) | Python

### Descripción del proyecto

Sweet Lift Taxi necesita pronosticar la demanda horaria de taxis en aeropuertos para mejorar la disponibilidad de los conductores y la planificación operativa.

Este proyecto desarrolla y evalúa modelos de aprendizaje automático, utilizando datos históricos de solicitudes de taxis, para predecir la demanda de la hora siguiente.

### Conjunto de datos

El conjunto de datos contiene 4.416 observaciones horarias correspondientes al periodo entre marzo y agosto de 2018, e incluye marcas de tiempo y el número de solicitudes de taxis.

### Metodología

- Preparación de datos: Ordenamiento cronológico y remuestreo por horas.

- Análisis exploratorio de datos: Identificación de tendencias de demanda, patrones recurrentes y fluctuaciones.

- Ingeniería de características: Variables basadas en el tiempo, retardos (lags) de 24 horas y una media móvil de 24 horas.

- Modelado: Regresión lineal, Random Forest, CatBoost y LightGBM.

- Evaluación: División cronológica de los datos para entrenamiento, validación y prueba, utilizando la métrica RMSE.

### Resultados

| Model | Validation RMSE |
|---|---:|
| Linear Regression | 34.22 |
| Random Forest | 32.58 |
| CatBoost | **31.02** |
| LightGBM | 31.75 |

### Modelo Final

Final Model: CatBoost

Test RMSE: 41.33

Target RMSE: ≤ 48

Resultado: Objetivo alcanzado.

### Principales hallazgos

CatBoost obtuvo el menor error de validación y logró captar los patrones generales de la demanda por horas.

No obstante, el modelo tendió a subestimar los picos repentinos de demanda, lo que pone de manifiesto una oportunidad para mejorar las previsiones durante los periodos de mayor actividad.

### Recomendaciones para el negocio

- Utilizar las previsiones de demanda para optimizar la asignación de conductores.
- Mantener una mayor disponibilidad de conductores durante los periodos en los que, históricamente, la demanda es elevada.
- Realizar un seguimiento de los errores de predicción y reentrenar el modelo periódicamente con datos actualizados.

### Technologías

Python | Pandas | NumPy | Matplotlib | Scikit-learn | CatBoost | LightGBM

### Conclusión

Este proyecto demuestra cómo la predicción de series temporales y el aprendizaje automático pueden servir de apoyo a la toma de decisiones operativas en los servicios de transporte con conductor.