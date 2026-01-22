# 📓 Bitácora: [Asignatura]

<details>
<summary><b>📅 21/01/2026: Inicio de la asignatura antes de que empieze el Máster</b> (Clic para expandir)</summary>

- **Idea:** Examinar bibliografría, y lectura en diagonal de la misma.
- **Ajá!:** Reflexión: Grupos de Lie, Simetrías y la Naturaleza de las EDOs</b></summary>

Tras estos días estudiando la primera parte de la asignatura, mi impresión principal es que los **Grupos de Lie** son 
la llave para resolver ecuaciones diferenciales con solución analítica exacta de forma **sistemática**. Es fascinante
ver cómo Lie convirtió lo que antes era un simple "catálogo de trucos" (donde resolvías según la forma de la ecuación) 
en una verdadera **ciencia de simetrías**.

Me ha parecido revelador entender que podemos rotar elementos no solo mediante ángulos discretos o matrices fijas —que
son como una "foto" del estado final—, sino de forma **diferencial e infinitesimal**. Es la diferencia entre ver el
resultado y entender el "generador" del movimiento (el Álgebra de Lie).

Lo que me resulta más maravilloso es ver cómo las rotaciones, traslaciones y elongaciones nos ayudan a encontrar 
simetrías que, conectadas con el **Teorema de Noether**, revelan cantidades conservadas como la energía, el momento
lineal o el momento angular. Al final, todo encaja: la geometría del universo dicta las leyes de la física y, al
encontrar esas simetrías en las ecuaciones diferenciales, puedo resolverlas de manera estructurada y profunda.
</details>

<details>
<summary><b>📅 21/01/2026: Formulario Maestro: Simetrías de Lie y Resolución de EDOs</b></summary>

### 1. El Generador Infinitesimal ($\mathbf{X}$)
Para una EDO $y' = f(x,y)$, el generador define la transformación infinitesimal:
$$\mathbf{X} = \xi(x, y) \frac{\partial}{\partial x} + \eta(x, y) \frac{\partial}{\partial y}$$

### 2. Simetrías Estándares (Candidatos comunes)
Cuando no conocemos $\xi$ y $\eta$, probamos estos "moldes" geométricos:

| Transformación | $\xi(x, y)$ | $\eta(x, y)$ | Efecto Geométrico |
| :--- | :---: | :---: | :--- |
| **Traslación en $x$** | $1$ | $0$ | Desplazamiento horizontal |
| **Traslación en $y$** | $0$ | $1$ | Desplazamiento vertical |
| **Escala en $x$** | $x$ | $0$ | Estiramiento horizontal |
| **Escala en $y$** | $0$ | $y$ | Estiramiento vertical |
| **Escala Uniforme** | $x$ | $y$ | Zoom proporcional |
| **Rotación** | $y$ | $-x$ | Giro respecto al origen |
| **Proyectiva** | $x^2$ | $xy$ | Cambio de perspectiva |

### 3. La Primera Prolongación (Extensión)
Para que el generador pueda actuar sobre una EDO (que tiene derivadas $y'$), necesitamos extenderlo:
$$\mathbf{X}^{(1)} = \xi \frac{\partial}{\partial x} + \eta \frac{\partial}{\partial y} + \eta^{(1)} \frac{\partial}{\partial y'}$$
Donde la fórmula de la **prolongación** para $\eta^{(1)}$ es:
$$\eta^{(1)} = \frac{D\eta}{Dx} - y' \frac{D\xi}{Dx} = (\eta_x + y'\eta_y) - y'(\xi_x + y'\xi_y)$$

