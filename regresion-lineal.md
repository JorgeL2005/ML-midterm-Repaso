## 📌 **Concepto de Regresión**:

-   La regresión es un método para **ajustar curvas a los datos**.
-   Se utiliza para predecir un **valor numérico** en lugar de una clase (como en clasificación).
-   La forma general de una regresión lineal es:

    $$
    f(x) = wx + b
    $$

    Donde:

    -   $w$ es el coeficiente o pendiente de la línea.
    -   $b$ es el sesgo o intercepto en el eje $y$.

---

## 🏡 **Ejemplos Comunes**:

1. **Precio de una casa**:

    - Predecir el valor de una casa con base en características como el tamaño, ubicación, número de habitaciones, etc.

2. **Cantidad de seguidores en redes sociales**:

    - Predecir el número de seguidores según la actividad y el alcance de las publicaciones.

3. **Predicción de ventas**:

    - Estimar las ventas futuras de un producto según datos históricos.

---

## ⚙️ **Función de Pérdida (Loss Function) vs Métrica (Metric)**:

-   La **función de pérdida (Loss Function)** es lo que el modelo intenta minimizar durante el entrenamiento.

    -   Ejemplos: **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**.

-   Las **métricas (Metrics)** son utilizadas por las personas para evaluar el rendimiento del modelo, pero **no influyen en el entrenamiento**.

    -   Ejemplo: **R² (Coeficiente de determinación)** para medir qué tan bien se ajusta el modelo.

---

## 🔎 **Métricas Comunes para Regresión**:

1. **Mean Squared Error (MSE)**:

    $$
    MSE = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y_i})^2
    $$

    - Penaliza más los errores grandes, ya que están elevados al cuadrado.

2. **Mean Absolute Error (MAE)**:

    $$
    MAE = \frac{1}{n} \sum_{i=1}^n |y_i - \hat{y_i}|
    $$

    - Penaliza de forma lineal, es más robusto a outliers.

---

## 📈 **Regresión Lineal Simple**:

-   Se ajusta una línea recta para modelar la relación entre una **variable independiente (x)** y una **dependiente (y)**.
-   El objetivo es encontrar los mejores valores para $w$ (pendiente) y $b$ (intercepto) que minimicen el error.

**Ejemplo**:

-   Queremos predecir el precio de un auto en función de su antigüedad.

    -   Si un auto tiene 5 años, el modelo podría predecir un valor aproximado de acuerdo a la línea ajustada.

---

## 🗺️ **Regresión Lineal Multidimensional**:

-   Se extiende el concepto para múltiples variables independientes.
-   La fórmula general es:

    $$
    f(x) = w_0 + w_1x_1 + w_2x_2 + ... + w_nx_n
    $$

    -   $w_0$ es el sesgo.
    -   Los demás $w_i$ son los pesos correspondientes a cada característica.
    -   Cada **x** representa una característica del dataset.

**Ejemplo**:

-   Predicción del precio de una casa en función de:

    -   Tamaño (m²),
    -   Número de habitaciones,
    -   Localización,
    -   Antigüedad, etc.

---

## 🧮 **Optimización del Modelo: Descenso de Gradiente (Gradient Descent)**:

-   Es el método usado para minimizar la función de pérdida.
-   **Paso a paso**:

    1. Se calculan las predicciones del modelo.
    2. Se mide el error (MSE o MAE).
    3. Se ajustan los pesos $w$ y el sesgo $b$ para reducir ese error.
    4. Se repite hasta encontrar el mínimo.

**Tipos de Descenso de Gradiente**:

1. **Batch Gradient Descent**:

    - Se actualizan los pesos utilizando todo el conjunto de datos en cada iteración.

2. **Stochastic Gradient Descent (SGD)**:

    - Los pesos se actualizan para cada muestra, lo que lo hace más rápido pero ruidoso.

---

## 📝 **Resumen General**:

| **Concepto**                             | **Descripción**                                                      | **Ejemplo**                                                          |
| ---------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Regresión Lineal Simple**              | Relación entre una sola variable independiente y una dependiente.    | Predecir el precio de un auto según su antigüedad.                   |
| **Regresión Lineal Múltiple**            | Relación entre múltiples variables independientes y una dependiente. | Estimar el precio de una casa en función del tamaño, ubicación, etc. |
| **Función de Pérdida (MSE, MAE)**        | Métrica que el modelo minimiza para mejorar la predicción.           | MSE penaliza más los errores grandes.                                |
| **Optimización (Descenso de Gradiente)** | Método iterativo para ajustar los pesos del modelo.                  | SGD ajusta los pesos en cada muestra.                                |

---
