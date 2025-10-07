## Resumen: Regresión Polinomial, No Lineal y Regularización

---

### 1. **¿Qué es la regresión no lineal?**

-   Cuando un modelo lineal no es suficiente para ajustar los datos, usamos regresión no lineal.
-   Ejemplo clásico: regresión polinomial donde se incluyen potencias de la variable $x$:

    $$
    f(x) = w_0 + w_1 x + w_2 x^2 + \dots + w_M x^M
    $$

-   Se pueden combinar muchas transformaciones y variables para capturar relaciones complejas.

---

### 2. **Ajuste polinomial**

-   Al añadir términos polinomiales, el modelo puede ajustarse mejor a curvas complejas.
-   Riesgo: si el grado $M$ es muy alto, el modelo puede **sobreajustar** (overfitting) y perder capacidad de generalizar.
-   Esto sucede cuando el modelo también aprende el ruido, no sólo la señal.

---

### 3. **Generalización y sobreajuste**

-   La **generalización** es la capacidad del modelo para predecir bien nuevos datos.
-   Modelos muy complejos con pocos datos tienden a tener pesos muy grandes y sobreajustar.
-   Es necesario controlar la complejidad para mantener buen desempeño.

---

### 4. **Regularización**

-   Técnica para evitar sobreajuste añadiendo una penalización a la complejidad del modelo.
-   Se agrega un término en la función objetivo que penaliza los pesos grandes o la cantidad de variables usadas.
-   Función objetivo modificada:

    $$
    J(\theta) = \text{Error} + \lambda \times \text{Regularizador}
    $$

    donde $\lambda$ controla la fuerza de la penalización.

---

### 5. **Tipos principales de regularización y qué hace cada una**

#### a) **Regularización L0**

-   **¿Qué hace?** Penaliza directamente el número de coeficientes distintos de cero (cuántas variables están activas).
-   **Efecto:** Busca el modelo con el menor número posible de variables relevantes.
-   **Ventaja:** Realiza una selección de variables muy estricta, favoreciendo modelos simples y muy interpretables.
-   **Desventaja:** Es un problema combinatorio (no es diferenciable), difícil de resolver computacionalmente para problemas grandes.

---

#### b) **Regularización L1 (Lasso)**

-   **¿Qué hace?** Penaliza la suma de los valores absolutos de los pesos:

    $$
    \text{L1} = \sum |w_i|
    $$

-   **Efecto:** Promueve la **esparsidad** — hace que muchos pesos se vuelvan exactamente cero.
-   **Ventaja:** Selecciona automáticamente variables importantes y elimina las irrelevantes, facilitando interpretabilidad y reduciendo el ruido.
-   **Aplicación común:** Cuando se cree que sólo algunas variables realmente importan, o para reducir dimensionalidad.
-   **Optimización:** Puede ser resuelto eficientemente con técnicas específicas (e.g., métodos de optimización convexa).

---

#### c) **Regularización L2 (Ridge)**

-   **¿Qué hace?** Penaliza la suma de los cuadrados de los pesos:

    $$
    \text{L2} = \sum w_i^2
    $$

-   **Efecto:** Reduce el tamaño de todos los pesos, pero **no los anula**; los hace más pequeños para que ninguno domine.
-   **Ventaja:** Estabiliza el modelo, reduce la varianza y mejora la generalización.
-   **Aplicación común:** Cuando todas las variables tienen cierta relevancia y se quiere evitar coeficientes excesivamente grandes.
-   **Optimización:** Es diferenciable y fácil de resolver usando técnicas clásicas.

---

#### d) **Regularización ElasticNet**

-   **¿Qué hace?** Combina las penalizaciones L1 y L2:

    $$
    \text{ElasticNet} = \alpha \sum |w_i| + (1-\alpha) \sum w_i^2
    $$

    donde $\alpha \in [0,1]$ controla el balance entre L1 y L2.

-   **Efecto:** Une la capacidad de selección de variables de L1 con la estabilidad y control de magnitudes de L2.
-   **Ventaja:** Más flexible y potente que usar solo L1 o L2, se adapta mejor a datos reales complejos.
-   **Uso práctico:** Muy popular en la práctica, especialmente cuando no está claro cuál regularización es mejor.

---

### 6. **¿Por qué es importante la regularización?**

-   Reduce el **sobreajuste** y mejora la capacidad de generalización del modelo.
-   Controla la complejidad para evitar que el modelo aprenda ruido.
-   Facilita la interpretabilidad del modelo (especialmente con L1 y L0).
-   Estabiliza la solución y evita que los coeficientes tomen valores extremos.
-   Ajustar $\lambda$ (fuerza de la regularización) es clave: valores muy altos pueden subajustar; valores muy bajos no controlan el sobreajuste.

---

### 7. **Funciones no lineales más allá de polinomios**

-   Logaritmos, exponenciales, raíces cuadradas, sigmoides, etc.
-   En modelos multivariados, se pueden combinar potencias y términos cruzados:

    $$
    f(x) = w_0 + w_1 x_1 + w_2 x_1^2 + w_3 x_2 + w_4 x_2^2 + w_5 x_1 x_2 + \dots
    $$

-   Se pueden incorporar funciones no lineales de varias variables para modelar relaciones complejas.

---

### 8. **Ingeniería de características**

-   Clave en problemas complejos (texto, imágenes).
-   Técnicas como embeddings para texto o extracción automática en imágenes.
-   Mejora la representación y capacidad predictiva del modelo.

---
