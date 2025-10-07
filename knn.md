# Resumen Completo: Nearest Neighbors (Vecinos Más Cercanos)

---

## 1. ¿Qué es Nearest Neighbors (NN)?

-   Es un método para **clasificar** un nuevo dato basándose en la clase de los datos que ya conocemos.
-   No construye un modelo paramétrico; simplemente guarda todos los datos de entrenamiento.
-   La suposición: un dato nuevo tendrá la misma clase que sus datos más **cercanos**.

---

## 2. ¿Cómo funciona el algoritmo k-Nearest Neighbors (k-NN)?

-   $k$ es un número que define **cuántos vecinos más cercanos** se consideran para clasificar.
-   Para clasificar un nuevo dato $p$:

    1. Calculamos la distancia entre $p$ y todos los datos conocidos $a, b, c, ...$.
    2. Elegimos los $k$ datos más cercanos a $p$.
    3. La clase asignada a $p$ será la clase mayoritaria entre esos vecinos.

---

### Ejemplo simple

Nuevo punto $p$ y sus 3 vecinos más cercanos:

| Vecino | Clase   |
| ------ | ------- |
| $a$    | Manzana |
| $b$    | Manzana |
| $c$    | Naranja |

Con $k=3$, $p$ se clasifica como **Manzana** porque la mayoría de sus vecinos lo son.

---

## 3. Medición de distancia

-   Se usa la **distancia Euclidiana** para medir qué tan cerca están dos puntos:

$$
d(p, q) = \sqrt{\sum_{i=1}^D (p_i - q_i)^2}
$$

-   $p_i$ y $q_i$ son las características (atributos) del dato $p$ y $q$.
-   Por ejemplo, si un dato tiene altura y peso, la distancia es la raíz cuadrada de la suma de las diferencias al cuadrado en esas características.

---

## 4. ¿Qué son los límites de decisión?

-   Los límites de decisión son las **fronteras** en el espacio de características que separan distintas clases.
-   En k-NN, los límites se forman según los datos de entrenamiento y son **no lineales** y **muy flexibles**.
-   Para $k=1$, cada punto define una región llamada **celda de Voronoi**: todos los puntos dentro de esa región se clasifican igual que ese punto.
-   Para $k > 1$, los límites se vuelven más suaves, ya que se promedian las clases de varios vecinos.

---

## 5. Elección del parámetro $k$

-   Si $k=1$, la clasificación es muy sensible al ruido o datos atípicos.
-   Si $k$ es muy grande, la frontera se suaviza demasiado y puede mezclar clases diferentes.
-   Regla práctica: usar un $k$ menor que $\sqrt{n}$, donde $n$ es el total de datos.
-   La elección óptima se suele hacer con validación cruzada.

---

## 6. Importancia de la normalización

-   Las características pueden tener escalas muy diferentes (ej. peso en kg y altura en cm).
-   Sin normalización, las características con valores grandes dominan la distancia.
-   Se normalizan las características para que estén en la misma escala (por ejemplo, entre 0 y 1).

---

## 7. Problemas comunes y soluciones

| Problema                          | Solución                                             |
| --------------------------------- | ---------------------------------------------------- |
| Alta dimensionalidad              | Reducir características o usar técnicas de selección |
| Ruido en datos                    | Usar $k > 1$ para suavizar la predicción             |
| Cálculo lento en grandes datasets | Usar estructuras kd-trees o algoritmos aproximados   |

---

## 8. Ventajas y desventajas

| Ventajas                              | Desventajas                                       |
| ------------------------------------- | ------------------------------------------------- |
| Fácil de entender e implementar       | Lento para muchos datos                           |
| Funciona bien con fronteras complejas | Sensible a ruido y escalas                        |
| No necesita entrenamiento             | La distancia pierde significado en alta dimensión |

---

## 9. Diferencia con modelos lineales

-   Modelos lineales (regresión logística, SVM lineal) generan límites de decisión **planos o lineales**.
-   k-NN crea límites **curvos y adaptativos** que se ajustan a los datos locales.

---

## 10. Resumen final

-   k-NN clasifica nuevos datos según los vecinos cercanos guardados.
-   La elección de $k$ y la normalización son clave para un buen desempeño.
-   Es ideal para problemas con fronteras complejas, pero requiere cuidado con el ruido y la escala.

---
