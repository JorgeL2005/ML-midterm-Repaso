## Tipos de Aprendizaje en Machine Learning:

---

### 1. **Aprendizaje Supervisado (Supervised Learning)**

-   **Descripción General**:

    -   Aprende a predecir una salida específica basándose en datos etiquetados.
    -   Se busca reducir un error medido entre la predicción del modelo y la realidad.

-   **Entrada**:

    -   Datos etiquetados (por ejemplo: números, imágenes, texto o señales).

-   **Salida**:

    -   Un valor específico (booleano, numérico o categórico).

-   **Medida de error**:

    -   Cuantitativa, como Mean Squared Error (MSE), Mean Absolute Error (MAE) o Cross Entropy (para clasificación).

-   **Ejemplo**:

    -   Diagnóstico médico (predecir si un paciente tiene o no una enfermedad según sus atributos).

-   **Representación visual**:

    -   Un "maestro" proporciona respuestas correctas (Ground Truth), comparadas contra la predicción del "estudiante" (el modelo).

---

### 2. **Aprendizaje No Supervisado (Unsupervised Learning)**

-   **Descripción General**:

    -   Descubre patrones o estructuras intrínsecas en los datos sin etiquetas.
    -   No existe una referencia directa a un resultado esperado.

-   **Entrada**:

    -   Datos no etiquetados (números, imágenes, textos, señales).

-   **Salida**:

    -   Representaciones internas o agrupamientos (clústeres, vectores multidimensionales).

-   **Medida de error**:

    -   Intrínseca (busca patrones o agrupamientos naturales), basado en similitud o diferencia.

-   **Ejemplo**:

    -   Agrupar clientes según sus hábitos de compra, sin conocer categorías previamente.

-   **Representación visual**:

    -   El modelo intenta discernir por sí mismo lo que es similar o diferente.

---

### 3. **Aprendizaje por Refuerzo (Reinforcement Learning)**

-   **Descripción General**:

    -   Aprende a tomar decisiones mediante interacciones con el entorno para maximizar una recompensa acumulada.
    -   Basado en ensayo y error.

-   **Entrada**:

    -   Estado del entorno (descripción del contexto actual).

-   **Salida**:

    -   Una acción concreta en respuesta al estado actual.

-   **Medida de error**:

    -   Se mide en función del "arrepentimiento" (regret) respecto a la recompensa máxima posible.

-   **Ejemplo**:

    -   Un robot aprendiendo a navegar por un laberinto, eligiendo caminos que maximizan su recompensa (llegar rápido al objetivo).

-   **Representación visual**:

    -   No hay maestro explícito; el modelo aprende por recompensa (premio/castigo).

---

## Ejemplos Claros:

-   **Supervisado**:

    -   Diagnóstico de enfermedades cardíacas: Dados atributos médicos (edad, presión arterial, colesterol), predecir presencia o ausencia de enfermedad cardíaca.

-   **No Supervisado**:

    -   Segmentación de clientes: Clasificar automáticamente clientes según patrones de compra o comportamiento, sin etiquetas previas.

-   **Reforzado**:

    -   Juego de ajedrez automático: El sistema aprende jugadas óptimas interactuando continuamente con partidas y evaluando sus movimientos mediante recompensas.

---

## Información extra en el PDF:

Además de los tipos de aprendizaje, el documento aborda otros temas como:

-   **Funciones objetivo**: explica brevemente cómo se busca aproximar funciones objetivo desconocidas utilizando hipótesis y conjuntos de datos.
-   **Error del modelo**: Distinción entre error de entrenamiento (training error), error de prueba (test error) y error verdadero (error real sobre todos los posibles datos).
-   **Algoritmos específicos para clasificación**:

    -   Votación mayoritaria: Clasifica según la clase más frecuente en los datos.
    -   Memorizador: Clasifica usando coincidencias exactas de características en datos vistos previamente (error cero en entrenamiento).
    -   Decision Stump (tronco de decisión): Clasifica basado en una única característica específica, con un error mayor a cero pero más generalizable que el memorizador.

---

## En Resumen:

| **Tipo**       | **Entrada**         | **Salida**                                | **Etiquetas**           | **Medida de Error**           | **Ejemplo**           |
| -------------- | ------------------- | ----------------------------------------- | ----------------------- | ----------------------------- | --------------------- |
| Supervisado    | Datos etiquetados   | Valor específico (predicción)             | Sí                      | Cuantitativa (MSE, MAE)       | Diagnóstico médico    |
| No Supervisado | Datos sin etiquetar | Representaciones internas o agrupamientos | No                      | Intrínseca (similaridad)      | Segmentación clientes |
| Refuerzo       | Estado del entorno  | Acción concreta                           | No directa (recompensa) | Recompensa acumulada (Regret) | Juegos, Robots        |

---
