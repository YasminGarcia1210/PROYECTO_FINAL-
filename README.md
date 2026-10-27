# PROYECTO_FINAL

## Descripción general

Proyecto final de Analítica de Datos. Se desarrolla aplicando las fases de la metodología **CRISP-DM** en un contexto disciplinar específico, y se realiza **por carrera**: cada carrera aborda un problema propio de su área.

## Objetivos

1. Desarrollar un proyecto de analítica de datos aplicando las fases de la metodología CRISP-DM en un contexto disciplinar específico, desde la comprensión del problema hasta la evaluación de resultados.
2. Aplicar técnicas de preparación, exploración y modelado de datos para resolver un problema real, documentando las decisiones tomadas, los métodos utilizados y los resultados obtenidos.
3. Modelar, evaluar e interpretar los resultados del análisis en función del contexto del problema y proponer conclusiones o recomendaciones basadas en datos.
4. Comunicar los hallazgos del proyecto mediante un informe escrito y una presentación oral, demostrando claridad, rigor y capacidad de argumentación.

## Fases CRISP-DM

1. Comprensión del negocio / problema
2. Comprensión de los datos
3. Preparación de los datos
4. Modelado
5. Evaluación
6. Despliegue / comunicación de resultados

## Entregables

- Informe escrito
- Presentación oral

## Estructura de cada carpeta de carrera

```
CARRERA/
├── README.md          # Consigna resumida de la carrera
├── consigna/          # Documento original de la consigna (.docx / .pdf)
├── datos/             # Datos del proyecto (NO se suben a GitHub)
├── notebooks/         # Notebook(s) de Python con el análisis (.ipynb)
├── informe/           # Informe final (PDF o Word)
└── presentacion/      # Diapositivas de la sustentación (PDF)
```

Carpetas: `BIOLOGIA/`, `INDUSTRIAL/` y `ENER_INTELIGENTES/`. En la raíz también están `requirements.txt` (librerías: `pip install -r requirements.txt`) y `.gitignore`.

### Cómo entregar
1. Trabajen en la carpeta de su carrera (en un grupo, dentro de una subcarpeta con el nombre del equipo si hace falta).
2. Pongan el notebook en `notebooks/`, el informe en `informe/` y las diapositivas en `presentacion/`.
3. Guarden los datos en `datos/`: están ignorados por Git, así que no se suben.
4. Verifiquen que el notebook corre de principio a fin antes de entregar.

## Rúbrica de evaluación

Se evalúan 8 criterios en 4 niveles (Outstanding, Proficient, Developing, Beginning). La tabla completa está en [RUBRICA.md](RUBRICA.md).

1. Identificación y análisis de dilemas éticos (PI1)
2. Análisis de impactos globales, sociales, ambientales y económicos (PI2)
3. Formulación matemática del problema (PI3)
4. Estrategia de solución y justificación técnica
5. Aplicación rigurosa de fundamentos matemáticos (normalización, métricas, cálculos, funciones de pérdida, ángulos, etc.)
6. Análisis e interpretación de resultados
7. Conclusiones técnicas y coherencia general
8. Calidad del informe final (estructura, claridad, figuras, referencias, documentación)
