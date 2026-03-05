# 03: Generadores Simétricos, Boosts y la Métrica de Minkowski
**Referencia:** [Grupos de Lie - Capítulo 3 (Javier García)](https://www.youtube.com/watch?v=lQyUySQLQKw)

---

### Descripción del Contenido
En este capítulo, se demuestra cómo un cambio aparentemente trivial en el generador de una transformación nos traslada de la geometría euclídea a la **Relatividad Especial de Einstein**. Javier García deriva la matriz de un **Boost** de Lorentz, introduce el concepto de **Métrica** ($\eta$) para definir invariantes con signos negativos y formaliza la **notación de índices** (vectores covariantes y contravariantes), estableciendo el lenguaje estándar de la física teórica.

---

## 1. El experimento: Cambiando el signo del Generador
Javier plantea un escenario: ¿Qué ocurre si en lugar del generador antisimétrico de las rotaciones ($B$), utilizamos un generador simétrico $K$?

$$
K = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}
$$

### Propiedad fundamental de $K$
A diferencia de las rotaciones donde $B^2 = -I$, para este nuevo generador se cumple que su cuadrado es la identidad:

$$
K^2 = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

Esto implica que cualquier potencia par de $K$ es $I$ ($K^2=I, K^4=I...$) y cualquier potencia impar es el propio $K$ ($K^3=K, K^5=K...$).

---

## 2. Derivación de la Matriz de Boost (Transformación de Lorentz)
Para obtener la transformación finita con parámetro $\omega$, aplicamos el mapa exponencial $L(\omega) = e^{\omega K}$. Desarrollando la serie de Taylor:

$$
L(\omega) = I + \omega K + \frac{\omega^2 K^2}{2!} + \frac{\omega^3 K^3}{3!} + \dots
$$

Separamos los términos que acompañan a la identidad ($I$) y al generador ($K$):

* **Parte con $I$ (potencias pares):** $1 + \frac{\omega^2}{2!} + \frac{\omega^4}{4!} + \dots = \cosh(\omega)$
* **Parte con $K$ (potencias impares):** $\omega + \frac{\omega^3}{3!} + \frac{\omega^5}{5!} + \dots = \sinh(\omega)$

La matriz resultante es el **Boost de Lorentz**:

$$
L(\omega) = \begin{pmatrix} \cosh \omega & \sinh \omega \\\\ \sinh \omega & \cosh \omega \end{pmatrix}
$$


---

## 3. El Invariante Relativista y la Métrica
Si aplicamos esta matriz a las coordenadas $(x^0, x^1)$, donde $x^0 = ct$ (tiempo) y $x^1 = x$ (espacio), la suma de cuadrados no se conserva. Sin embargo, usando la identidad $\cosh^2 \omega - \sinh^2 \omega = 1$, se demuestra que se conserva la **diferencia de cuadrados**:

$$
(x^0)^2 - (x^1)^2 = (x^{0'})^2 - (x^{1'})^2
$$

### Definición de la Métrica ($\eta$)
Para automatizar este signo negativo, introducimos la matriz métrica. Para el espacio-tiempo de Minkowski en 2D:

$$
\eta = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}
$$

El invariante se define ahora mediante la forma cuadrática $s^2 = \mathbf{x}^T \eta
