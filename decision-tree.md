# Resumen Completo: Árboles de Decisión (Decision Trees)

---

## 1. ¿Qué es un Árbol de Decisión?

-   Modelo para clasificación o regresión que divide datos mediante decisiones basadas en atributos.
-   Compuesto por:

    -   **Nodos internos:** pruebas de atributos.
    -   **Ramas:** posibles resultados de las pruebas.
    -   **Hojas:** clases o valores asignados.

---

## 2. Construcción del árbol

-   Construir el árbol óptimo es NP-completo.
-   Se usa un método **voraz (greedy)**:

    -   Elegir en cada paso el atributo que mejor divide los datos.
    -   Repetir recursivamente en los subconjuntos.

---

## 3. Selección del mejor atributo: métricas principales

---

### 3.1 Entropía

-   Fórmula para un conjunto con dos clases, con proporciones $p$ y $1-p$:

$$
H(p) = -p \log_2 p - (1-p) \log_2 (1-p)
$$

-   Mide la incertidumbre de la clase.
-   $H=0$ cuando todos los datos son de una misma clase.
-   $H=1$ cuando hay igual número de ambas clases.

---

**Ejemplo:**

Conjunto de 14 datos: 9 positivos, 5 negativos.

$$
p = \frac{9}{14} \approx 0.64
$$

$$
H = -0.64 \log_2 0.64 - 0.36 \log_2 0.36 \approx 0.94
$$

---

### 3.2 Ganancia de Información (Information Gain)

-   Reducción de entropía tras dividir por un atributo:

$$
IG(S, A) = H(S) - \sum_{v \in Values(A)} \frac{|S_v|}{|S|} H(S_v)
$$

-   Donde:

    -   $S$: conjunto original.
    -   $S_v$: subconjunto con valor $v$ del atributo $A$.
    -   $H(S)$, $H(S_v)$: entropías del conjunto original y del subconjunto.

---

### 3.3 Índice de Gini

-   Fórmula para un conjunto con clases con proporciones $p_i$:

$$
Gini = 1 - \sum_i p_i^2
$$

-   Para dos clases con proporciones $p$ y $1-p$:

$$
Gini = 1 - p^2 - (1-p)^2 = 2p(1-p)
$$

-   Mide la impureza del conjunto (0 = puro, máximo en 0.5 para dos clases).

---

**Ejemplo:**

Mismo conjunto de 14 datos, $p=0.64$:

$$
Gini = 2 \times 0.64 \times 0.36 = 0.46
$$

---

## 4. Límites de decisión

-   Los árboles dividen el espacio con límites **alineados a los ejes** (por ejemplo, $x_1 \leq 5$).
-   Generan regiones rectangulares que agrupan datos.
-   Esto facilita la interpretación pero limita la forma del límite.

---

## 5. Ventajas y limitaciones

| Ventajas                             | Limitaciones                         |
| ------------------------------------ | ------------------------------------ |
| Fácil de interpretar                 | Puede sobreajustar (overfitting)     |
| Maneja datos categóricos y numéricos | Límites no lineales limitados a ejes |
| Soporta clasificación multiclase     | Sensible a pequeñas variaciones      |

---

## 6. Métodos ensemble para mejorar el desempeño

-   **Random Forest:** muchos árboles con muestras y atributos aleatorios, luego se promedian resultados.
-   **Boosting (XGBoost):** árboles secuenciales que corrigen errores anteriores.
-   Reducen el sobreajuste y aumentan precisión.

---

## 7. Resumen final

-   Árboles de decisión crean reglas simples para dividir datos y clasificar.
-   Usan entropía o Gini para decidir mejores divisiones.
-   Métodos ensemble mejoran robustez y precisión.

---
