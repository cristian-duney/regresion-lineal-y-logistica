# Predicción de Calorías Quemadas con Modelos de Regresión y Clasificación
Este proyecto emplea modelos de regresión, como la **Regresión Lineal**, y modelos de clasificación, como la **Regresión Logística**, para analizar y predecir las calorías quemadas durante sesiones de ejercicio físico. A partir de variables clave como la **duración del ejercicio** y el pulso **máximo alcanzado**, se construye un modelo que permite estimar con precisión la cantidad de calorías quemadas en cada sesión. Además, este modelo se ajusta para clasificar las calorías quemadas en distintas categorías, facilitando un análisis más segmentado.

## Tabla de Contenidos
- [Objetivo](#objetivo)
- [Metodología](#metodología)
  - Modelo de Regresión Lineal
  - Modelo de Clasificación
- [Resultados](#resultados)
- [Conclusión](#conclusión)
- [Software](#software)
- [Instalación](#instalación)

## Objetivo
El objetivo de este proyecto es predecir las **calorías quemadas** durante sesiones de ejercicio mediante el uso de **modelos de regresión lineal**, tanto simple como múltiple. Adicionalmente, la variable de calorías se transforma en categorías específicas para implementar un modelo de **regresión logística**, permitiendo clasificar las sesiones según rangos de gasto calórico.

## Metodología
**Modelo de Regresión**

1. **Regresión Lineal Simple**:
   Se utiliza **Duración** como variable independiente para predecir las **Calorías quemadas**. El modelo obtiene la relación entre ambas variables y genera una predicción basada en la duración del ejercicio.

2. **Regresión Lineal Múltiple**:
   Se incluyen otras variables relevantes como **Máximo Pulso** para mejorar la predicción de las **Calorías quemadas**. Este modelo considera múltiples factores simultáneamente para hacer predicciones más precisas.

   - **Ecuación del modelo**: 
     - Regresión Lineal Simple: 
        - `Calories = Intercepto + Coeficiente * Duration`
     - Regresión Lineal Múltiple:
       - `Calories = Intercepto + Coef1 * Duration + Coef2 * Pulse + Coef3 * Maxpulse`

**Modelo de Clasificación**  

Para la clasificación de las **Calorías quemadas**, se transforma la variable continua de calorías en categorías (Baja, Media, Alta), utilizando técnicas como la discretización de valores.

**Pasos de clasificación**:
- Definir las categorías de calorías (Baja, Media, Alta).
- Asignar cada observación a una de estas categorías según la cantidad de calorías quemadas.
- Utilizar como modelo de clasificación la **Regresión Logística** para predecir la categoría.

## Resultados
**Resultados del Modelo de Regresión**

- **Regresión Lineal Simple**:
  - **Coeficiente**: 5.75
  - **Intercepto**: 5.22
  - **Error Cuadrático Medio (MSE)**: 8245.55
  - **R² (Coeficiente de Determinación)**: 0.74
  - **Calorías Predichas**: 408.11

  **Interpretación**: El modelo de regresión lineal simple muestra que la **Duración** tiene una relación positiva con las **Calorías quemadas**, aunque la precisión no es tan alta (con un R² de 0.74). Esto significa que aproximadamente el 74.7% de la variabilidad en las calorías quemadas puede ser explicada por la duración del ejercicio.

- **Regresión Lineal Múltiple**:
  - **Coeficientes**: 5.71 (Duración), 2.99 (Maximo Pulso)
  - **Intercepto**: -393.44
  - **Error Cuadrático Medio (MSE)**: 3558.03
  - **R² (Coeficiente de Determinación)**: 0.89
  - **Calorías Predichas**: 425.43

  **Interpretación**: En el modelo de regresión lineal múltiple, al incluir tanto la **Duración** como el **Maximo Pulsos**, la predicción de las **Calorías quemadas** mejora considerablemente, alcanzando un R² de 0.89. Esto indica que este modelo explica aproximadamente el 89% de la variabilidad en las calorías quemadas, lo que representa una mejora con respecto al modelo simple.

**Resultados del Modelo de Clasificación**

- **Regresión Logistica**:
  - **Exactitud del modelo**: 0.84 (84%) 
  - **Reporte de clasificación**:
  
  | Clase | Precision | Recall | F1-Score | Support |
  |-------|-----------|--------|----------|---------|
  | 0     | 1.00      | 0.67   | 0.80     | 6       |
  | 1     | 0.67      | 0.80   | 0.73     | 5       |
  | 2     | 0.87      | 0.91   | 0.89     | 22      |  
- **Matriz de confusión**:
   
|Clase real \ Clase Predicha | Clase 0 | Clase 1 | Clase 2 |
|---------------|-------------|-------------|-------------|
| **Clase 0** | 4           | 0           | 2           |
| **Clase 1** | 0           | 4           | 1           |
| **Clase 2** | 0           | 2           | 20          |

**Interpretación**:
El modelo de clasificación **Regresión Logística** tiene una **precisión del 84%**, lo que significa que en el 84% de los casos el modelo clasifica correctamente las categorías de calorías (Baja, Media, Alta). El **F1-Score** promedio ponderado es alto, especialmente para la clase 2 (Alta), lo que indica que el modelo es bastante bueno al predecir esta categoría.

**Diferencia entre Regresión y Clasificación**
| Aspecto           | Regresió                          | Clasificación                              |
|--------------------|-----------------------------------------|----------------------------------------|
| **Variable objetivo** | Numérica continua (por ejemplo, 300 calorías)  | Categórica (por ejemplo, "Baja", "Media") |
| **Tarea del modelo**   | Predecir un valor numérico específico        | Asignar categorías a instancias |
| **Ejemplo de salida**  | Valor exacto: 375,5                         | Clase "Alta"                   |

## Conclusión
- Si el objetivo es predecir el valor exacto de calorías:
El modelo de regresión lineal múltiple es el mejor, ya que tiene un menor error (MSE) y un ajuste más alto (R² = 89%).

- Si el objetivo es clasificar las sesiones en rangos de calorías:
La clasificación con regresión logística sería la mejor opción, dado que tiene un buen desempeño en términos de precisión y F1-Score (84%).

## Software
**Requisitos**
1. Python 3.x
2. Visual Studio Code
3. Jupyter notebook
2. Bibliotecas necesarias:
   - `pandas`
   - `plotly`
   - `scikit-learn`

## Instalación
```bash
pip install pandas plotly scikit-learn

