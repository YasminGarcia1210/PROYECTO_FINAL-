# Biología: ovitrampas de *Aedes aegypti*

## Contexto
*Aedes aegypti* es uno de los principales vectores del dengue. Se asume un sistema hipotético de vigilancia con ovitrampas junto a 18 nodos del Observatorio Ambiental de la Comuna 22 de Cali. Cada ovitrampa se revisa semanalmente y se cuentan los huevos. El objetivo es relacionar los conteos con temperatura, humedad y precipitación para detectar las épocas del año con posibles picos de dengue.

Los conteos de huevos son **simulados con fines académicos**; no son monitoreo real y no deben interpretarse como registros epidemiológicos.

## Datos
`Consolidado_ambiental_nodos_Comuna_22_AD.xlsx`: hoja *Datos semanales* (una observación semanal por nodo, con temperatura, humedad relativa, precipitación y huevos; contiene valores faltantes y atípicos) y hoja *Diccionario*.

## Consigna
1. **EDA**: distribución, temporalidad, diferencias entre nodos, faltantes, extremos y relaciones entre variables. Justificar el tratamiento de faltantes y atípicos (y toda exclusión).
2. **Aprendizaje no supervisado**: agrupar nodos con una matriz resumen por nodo, incorporando al menos 2 variables externas de fuentes verificables (NDVI, cobertura urbana, cercanía a cuerpos de agua, densidad poblacional, etc.). Describir fuentes y procedimiento, estandarizar y justificar el número de grupos. Interpretar los grupos y comparar su oviposición; discutir limitaciones por el número de nodos.
3. **Modelos predictivos**: (a) número semanal de huevos; (b) clasificar la ovitrampa como positiva o negativa. Partición temporal: entrenamiento del 26-jun-2023 al 14-sep-2025; prueba del 15-sep-2025 al 14-sep-2026. Métricas apropiadas para conteos y clasificación, comparación de modelos e interpretación de variables.
4. **Sistema de alerta temprana**: condiciones de activación, niveles (bajo, moderado, alto), nodos y periodos de mayor vigilancia, acciones por nivel y limitaciones.
5. **Conclusiones** sobre utilidad y limitaciones del modelo.

## Entregables
- **Código**: notebook de Python reproducible, organizado por secciones, con diccionario de variables y comentarios.
- **Informe**: Word, máximo 5 páginas, letra 12, espacio sencillo. Introducción (1 pág), objetivos (0.5), metodología (1), resultados (1.5), discusión y conclusiones (1), referencias.
- **Sustentación**: 10 min de presentación + 5 min de preguntas; todos los integrantes participan.

Consigna completa: `Proyecto_analitica_BIO_20262.docx`.
