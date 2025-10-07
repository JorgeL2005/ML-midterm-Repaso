# Resumen Completo: Reducción de Dimensionalidad I

---

## 1. ¿Qué es la reducción de dimensionalidad?

-   Es el proceso de transformar datos de alta dimensión a un espacio de menor dimensión, preservando la mayor cantidad de información posible.
-   Ayuda a simplificar datos complejos, facilitar visualización, reducir ruido y mejorar rendimiento de algoritmos de Machine Learning.

---

## 2. ¿Por qué es importante?

-   **Maldición de la dimensionalidad:** A medida que aumenta la dimensión, el volumen del espacio crece exponencialmente y los datos se vuelven dispersos.
-   Esto dificulta:

    -   La generalización.
    -   El cálculo eficiente.
    -   La interpretación.

-   Reducir dimensionalidad combate estos problemas.

---

## 3. Tipos de reducción de dimensionalidad

-   **Métodos lineales:** Asumen que los datos se distribuyen cerca de un subespacio lineal de menor dimensión.
-   **Métodos no lineales:** Capturan estructuras complejas no lineales en los datos (no cubiertos en este PDF).

---

## 4. Principal Component Analysis (PCA)

-   Técnica no supervisada para identificar las direcciones (componentes principales) de mayor varianza en los datos.
-   Objetivo: proyectar los datos en un subespacio donde la varianza se maximiza.
-   Se buscan vectores ortogonales que representan las nuevas dimensiones.

---

### Funcionamiento de PCA

1. **Centralizar los datos:** Restar la media para centrar el conjunto en el origen.
2. **Calcular la matriz de covarianza** de los datos.
3. **Obtener eigenvectores y eigenvalores** de la matriz de covarianza.
4. **Seleccionar los $M$ eigenvectores** principales (con mayores eigenvalores).
5. **Proyectar los datos** originales en el subespacio formado por esos vectores.

---

### Propiedades de PCA

-   Maximiza la varianza proyectada.
-   Minimiza el error de reconstrucción.
-   Facilita la visualización y reduce ruido.

---

### Ejemplo

-   PCA aplicado a imágenes (como caras) puede reducir dimensiones manteniendo características relevantes.

---

## 5. Singular Value Decomposition (SVD)

-   Método alternativo para realizar PCA de forma numéricamente estable.
-   Descompone la matriz de datos en tres matrices: $U \Sigma V^T$.
-   Permite calcular componentes principales sin construir directamente la matriz de covarianza.
-   Es útil para datasets grandes o ruidosos.

---

## 6. Ventajas y limitaciones de PCA y SVD

| Ventajas                               | Limitaciones                            |
| -------------------------------------- | --------------------------------------- |
| Reduce dimensionalidad eficientemente  | Asume relaciones lineales               |
| Elimina redundancia y ruido            | Pierde interpretabilidad en componentes |
| Mejora rendimiento y evita overfitting | Sensible a outliers y escala de datos   |

---

## 7. Aplicaciones principales

-   Preprocesamiento para clasificación y regresión.
-   Visualización de datos en 2D o 3D.
-   Compresión y reducción de ruido.

---

## 8. Resumen final

-   La reducción de dimensionalidad es clave para trabajar con datos complejos.
-   PCA es la técnica lineal más popular para encontrar subespacios que capturan la mayoría de la información.
-   SVD es una herramienta matemática poderosa para implementar PCA de manera estable.
-   Estas técnicas mejoran eficiencia y ayudan a entender mejor los datos.