### 4. Determinación Sistemática del Generador
Para hallar $\xi$ y $\eta$, obligamos a la EDO a ser invariante mediante la **Condición de Invariancia**:
$$\mathbf{X}^{(1)}(y' - f(x,y)) = 0 \quad \text{cuando } y' = f$$
Esto se traduce en la ecuación maestra de derivadas parciales que ya conocemos:
$$\eta_x + (\eta_y - \xi_x)f - \xi_y f^2 = \xi f_x + \eta f_y$$

### 5. Teorema de Noether (Conexión Física)
Si una acción física es invariante bajo el grupo de Lie generado por $\mathbf{X}$, entonces existe una cantidad conservada $Q$.
- **Simetría temporal** ($\xi=1$) $\rightarrow$ Energía constante.
- **Simetría traslacional** ($\xi=1$) $\rightarrow$ Momento lineal constante.
- **Simetría rotacional** $\rightarrow$ Momento angular constante.

### 6. Resolución de la EDO (Paso final)
Una vez hallados $\xi$ y $\eta$, la EDO $Mdx + Ndy = 0$ se resuelve mediante el **Factor Integrante de Lie**:
$$\mu(x, y) = \frac{1}{\eta - \xi f}$$
Multiplicamos la EDO por $\mu$ y esta se vuelve **exacta**, permitiendo la integración directa para hallar la solución analítica.


### 💡 El Momento "¡Ajá!"
El método sistemático elimina la incertidumbre. No importa si la EDO parece compleja; si satisface la condición de invariancia para un par $(\xi, \eta)$, el factor integrante $\mu$ garantiza que la ecuación se volverá separable o exacta. Es como tener una llave maestra para cada cerradura.

</details>


<details>
<summary><b>📅 Resolución Paso a Paso: EDO $y' = y/x$ mediante Simetrías de Lie</b></summary>

### Enunciado del Ejercicio
Resolver la siguiente ecuación diferencial ordinaria de primer orden de forma sistemática:
$$\frac{dy}{dx} = \frac{y}{x}$$

---

### Paso 1: Identificación de componentes ($M$ y $N$)
Para aplicar el método de Lie, primero reescribo la ecuación en su **forma diferencial** igualada a cero:
$$y \, dx - x \, dy = 0$$

De aquí extraigo los componentes fundamentales que me servirán para organizar los cálculos:
* **$M(x, y) = y$**: Es la función que acompaña al diferencial $dx$.
* **$N(x, y) = -x$**: Es la función que acompaña al diferencial $dy$.
* **$f(x, y) = y/x$**: Es la pendiente original de la ecuación (mi función $y'$).

---

### Paso 2: Descubrimiento de la simetría ($\xi$ y $\eta$)
Para hallar el generador infinitesimal, consulto mi tabla de candidatos estándar. Decido probar con la **Escala en $x$**, que asume que la ecuación es invariante si estiramos el eje horizontal. Las funciones para este candidato son:
$$\xi = x, \quad \eta = 0$$

Para validar que este "descubrimiento" es una simetría real de la EDO, aplico la **Condición de Invariancia**:
$$\eta_x + (\eta_y - \xi_x)f - \xi_y f^2 = \xi f_x + \eta f_y$$



Calculo las derivadas necesarias para la fórmula. Es importante notar que como he definido $\eta = 0$ (una constante), sus derivadas respecto a cualquier variable son nulas:
* **$\eta_x = 0$** y **$\eta_y = 0$** (Derivadas de la función constante cero).
* **$\xi_x = 1$** y **$\xi_y = 0$** (Derivadas de $\xi = x$).
* **$f_x = -y/x^2$** y **$f_y = 1/x$** (Derivadas de la pendiente original $y/x$).

Sustituyo en la condición:
$$(0) + (0 - 1)\frac{y}{x} - (0)\frac{y^2}{x^2} = (x) \left(-\frac{y}{x^2}\right) + (0)\left(\frac{1}{x}\right)$$
$$-\frac{y}{x} = -\frac{y}{x}$$

La igualdad es idéntica, lo que confirma que mi elección de $\xi = x$ y $\eta = 0$ es una simetría válida.

---

### Paso 3: Cálculo del Factor Integrante ($\mu$)
Con la simetría confirmada, calculo el factor integrante de Lie, que es la "llave" para convertir la EDO en una ecuación exacta:
$$\mu = \frac{1}{\eta - \xi f}$$

Sustituyo mis funciones:
$$\mu = \frac{1}{0 - (x)\left(\frac{y}{x}\right)} = \frac{1}{-y} = -\frac{1}{y}$$

---

### Paso 4: Transformación y Separación de Variables
Multiplico mi ecuación diferencial original ($y \, dx - x \, dy = 0$) por el factor $\mu = -1/y$:
1.  $(y) \cdot \left(-\frac{1}{y}\right) dx = -1 \, dx$
2.  $(-x) \cdot \left(-\frac{1}{y}\right) dy = \frac{x}{y} \, dy$

Obtengo la nueva forma de la ecuación:
$$-1 \, dx + \frac{x}{y} \, dy = 0$$

Para integrar cómodamente, divido toda la expresión por $x$ para dejar cada diferencial con su variable correspondiente:
$$\frac{-1}{x} dx + \frac{1}{y} dy = 0$$

---

### Paso 5: Integración y Solución Final
Integro ambos términos aplicando la regla fundamental $\int \frac{1}{u} du = \ln|u|$:
$$\int -\frac{1}{x} dx + \int \frac{1}{y} dy = C \implies -\ln|x| + \ln|y| = C$$

Utilizo las propiedades de los logaritmos para simplificar la expresión:
$$\ln\left(\frac{y}{x}\right) = C$$

Para eliminar el logaritmo, aplico la función exponencial a ambos lados:
$$\frac{y}{x} = e^C$$

Finalmente, defino la constante de integración $K = e^C$ para obtener la solución analítica general:
$$\mathbf{y = Kx}$$

### 💡 Conclusión
El proceso sistemático demuestra que al encontrar la simetría de escala en $x$, la resolución de la EDO se reduce a una integración elemental. La solución final $y = Kx$ representa una familia de rectas que nacen del origen, lo cual es geométricamente consistente con la simetría de estiramiento horizontal detectada.

</details>











