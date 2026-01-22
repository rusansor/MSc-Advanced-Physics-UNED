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
<summary><b>📅 Formulario Maestro: Simetrías de Lie y Resolución de EDOs</b></summary>

### 1. El Generador Infinitesimal ($\mathbf{X}$)
Para una EDO $y' = f(x,y)$, el generador define la transformación infinitesimal:
$$\mathbf{X} = \xi(x, y) \frac{\partial}{\partial x} + \eta(x, y) \frac{\partial}{\partial y}$$

### 2. Simetrías Estándares (Candidatos comunes)
Cuando no conocemos $\xi$ y $\eta$, probamos estos "moldes" geométricos:

| Transformación | $\xi(x, y)$ | $\eta(x, y)$ |
| :--- | :--- | :--- |
| **Traslación en $x$** | $1$ | $0$ |
| **Traslación en $y$** | $0$ | $1$ |
| **Escala (Elongación)** | $x$ | $y$ |
| **Rotación** | $y$ | $-x$ |

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


<summary><b>📅 Ejemplo Práctico: Resolución Sistemática vs. Intuición</b></summary>

### 🎯 Caso de estudio: La EDO de crecimiento lineal
Analizamos la ecuación diferencial:
$$y' = \frac{y}{x}$$

### 1. El Camino de la "Intuición" (Trial & Error)
Probamos si una **traslación en $y$** ($\xi=0, \eta=1$) es simetría:
- Calculamos el Factor Integrante: $\mu = \frac{1}{\eta - \xi f} = \frac{1}{1 - 0} = 1$.
- Al multiplicar la EDO por $1$, vemos que no se simplifica el problema de forma inmediata. La intuición a veces requiere varios intentos.

### 2. El Camino Sistemático (Condición de Invariancia)
Aplicamos la "fórmula madre" para testear la simetría de **escala en $x$** ($\xi=x, \eta=0$):
$$\eta_x + (\eta_y - \xi_x)f - \xi_y f^2 = \xi f_x + \eta f_y$$

Sustituyendo los valores de nuestra EDO ($f = y/x$):
$$0 + (0 - 1)\frac{y}{x} - 0 = x \left(-\frac{y}{x^2}\right) + 0$$
$$-\frac{y}{x} = -\frac{y}{x} \quad \text{(¡Identidad confirmada!)}$$

**Resultado:** La simetría $\xi=x, \eta=0$ es matemáticamente válida para esta EDO.

### 3. Un ejemplo concreto de como resolver una ecuación diferencial con simetrías - Resolución Paso a Paso
1. **Generar $\mu$:** Usando la simetría hallada:
   $$\mu = \frac{1}{0 - x(\frac{y}{x})} = -\frac{1}{y}$$
2. **Transformar la EDO:** Multiplicamos $dy - \frac{y}{x}dx = 0$ por $\mu$:
   $$-\frac{1}{y}dy + \frac{1}{x}dx = 0$$
3. **Integración Directa:**
   $$\int \frac{1}{x}dx - \int \frac{1}{y}dy = C \implies \ln|x| - \ln|y| = C$$
4. **Solución General:**
   $$y = Kx$$

### 💡 El Momento "¡Ajá!"
El método sistemático elimina la incertidumbre. No importa si la EDO parece compleja; si satisface la condición de invariancia para un par $(\xi, \eta)$, el factor integrante $\mu$ garantiza que la ecuación se volverá separable o exacta. Es como tener una llave maestra para cada cerradura.

</details>




---

<details>
<summary><b>📅 22/01/2026: Texooooooooo</b> (Clic para expandir)</summary>

- **Idea:** 
- **Fórmula:** 
- **Ajá!:** 
</details>











