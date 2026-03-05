# Apuntes: Teoría de Grupos de Lie (Capítulo 2)
**Referencia:** [Grupos de Lie - Capítulo 2 (Javier García)](https://www.youtube.com/watch?v=AYygFmk80OA)

---

## 1. El concepto de Invarianza
En física teórica, un grupo de simetría se define por aquello que deja **invariante**. Javier comienza con el caso de una rotación en el plano $x-y$ que deja intacta la distancia al origen.

### El Invariante Cuadrático
Si tenemos un punto $P = (x_1, x_2)$, su distancia al cuadrado al origen es:
$$s^2 = x_1^2 + x_2^2$$

Queremos una transformación lineal $R$ tal que el nuevo punto $P' = (x_1', x_2')$ cumpla:
$$(x_1')^2 + (x_2')^2 = x_1^2 + x_2^2$$

### Notación Matricial
Definiendo el vector columna $\mathbf{x} = \begin{pmatrix} x_1 \\ x_2 \end{pmatrix}$, la distancia al cuadrado se escribe como:
$$\mathbf{x}^T \mathbf{x} = \begin{pmatrix} x_1 & x_2 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = x_1^2 + x_2^2$$

Si $\mathbf{x}' = R\mathbf{x}$, entonces la condición de invarianza es:
$$(R\mathbf{x})^T (R\mathbf{x}) = \mathbf{x}^T \mathbf{x}$$
$$\mathbf{x}^T (R^T R) \mathbf{x} = \mathbf{x}^T I \mathbf{x}$$

De aquí surge la **condición definitoria del grupo $O(2)$**:
$$R^T R = I$$

---

## 2. La Transformación Infinitesimal
Javier explica que las rotaciones son un **grupo continuo**. Esto nos permite estudiar la identidad ($I$) y lo que ocurre "justo al lado" mediante un parámetro $\epsilon$ muy pequeño.

$$R(\epsilon) \approx I + \epsilon A$$

### Restricción sobre el Generador $A$
Aplicamos la condición de ortogonalidad $R^T R = I$:
$$(I + \epsilon A)^T (I + \epsilon A) = I$$
$$(I^T + \epsilon A^T) (I + \epsilon A) = I$$
$$I + \epsilon A^T + \epsilon A + \epsilon^2 A^T A = I$$

Despreciando el término de segundo orden $\epsilon^2$ y simplificando la identidad:
$$\epsilon (A^T + A) = 0 \implies A^T = -A$$

> **Resultado Clave:** Los generadores de las rotaciones deben ser **matrices antisimétricas**.

---

## 3. Construcción del Generador en 2D
En 2 dimensiones, la matriz antisimétrica base (usando $k=1$ para normalizar el ángulo) es:
$$B = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$$



---

## 4. La Exponencial de una Matriz (Mapa Exponencial)
Para obtener una rotación finita $\theta$, acumulamos infinitos pasos infinitesimales:
$$R(\theta) = \lim_{N \to \infty} \left( I + \frac{\theta B}{N} \right)^N = e^{ \theta B }$$

### Desarrollo en Serie de Taylor
Para calcular $e^{\theta B}$, usamos la expansión:
$$e^{\theta B} = I + \theta B + \frac{\theta^2 B^2}{2!} + \frac{\theta^3 B^3}{3!} + \frac{\theta^4 B^4}{4!} + \dots$$

Observando las potencias cíclicas de $B$:
* $B^1 = B$
* $B^2 = -I$
* $B^3 = -B$
* $B^4 = I$

Sustituyendo y agrupando términos en $I$ y $B$:
$$R(\theta) = I \left( 1 - \frac{\theta^2}{2!} + \frac{\theta^4}{4!} - \dots \right) + B \left( \theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} - \dots \right)$$

Identificamos las series de Taylor del **Coseno** y el **Seno**:
$$R(\theta) = \cos(\theta) I + \sin(\theta) B$$



### Resultado Final (Matriz de Rotación)
$$R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

---

## 5. Resumen de Conceptos Clave
1. **Grupo de Lie ($SO(2)$):** El conjunto de matrices de rotación (la variedad geométrica).
2. **Álgebra de Lie ($\mathfrak{so}(2)$):** El conjunto de matrices antisimétricas (el espacio tangente en la identidad).
3. **Generador:** La derivada de la transformación en la identidad, que permite "reconstruir" todo el grupo mediante la exponencial.
