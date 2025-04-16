## Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Dataset](#dataset)
- [Proceso de trabajo](#proceso-de-trabajo)
- [Resultados finales](#resultados-finales-y-decisión-del-modelo)
- [Conclusión](#conclusión)

# Proyecto de Clasificación: Detección de Enfermedades Cardíacas con Machine Learning
##  Descripción del Proyecto
Este proyecto tiene como objetivo desarrollar un modelo de Machine Learning capaz de predecir si un paciente presenta enfermedad cardíaca, utilizando datos clínicos. La solución está orientada como sistema de apoyo al diagnóstico médico.

## Dataset
- **Origen**: UCI Heart Disease Dataset
- **Instancias**: 920 pacientes
- **Etiquetas**: `0` (sano), `1` (enfermo)
- **Variables**: edad, sexo, tipo de dolor torácico, presión, colesterol, etc.

##  Proceso de trabajo

### 1. Carga y exploración del dataset
- Revisión de tipos, valores nulos y distribuciones.
- Transformación de la variable `num` a `target` binaria (`0`: sano, `1`: enfermo).

### 2. Preprocesamiento
- Eliminación de columnas irrelevantes (`id`, `num`).
- Imputación de valores nulos con la media.
- Codificación de variables categóricas (One-Hot Encoding).
- Escalado de variables numéricas (StandardScaler).

### 3. Análisis exploratorio (EDA)
- Gráficos: countplot, boxplots, histograma, heatmap.
- Análisis de correlación y multicolinealidad.

### 4. Modelado y comparación de modelos
- Modelos evaluados:
  - Logistic Regression
  - K-Nearest Neighbors
  - Random Forest
- Métricas utilizadas: Accuracy, Recall, F1-score
- Validación cruzada + GridSearchCV para optimización

### 5. Evaluación del mejor modelo (Random Forest)
- **Accuracy**: 0.8261
- **F1-score clase 1**: 0.85
- **AUC ROC**: ~0.92

### 6. Visualizaciones clave
- Matriz de confusión normalizada
- Importancia de características
- Curva ROC
- PCA (2D) para distribución de clases

### 7. Predicción simulada
- Se seleccionó un paciente aleatorio del conjunto de prueba.
- Se mostró la predicción, la clase real y la probabilidad de enfermedad.

## Resultados finales y decisión del modelo

| Modelo                | Accuracy | F1-score (Clase 1) | Recall (Clase 1) |
|----------------------|----------|--------------------|------------------|
| Random Forest        | 0.83     | 0.85               | 0.86             |
| KNN                  | 0.86     | 0.88               | **0.91**         |
| Logistic Regression  | 0.84     | 0.86               | 0.90             |

**Modelo elegido: Random Forest**
Por su equilibrio entre rendimiento, robustez, interpretabilidad y facilidad para analizar la importancia de variables.

## Conclusión
El modelo desarrollado ofrece un buen rendimiento para tareas de clasificación binaria aplicadas a diagnóstico clínico. Puede ser utilizado como sistema de apoyo al profesional médico en decisiones tempranas sobre enfermedades cardíacas.

Este proyecto demuestra el uso completo de un flujo de Machine Learning: desde exploración y preprocesamiento hasta evaluación y visualización.

---
**Autor:** Alejandro Fuentes
**Curso:** Máster en Inteligencia Artificial  
**Módulo:** Machine Learning

