# Energías Inteligentes: plantas solares fotovoltaicas

Analítica de Datos I · Proyecto Final 2026-02 · Universidad Icesi. Peso: 30 % de la nota final.

La carrera ofrece **5 proyectos alternativos**, todos sobre datos reales de dos plantas solares (Planta 1 y Planta 2). Cada equipo desarrolla **uno**.

## Contexto común
Una empresa de operación y mantenimiento (O&M) de plantas solares quiere ofrecer sus servicios en Colombia y necesita herramientas analíticas para vigilar el desempeño de las plantas. Se trabaja con la planta completa: `AC_PLANTA_KW` es la suma de la potencia AC de sus 22 inversores, medida cada 15 minutos entre el 15-may-2020 y el 17-jun-2020 (34 días), solo en horas de sol. El modelo estima el instante siguiente (t + 1) con información disponible hasta t.

## Los 5 proyectos

| # | Proyecto | Tipo | Equipo | Archivo de la consigna |
|---|---|---|---|---|
| 1 | Potencia de la planta solar, **Planta 1** | Regresión | 4 personas | `Proyecto_Final_Solar_1_Regresion_Planta1.pdf` |
| 2 | Potencia de la planta solar, **Planta 2** (con pérdidas operativas) | Regresión + K-Means de días | 4 personas | `Proyecto_Final_Solar_2_Regresion_Planta2.pdf` |
| 3 | Nivel de generación (alto, medio, bajo), **Planta 1** | Clasificación | 3 personas | `Proyecto_Final_Solar_3_Clasificacion_Planta1.pdf` |
| 4 | Nivel de generación (alto, medio, bajo), **Planta 2** (con pérdidas operativas) | Clasificación + K-Means de días | 4 personas | `Proyecto_Final_Solar_4_Clasificacion_Planta2.pdf` |
| 5 | Temperatura del módulo, **Plantas 1 y 2** | Regresión + prueba en otra planta | 3 personas | `Proyecto_Final_Solar_5_Temperatura_Modulo.pdf` |

### Qué se hace en cada uno
- **1 y 2 (regresión de potencia):** predecir `AC_PLANTA_KW`. Líneas base: regresión lineal con la irradiación sola y persistencia (potencia de 15 min antes). Modelos: regresión lineal múltiple y árbol de decisión. Métricas: R², RMSE y MAE. En el proyecto 2, además, segmentar los días con K-Means (codo y silhouette) y relacionar los grupos con el error del modelo; se debe analizar por qué el clima no explica toda la variación (inversores sin producción, pérdidas operativas).
- **3 y 4 (clasificación de nivel):** clasificar el nivel de generación del instante siguiente con terciles de `AC_PLANTA_KW` calculados solo con entrenamiento. Líneas base: clase más frecuente y persistencia de la clase. Modelos: regresión logística, KNN y árbol de decisión. Métricas: accuracy, precision, recall, F1 por clase y matriz de confusión. En el proyecto 4, K-Means de días obligatorio para analizar los errores.
- **5 (temperatura del módulo):** predecir `MODULE_TEMPERATURE` a partir de temperatura ambiente, irradiación y hora. Se entrena y valida con la Planta 1 y se evalúa **sin reentrenar** en la Planta 2; se comparan los coeficientes de ambas plantas, se estima el porcentaje de pérdida de potencia por calor y se propone un umbral de alerta.

## Tareas (fases CRISP-DM)
1. **Contexto energético y operativo** (comprensión del negocio): al menos 5 fuentes confiables en formato IEEE (UPME, XM, CREG, IDEAM, artículos científicos) y 2 o 3 preguntas analíticas.
2. **Datos y EDA** (comprensión y preparación): construcción de `AC_PLANTA_KW`, registros ausentes, instantes con inversores faltantes, ceros nocturnos, formatos de fecha distintos entre archivos, error de escala DC/AC, atípicos (IQR o z), imputación justificada y exclusión de variables con fuga de información (potencia DC, `DAILY_YIELD`, `TOTAL_YIELD` y la potencia del mismo instante).
3. **Modelado y evaluación**: de lo simple a lo complejo y siempre contra una línea base. División cronológica por días (aprox. 80 % entrenamiento, 20 % prueba), `TimeSeriesSplit` de 5 particiones para hiperparámetros, escalado e imputación ajustados solo con entrenamiento, comparación entrenamiento vs. prueba para detectar sobreajuste.
4. **Informe, notebook y sustentación** (despliegue): cómo usaría la empresa el modelo.

## Datos
Dataset de Kaggle: https://www.kaggle.com/datasets/anikannal/solar-power-generation-data (cuenta gratuita, botón *Download*). Cada equipo lo descarga; **no está en este repositorio** y no debe incluirse en la entrega.

| Proyecto | Archivos a usar |
|---|---|
| 1 y 3 | `Plant_1_Generation_Data.csv` y `Plant_1_Weather_Sensor_Data.csv` |
| 2 y 4 | Los dos archivos equivalentes de la Planta 2 |
| 5 | Solo los archivos de sensores de ambas plantas |

Cada consigna trae un Anexo A (diccionario de datos) y un Anexo B (funciones de apoyo: ubicar datos, rezagos, persistencia y `crear_niveles`).

## Entregables
Un solo envío por grupo en la plataforma del curso, en un ZIP llamado `Proyecto<N>_Grupo_ApellidosMiembros.zip`, **sin los CSV**:
- **Notebook** (`.ipynb`): documentado, ejecutado de principio a fin con las salidas visibles y `random_state = 42`.
- **Informe**: PDF de máximo 5 páginas en la plantilla IEEE del curso (resumen de 150 a 250 palabras, cuatro palabras clave, introducción, materiales y métodos, resultados, discusión, conclusiones, declaración de uso de IAG y referencias IEEE). Sin código anexo.
- **Diapositivas** de la sustentación (PDF).

## Fechas
- Duración: 4 semanas, del miércoles 28-oct al miércoles 25-nov-2026.
- Entrega: **martes 24-nov-2026, 11:59 p. m.**
- Sustentación: **miércoles 25-nov-2026** (semana 17); 12 minutos de presentación y 8 de preguntas, y todos los integrantes presentan.

## Uso de IA generativa (Nivel 3, colaboración)
Se permite pedir explicaciones, generar o depurar código que el grupo entienda, mejorar la redacción y buscar fuentes (verificándolas en el documento original). **No** se permite delegar en la IAG las decisiones del proyecto (variables, faltantes y atípicos, modelo) ni la interpretación y las conclusiones, ni entregar nada que un integrante no pueda explicar. Es obligatorio llevar un registro de las interacciones y declarar el uso en el informe.

## Rúbrica
| Criterio | Peso |
|---|---|
| 1. Claridad y rigor en el análisis | 17.5 % |
| 2. Desarrollo y ajuste de los modelos | 17.5 % |
| 3. Validación y métricas | 17.5 % |
| 4. Comunicación de resultados | 17.5 % |
| 5. Sustentación oral (individual) | 30 % |

Niveles: Outstanding (4.5 a 5.0), Proficient (3.8 a 4.5), Developing (3.0 a 3.8) y Beginning (0 a 3.0). Los criterios 1 a 4 se califican por grupo y el 5 de forma individual: cualquier integrante puede ser llamado a explicar o modificar el notebook en vivo.
