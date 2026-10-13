# Análisis de Sentimientos con Minería de Datos

Proyecto académico de minería de datos enfocado en el análisis de sentimientos de comentarios en español mediante técnicas de procesamiento de texto y aprendizaje automático.

## Descripción

El objetivo del proyecto es analizar comentarios relacionados con pseudociencias y prácticas alternativas, clasificándolos en tres categorías: **Positivo, Negativo y Neutral**.

Para ello, se integran dos fuentes de información: un conjunto de datos original y comentarios recopilados de YouTube. Posteriormente, se limpian y procesan los textos para comparar diferentes métodos de clasificación de sentimientos.

## Objetivos

- Integrar y limpiar conjuntos de datos de texto.
- Aplicar técnicas de preprocesamiento de lenguaje natural.
- Representar comentarios mediante una matriz de características de texto.
- Comparar métodos de clasificación de sentimientos.
- Evaluar los modelos mediante accuracy, precision, recall, F1-score y validación cruzada.
- Visualizar la distribución de sentimientos, las palabras frecuentes y las matrices de confusión.

## Tecnologías utilizadas

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Expresiones regulares (Regex)

## Conjuntos de datos

El proyecto combina dos fuentes:

| Fuente | Comentarios |
|---|---:|
| Dataset original | 15,705 |
| Comentarios de YouTube después de la limpieza | 4,499 |
| **Total combinado** | **20,204** |

Los datos se procesan para normalizar los comentarios y preparar las características utilizadas por los métodos de análisis.

## Metodología

1. **Carga de datos:** lectura de los archivos CSV originales y de comentarios de YouTube.
2. **Limpieza de texto:** conversión a minúsculas, normalización de abreviaciones, eliminación de enlaces y caracteres no deseados.
3. **Etiquetado de sentimientos:** utilización de las categorías Positivo, Negativo y Neutral.
4. **Vectorización:** transformación de los textos en una matriz de características mediante `CountVectorizer`.
5. **División de datos:** separación en conjuntos de entrenamiento y prueba.
6. **Entrenamiento:** aplicación de cuatro métodos de clasificación.
7. **Evaluación:** comparación de resultados y validación cruzada de cinco particiones para Naive Bayes y Regresión Logística.
8. **Visualización:** generación de gráficas de distribución, comparación de modelos, matrices de confusión y palabras frecuentes.

## Resultados

Los siguientes resultados corresponden a la ejecución del notebook con el conjunto de datos combinado.

| Método | Accuracy |
|---|---:|
| Método Lexicon (diccionario) | 54.34% |
| Naive Bayes | 77.88% |
| Regresión Logística | 86.21% |
| Regresión Lineal | 69.68% |

### Mejor resultado

La **Regresión Logística** obtuvo el mayor accuracy reportado, con **86.21%** sobre el conjunto de prueba.

En la validación cruzada de cinco particiones, los resultados reportados fueron:

- Naive Bayes: 78.21% ± 0.75%.
- Regresión Logística: 86.05% ± 0.55%.

Estos resultados permiten comparar el desempeño de los métodos evaluados dentro de este experimento. No garantizan la misma precisión en otros conjuntos de datos.

## Estructura del proyecto

```text
analisis-sentimientos-mineria-datos/
├── proyecto_analisis_sentimientos.ipynb
├── dataset.csv
├── comentarios_youtube_limpios.csv
├── README.md
├── requirements.txt
└── .gitignore
```

Los archivos CSV deben incluirse únicamente si se cuenta con autorización para compartirlos. Si no están disponibles públicamente, consulta la sección de ejecución para conocer el ajuste necesario.

## Instalación y ejecución

### 1. Clonar el repositorio

```bash
git clone https://github.com/TU-USUARIO/analisis-sentimientos-mineria-datos.git
cd analisis-sentimientos-mineria-datos
```

Sustituye `TU-USUARIO` por tu nombre de usuario de GitHub.

### 2. Crear un entorno virtual (opcional, recomendado)

```bash
python -m venv .venv
```

En Windows:

```bash
.venv\Scripts\activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Ejecutar el notebook

Abre `proyecto_analisis_sentimientos.ipynb` en Jupyter Notebook, JupyterLab o Google Colab y ejecuta las celdas en orden.

Los archivos `dataset.csv` y `comentarios_youtube_limpios.csv` deben estar en la ubicación que espera el notebook para reproducir los resultados originales. Si no se incluyen, será necesario proporcionar los datos autorizados o adaptar la carga de archivos.

## Limitaciones

- Los resultados dependen de la calidad y representatividad de los datos utilizados.
- La limpieza de texto puede eliminar información contextual relevante.
- La clasificación de sentimientos puede presentar dificultades con ironías, negaciones y expresiones ambiguas.
- El accuracy por sí solo no describe completamente el rendimiento de un clasificador; también deben considerarse las métricas por clase.
- Los resultados son experimentales y no constituyen una evaluación de la eficacia médica de las prácticas mencionadas en los comentarios.

## Autoría

Proyecto académico desarrollado como parte de la asignatura de Minería de Datos.

## Estado del proyecto

Proyecto académico funcional en su versión actual, susceptible de mejoras en el preprocesamiento, la selección de características, la evaluación y la reproducibilidad de los experimentos.
