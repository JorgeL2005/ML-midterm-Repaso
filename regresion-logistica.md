# Resumen de Regresión Logística

## 1. Introducción a la Regresión Logística

La regresión logística es un modelo utilizado para problemas de clasificación binaria, donde la variable objetivo sólo puede tomar dos valores, como aprobar o reprobar un examen. A diferencia de la regresión lineal, que predice valores continuos, la regresión logística predice la probabilidad de que una observación pertenezca a una clase específica.

## 2. Formalización del Modelo

Para modelar esta probabilidad, se usa la función sigmoide o logística, que transforma la combinación lineal de las variables predictoras en un valor entre 0 y 1:

$$
\sigma(z) = \frac{1}{1 + e^{-z}}, \quad \text{donde } z = w^T x + w_0
$$

Los parámetros $w$ son los pesos asignados a cada característica, y $w_0$ es un término de sesgo. Las características pueden ser continuas o discretas, y el resultado $\sigma(z)$ representa la probabilidad estimada de la clase positiva.

## 3. Interpretación Probabilística y Decisión

El modelo estima la probabilidad condicional de que la clase sea 1 dado el vector de características $x$:

$$
p(C=1|x) = \sigma(w^T x + w_0)
$$

Para tomar una decisión, se fija un umbral (usualmente 0.5): si la probabilidad es mayor que el umbral, se asigna la clase positiva; de lo contrario, la negativa. La frontera de decisión que separa ambas clases es lineal en el espacio de características.

## 4. Aprendizaje por Máxima Verosimilitud

Para aprender los parámetros $w$, se define la función de verosimilitud, que representa la probabilidad de observar las etiquetas dadas las entradas y el modelo:

$$
L(w) = \prod_{i=1}^N P(t^{(i)} | x^{(i)}; w)
$$

Como las muestras se asumen independientes, la verosimilitud es el producto de las probabilidades de cada ejemplo.

Maximizar esta función directamente puede ser complejo debido al producto de muchas probabilidades, por lo que se trabaja con su logaritmo, transformando el producto en una suma, lo que simplifica los cálculos:

$$
\log L(w) = \sum_{i=1}^N \log P(t^{(i)} | x^{(i)}; w)
$$

El objetivo es encontrar los pesos $w$ que **maximicen** esta log-verosimilitud, es decir, que hagan que el modelo explique mejor los datos observados.

Sin embargo, en optimización es común trabajar con problemas de **minimización**. Para adaptar el problema, se toma el negativo de la log-verosimilitud y se define la función de pérdida como:

$$
\text{Loss}(w) = - \log L(w)
$$

Minimizar esta función de pérdida equivale exactamente a maximizar la verosimilitud original, pero facilita el uso de algoritmos de optimización estándar, como el descenso por gradiente, que están diseñados para encontrar mínimos de funciones.

Esta función de pérdida es conocida como **cross-entropy loss** o pérdida de entropía cruzada, y penaliza fuertemente las predicciones incorrectas.

## 5. Optimización mediante Descenso por Gradiente

Con la función de pérdida definida, el entrenamiento del modelo consiste en encontrar el vector de pesos $w$ que minimiza esta pérdida. Para esto, se utiliza el algoritmo de descenso por gradiente, que actualiza iterativamente los pesos en la dirección opuesta al gradiente (la pendiente) de la función de pérdida, es decir, moviéndose hacia donde la pérdida disminuye más rápido.

La actualización para cada peso $w_j$ se calcula usando la diferencia entre la predicción del modelo y la etiqueta real, multiplicada por el valor de la característica correspondiente.

Este proceso se repite hasta converger a un mínimo local o cumplir algún criterio de parada.

## 6. Regularización (Breve Mención)

Para evitar que el modelo se ajuste demasiado a los datos de entrenamiento (sobreajuste), se pueden añadir términos de regularización a la función de pérdida, tales como:

-   L1 (Lasso): promueve que muchos pesos sean cero, ayudando en la selección de características.
-   L2 (Ridge): penaliza pesos grandes, favoreciendo soluciones más estables.
-   ElasticNet: combina L1 y L2 para obtener beneficios de ambos.

## 7. Métricas de Evaluación

Para medir el desempeño del modelo se usa la matriz de confusión, que clasifica las predicciones en:

-   Verdaderos Positivos (TP)
-   Falsos Positivos (FP)
-   Verdaderos Negativos (TN)
-   Falsos Negativos (FN)

De esta matriz se derivan métricas importantes:

-   **Exactitud (Accuracy):** proporción de predicciones correctas sobre el total.
-   **Precisión (Precision):** proporción de predicciones positivas que fueron correctas.
-   **Recall (Sensibilidad):** proporción de positivos reales que fueron correctamente detectados.
-   **F1 Score:** media armónica entre precisión y recall, útil cuando las clases están desbalanceadas.

## 8. Actividad Práctica

El PDF incluye un ejemplo práctico donde se predice si un estudiante aprobará un examen en función del número de horas estudiadas. Se entrena el modelo para ajustar los pesos $w$ y luego se usa para predecir probabilidades y clasificar nuevos casos.

## 9. Ventajas y Limitaciones

Entre las ventajas de la regresión logística destacan que es un modelo interpretable, rápido de entrenar y resistente al sobreajuste si se regulariza correctamente. Además, proporciona una interpretación probabilística natural de las predicciones.

Como limitaciones, el modelo sólo puede producir fronteras de decisión lineales, por lo que puede no ser adecuado para problemas con relaciones complejas y no lineales entre variables.

---
