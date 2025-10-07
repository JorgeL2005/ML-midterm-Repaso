# Resumen Completo: Support Vector Machines (SVM)

## 1. Introducción y relación con regresión logística

-   SVM es un algoritmo supervisado para clasificación binaria, con etiquetas $t^{(i)} \in \{+1, -1\}$.
-   A diferencia de la regresión logística, que genera una frontera de decisión basada en probabilidades, SVM busca la frontera que **maximiza el margen** entre clases para mejorar la capacidad de generalización.

## 2. SVM Lineal: Margen máximo y frontera óptima

-   Busca un hiperplano lineal:

    $$
    \mathbf{w}^T \mathbf{x} + b = 0
    $$

-   Define dos hiperplanos de soporte paralelos:

    $$
    \mathbf{w}^T \mathbf{x} + b = +1 \quad \text{y} \quad \mathbf{w}^T \mathbf{x} + b = -1
    $$

-   Estos tocan los vectores soporte, puntos de datos más cercanos a la frontera.

-   El margen es la distancia entre estos dos hiperplanos:

    $$
    \text{Margen} = \frac{2}{\|\mathbf{w}\|}
    $$

-   La restricción de clasificación correcta y margen mínimo es:

    $$
    t^{(i)} (\mathbf{w}^T \mathbf{x}^{(i)} + b) \geq 1
    $$

## 3. Transformación de maximización a minimización

-   Maximizar el margen es equivalente a minimizar $\frac{1}{2} \|\mathbf{w}\|^2$.

-   Así, el problema se formula:

    $$
    \min_{\mathbf{w}, b} \frac{1}{2} \|\mathbf{w}\|^2
    \quad \text{sujeto a} \quad
    t^{(i)} (\mathbf{w}^T \mathbf{x}^{(i)} + b) \geq 1
    $$

-   Se resuelve mediante multiplicadores de Lagrange y optimización convexa.

## 4. SVM con margen suave (Soft Margin)

-   Para datos no perfectamente separables, se introducen variables de holgura $\xi_i \geq 0$:

    $$
    t^{(i)} (\mathbf{w}^T \mathbf{x}^{(i)} + b) \geq 1 - \xi_i
    $$

-   La función objetivo penaliza errores y minimiza el margen:

    $$
    \min_{\mathbf{w}, b, \xi} \frac{1}{2} \|\mathbf{w}\|^2 + \lambda \sum_i \xi_i
    $$

-   El parámetro $\lambda$ regula el balance entre margen amplio y tolerancia a errores.

## 5. Ejemplos de casos prácticos

-   Datos perfectamente separables: $\xi_i = 0$, margen máximo.
-   Algunos puntos dentro del margen o mal clasificados: $\xi_i > 0$, penalizados en la función objetivo.
-   Ajustar $\lambda$ cambia la rigidez del modelo frente a errores.

## 6. SVM No Lineal y el truco del kernel

-   Los datos no linealmente separables se transforman con $\phi(\mathbf{x})$ a un espacio de mayor dimensión donde se puede encontrar un hiperplano separador lineal.
-   La formulación dual permite usar solo productos internos $\phi(\mathbf{x}_i)^T \phi(\mathbf{x}_j)$.
-   El **truco del kernel** usa funciones kernel $K(\mathbf{x}_i, \mathbf{x}_j)$ que calculan estos productos sin necesidad del mapeo explícito.
-   Esto hace eficiente la clasificación no lineal.

## 7. Tipos de kernels y su aplicación práctica

-   **Kernel Lineal:**

    -   Función: $K(\mathbf{x}_i, \mathbf{x}_j) = \mathbf{x}_i^T \mathbf{x}_j$.
    -   Útil cuando los datos son aproximadamente linealmente separables o cuando la dimensionalidad es muy alta.
    -   En la práctica, es rápido y simple, ideal para texto o datos con muchas características.

-   **Kernel Polinomial:**

    -   Función: $K(\mathbf{x}_i, \mathbf{x}_j) = (\gamma \mathbf{x}_i^T \mathbf{x}_j + r)^d$, donde $\gamma > 0$, $r$ es un coeficiente y $d$ es el grado del polinomio.
    -   Permite aprender límites de decisión con formas polinomiales.
    -   En la práctica, útil cuando se sospecha relaciones no lineales de bajo orden entre las características.
    -   Puede ser computacionalmente más costoso a medida que $d$ aumenta.

-   **Kernel RBF (Radial Basis Function) o Gaussiano:**

    -   Función: $K(\mathbf{x}_i, \mathbf{x}_j) = \exp(-\gamma \|\mathbf{x}_i - \mathbf{x}_j\|^2)$, con $\gamma > 0$.
    -   Mapea a un espacio infinito dimensional, capaz de aprender fronteras muy flexibles y complejas.
    -   Es el kernel más popular y efectivo en problemas reales con relaciones altamente no lineales.
    -   En la práctica, requiere ajuste cuidadoso de $\gamma$ y $\lambda$ para evitar overfitting o underfitting.

-   **Otras kernels:**

    -   Sigmoide, laplaciano, entre otros, adaptados a casos específicos.
    -   Menos comunes pero útiles en dominios particulares.

### Visualización en práctica:

-   Con kernel lineal, la frontera es un hiperplano plano.
-   El kernel polinomial genera curvas suaves con cierto grado de complejidad (curvas polinomiales).
-   El kernel RBF produce fronteras muy flexibles y no lineales, que se adaptan a la forma de los datos, pero pueden ser menos interpretables.

## 8. Consideraciones finales

-   SVM ofrece una solución sólida para clasificación con una formulación matemática clara.
-   El margen suave y los kernels permiten manejar datos ruidosos y no lineales.
-   El rendimiento depende en gran medida de la selección y ajuste del kernel y parámetros.
-   Para datasets muy grandes, el entrenamiento puede ser costoso, por lo que se buscan optimizaciones y aproximaciones.

---

# Conceptos Clave

-   **Hiperplanos soporte:** $\mathbf{w}^T \mathbf{x} + b = \pm 1$, definen el margen.
-   **Variables de holgura $\xi_i$:** permiten errores para datos no separables.
-   **Función objetivo:** minimiza $\frac{1}{2}\|\mathbf{w}\|^2 + \lambda \sum \xi_i$.
-   **Kernel trick:** cálculo eficiente en espacios de alta dimensión sin mapeo explícito.
-   **Tipos de kernel:** lineal, polinomial, RBF y otros, cada uno con aplicaciones prácticas y complejidades distintas.
-   **Vectores soporte:** puntos clave que definen la frontera.

---
