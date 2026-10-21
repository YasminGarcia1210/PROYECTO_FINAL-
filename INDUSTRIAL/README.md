# Industrial: calidad y eficiencia en una planta de inyección de plásticos

Grupos de 3 a 4 personas. **No compartir los datos en repositorios públicos** (solo el código).

## Contexto
Envases del Pacífico S.A.S. (EnPac), en Yumbo, Valle del Cauca, fabrica envases y tapas por inyección. Opera 14 máquinas, 5 resinas y 40 moldes. Una corrida es una orden de producción en una máquina, con un molde y una resina. La gerencia observa más desperdicio (scrap), devoluciones de clientes, mayor consumo de energía por unidad y comportamientos desiguales entre máquinas y moldes.

## Preguntas
- ¿Qué explica el desperdicio (`pct_desperdicio`) y cuánto se puede anticipar?
- ¿Qué determina el consumo específico de energía (`kwh_por_1000_und`)?
- ¿Se puede anticipar si un lote será Aprobado, Reproceso o Rechazado (`resultado_calidad`)?
- ¿Qué regímenes de operación existen y cómo se relacionan con desperdicio y calidad?

## Datos
- `produccion_corridas.csv`: corridas de producción
- `condiciones_planta.csv`: condiciones de planta
- `mantenimientos.csv`: mantenimientos
- `catalogo_maquinas_moldes.xlsx`: catálogo de máquinas y moldes
- `diccionario_de_datos.xlsx`: descripción de cada variable

## Tareas
1. **Contexto**: proceso de inyección, indicadores (desperdicio, energía, OEE, muestreo), sector plástico en Colombia, estado del arte. Mínimo 6 hipótesis verificables y criterios de éxito.
2. **EDA**: integración de las 4 fuentes, auditoría de calidad con tabla de decisiones, análisis uni/bi/multivariado (correlación, VIF), selección de variables y fuga de información.
3. **Preparación**: hold-out 80/20 estratificado antes de imputar, pipelines, imputación justificada, transformación log del consumo de energía, mínimo 3 variables derivadas, atípicos y desbalance (clase Rechazado).
4. **Modelamiento**: regresión lineal múltiple (+ Ridge/Lasso/Elastic Net) con diagnóstico de supuestos; regresión logística multinomial y KNN; al menos 2 modelos avanzados (Random Forest, XGBoost, SVM); interpretabilidad (permutación y PDP/SHAP); K-Means + PCA; ajuste de hiperparámetros con CV (k = 5 o 10) solo en entrenamiento.
5. **Evaluación**: R², RMSE, MAE; matriz de confusión, precision/recall/F1, F1 macro, Kappa, AUC; comparación CV vs prueba; evaluación económica con matriz de costos (el error más caro es despachar un lote que debía rechazarse); veredicto de hipótesis y modelo final.
6. **Despliegue**: mínimo 3 recomendaciones priorizadas con impacto cuantificado, uso y monitoreo del modelo, datos adicionales y consideraciones éticas (p. ej. variables de operarios).

## Entregables
- **Código**: Jupyter Notebook documentado.
- **Informe**: máximo 5 páginas, formato IEEE (resumen, introducción, metodología, resultados y discusión, conclusiones y trabajo futuro). Sin anexar el código.

Consigna completa: `Consigna_Proyecto Analítica de Datos.docx`.
