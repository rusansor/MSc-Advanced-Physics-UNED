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
<summary><b>📅 22/01/2026: Formulario Maestro: Simetrías de Lie y Resolución de EDOs</b></summary>

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
<summary><b>📅 22/01/2026: Resolución Paso a Paso: EDO y' = y/x mediante Simetrías de Lie</b></summary>

### Enunciado del Ejercicio
Resolver la siguiente ecuación diferencial ordinaria de primer orden de forma sistemática:
$$\frac{dy}{dx} = \frac{y}{x}$$

---

### Paso 1: Identificación de componentes ($M$ y $N$)
Para aplicar el método de Lie, primero reescribo la ecuación en su **forma diferencial** igualada a cero:
$$y \, dx - x \, dy = 0$$

De aquí extraigo los componentes fundamentales para organizar los cálculos:
* **$M(x, y) = y$**: Es la función que acompaña al diferencial $dx$.
* **$N(x, y) = -x$**: Es la función que acompaña al diferencial $dy$.
* **$f(x, y) = y/x$**: Es la pendiente original de la ecuación (mi función $y'$).

---

### Paso 2: Descubrimiento de la simetría ($\xi$ y $\eta$)
Para hallar el generador infinitesimal, consulto mi tabla de candidatos estándar. Decido probar con la **Escala en $x$**, que asume que la ecuación es invariante si estiramos el eje horizontal. Las funciones para este candidato son:
$$\xi = x, \quad \eta = 0$$

Para validar que este descubrimiento es una simetría real, aplico la **Condición de Invariancia**:
$$\eta_x + (\eta_y - \xi_x)f - \xi_y f^2 = \xi f_x + \eta f_y$$



Calculo las derivadas necesarias. Como he definido $\eta = 0$ (una constante), sus derivadas son nulas:
* **$\eta_x = 0$** y **$\eta_y = 0$**
* **$\xi_x = 1$** y **$\xi_y = 0$** (ya que $\xi = x$)
* **$f_x = -y/x^2$** y **$f_y = 1/x$** (derivadas de la pendiente original $y/x$)

Sustituyo en la condición:
$$(0) + (0 - 1)\frac{y}{x} - (0)\frac{y^2}{x^2} = (x) \left(-\frac{y}{x^2}\right) + (0)\left(\frac{1}{x}\right)$$
$$-\frac{y}{x} = -\frac{y}{x}$$

La igualdad es idéntica, lo que confirma que la simetría es $\xi = x$ y $\eta = 0$.

---

### Paso 3: Cálculo del Factor Integrante ($\mu$)
Calculo el factor integrante de Lie, que es la "llave" para convertir la EDO en una ecuación exacta:
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

Para integrar cómodamente, divido toda la expresión por $x$ para separar las variables:
$$\frac{-1}{x} dx + \frac{1}{y} dy = 0$$

---

### Paso 5: Integración y Solución Final
Integro ambos términos aplicando la regla $\int \frac{1}{u} du = \ln|u|$:
$$\int -\frac{1}{x} dx + \int \frac{1}{y} dy = C \implies -\ln|x| + \ln|y| = C$$

Despejo utilizando las propiedades de la exponencial y el logaritmo:
$$\ln\left(\frac{y}{x}\right) = C \implies \frac{y}{x} = e^C$$

Finalmente, defino la constante de integración $K = e^C$:
$$\mathbf{y = Kx}$$

### 💡 Conclusión
Al encontrar la simetría de escala en $x$, la resolución de la EDO se reduce a una integración elemental. La solución final $y = Kx$ representa una familia de rectas que nacen del origen.

</details>


<details>
<summary><b>📅 22/01/2026: Cálculo Sistemático del Generador de Simetría (Ecuación Definitoria)</b></summary>

Antes de resolver la EDO, necesito encontrar el generador $\mathbf{X} = \xi \partial_x + \eta \partial_y$ sin recurrir a tablas. Para ello, debo resolver la **Ecuación Definitoria de Lie**.

### 1. Planteamiento de la Ecuación Definitoria
Para cualquier EDO $y' = f(x,y)$, el generador debe satisfacer:
$$\eta_x + (\eta_y - \xi_x)f - \xi_y f^2 = \xi f_x + \eta f_y$$

En mi caso, con $f = \frac{y}{x}$, calculo primero las derivadas parciales de la pendiente:
* $f_x = \frac{\partial}{\partial x}(\frac{y}{x}) = -\frac{y}{x^2}$
* $f_y = \frac{\partial}{\partial y}(\frac{y}{x}) = \frac{1}{x}$

Sustituyo estos valores en la ecuación:
$$\eta_x + (\eta_y - \xi_x)\frac{y}{x} - \xi_y \frac{y^2}{x^2} = \xi \left(-\frac{y}{x^2}\right) + \eta \left(\frac{1}{x}\right)$$

### 2. Simplificación Algebraica
Multiplico toda la ecuación por $x^2$ para eliminar denominadores y facilitar la separación de términos:
$$x^2 \eta_x + xy(\eta_y - \xi_x) - y^2 \xi_y = -y \xi + x \eta$$

Esta es una ecuación con dos incógnitas ($\xi$ y $\eta$). Para resolverla de forma sistemática, utilizo el método de **separación por potencias de $y$**.

### 3. Resolución del Sistema (Búsqueda de soluciones simples)
Asumo que los componentes del generador son funciones elementales. 

**Caso A: Busco una simetría donde $\eta = 0$**
Si decido que no hay desplazamiento en $y$, la ecuación se reduce drásticamente:
$$x^2(0) + xy(0 - \xi_x) - y^2 \xi_y = -y \xi + x(0)$$
$$-xy \xi_x - y^2 \xi_y = -y \xi$$

Divido toda la expresión por $-y$:
$$x \xi_x + y \xi_y = \xi$$

Para que esta igualdad se mantenga, si asumo que $\xi$ solo depende de $x$ (haciendo $\xi_y = 0$):
$$x \frac{d\xi}{dx} = \xi \implies \frac{d\xi}{\xi} = \frac{dx}{x}$$

Integrando ambos lados, obtengo $\ln|\xi| = \ln|x|$, por lo tanto:
$$\xi = x$$

**Resultado del cálculo:** He hallado sistemáticamente el generador $\mathbf{\xi = x, \eta = 0}$.

---

### 4. Verificación de una segunda simetría (Caso B)
¿Qué ocurre si asumo que $\xi = 0$? 
La ecuación original del Paso 2 se convierte en:
$$x^2 \eta_x + xy \eta_y = x \eta$$

Divido por $x$:
$$x \eta_x + y \eta_y = \eta$$

Si asumo que $\eta$ solo depende de $y$ (haciendo $\eta_x = 0$):
$$y \frac{d\eta}{dy} = \eta \implies \eta = y$$

**Resultado del cálculo:** He hallado un segundo generador válido $\mathbf{\xi = 0, \eta = y}$.



### 💡 Conclusión del procedimiento
Este método me permite "extraer" la simetría directamente de la estructura de la EDO. He demostrado que la ecuación $y' = y/x$ admite al menos dos generadores de escala independientes ($\xi=x$ o $\eta=y$). En el ejercicio práctico, utilizaré el primero ($\xi=x, \eta=0$) para construir el factor integrante $\mu$.

</details>


<details>
<summary><b>📅 19/02/2026: Salto a Segundo Orden: Prolongaciones y el Método de Cantwell/Arrigo</b> (Clic para expandir)</summary>

### 1. El Desafío del Segundo Orden
Cuando pasamos a ecuaciones del tipo $y'' = f(x, y, y')$, el generador infinitesimal $\mathbf{X}$ debe ser capaz de "ver" no solo la pendiente ($y'$), sino también la curvatura ($y''$). Para ello, recurro a la **segunda prolongación**.

### 2. El Formulario de Extensión (Fórmulas Maestras)
Basándome en la metodología de **Cantwell y Arrigo**, estas son las expresiones clave para las funciones extendidas:

* **Primera prolongación ($\eta^{(1)}$):**
    $$\eta^{(1)} = \eta_x + (\eta_y - \xi_x)y' - \xi_y(y')^2$$
* **Segunda prolongación ($\eta^{(2)}$):**
    $$\eta^{(2)} = \eta_{xx} + (2\eta_{xy} - \xi_{xx})y' + (\eta_{yy} - 2\xi_{xy})(y')^2 - \xi_{yy}(y')^3 + (\eta_y - 2\xi_x - 3\xi_y y')y''$$



### 3. La Condición de Invariancia de Segundo Orden
Para que la EDO sea invariante, el generador extendido debe anular la ecuación en su superficie de solución:
$$\eta^{(2)} - \xi f_x - \eta f_y - \eta^{(1)} f_{y'} = 0 \quad \text{evaluado en } y'' = f$$

### 4. Hoja de Ruta Sistemática (Algoritmo de Resolución)

1.  **Planteamiento:** Sustituyo $\eta^{(1)}$ y $\eta^{(2)}$ en la condición de invariancia. Reemplazo cada $y''$ por la función $f(x, y, y')$ original.
2.  **Separación por potencias:** Trato a $y'$ como una variable independiente. Agrupo términos por potencias de $y'$ ($(y')^0, (y')^1, (y')^2, (y')^3$) e igualo cada coeficiente a cero. Esto genera el sistema de **ecuaciones definitorias**.
3.  **Bifurcación de Resolución:**
    * **Caso A (1 Simetría):** Cambio a **Variables Canónicas** $(r, s)$ donde $\mathbf{X} = \partial_s$. La EDO reduce su orden de 2º a 1º.
    * **Caso B (2+ Simetrías):** Calculo el conmutador $[X_1, X_2]$. Si forman un álgebra resoluble ($[X_1, X_2] = \lambda X_1$), la ecuación se resuelve mediante dos integraciones directas (cuadraturas).



### Reflexión: De la Geometría a la Arquitectura
Lo más potente de este nivel es el **Teorema de Clasificación de Lie**. He aprendido que si una EDO de segundo orden tiene el máximo de simetría (8 generadores), es fundamentalmente equivalente a $y'' = 0$. 

Como *Solution Architect*, veo una analogía clara: resolver una EDO compleja mediante simetrías es como refactorizar un código monolítico buscando los patrones de diseño subyacentes. Una vez encuentras la simetría (el patrón), la solución (la implementación) se vuelve trivial y elegante.

</details>

<details>
<summary><b>📅 19/02/2026: Resolución Sistemática: y'' = 0 mediante Simetrías de Lie</b></summary>

### Enunciado del Ejercicio
Resolver la ecuación diferencial de segundo orden más elemental aplicando el método de Lie sin inferencias previas:
$$y'' = 0$$

---

### Paso 1: Definición de la Función y sus Derivadas
Para una EDO de segundo orden $y'' = f(x, y, y')$, identificamos:
* **$f(x, y, y') = 0$**
* Derivadas parciales: $f_x = 0$, $f_y = 0$, $f_{y'} = 0$.

### Paso 2: Planteamiento de la Condición de Invariancia
Utilizamos la condición maestra para segundo orden:
$$\eta^{(2)} - \xi f_x - \eta f_y - \eta^{(1)} f_{y'} = 0$$

Al ser todas las derivadas de $f$ nulas, la condición se reduce a:
$$\eta^{(2)} = 0$$

### Paso 3: Expansión de la Segunda Prolongación ($\eta^{(2)}$)
Sustituimos la fórmula completa de $\eta^{(2)}$ (asumiendo $y'' = 0$ según la EDO):
$$\eta_{xx} + (2\eta_{xy} - \xi_{xx})y' + (\eta_{yy} - 2\xi_{xy})(y')^2 - \xi_{yy}(y')^3 = 0$$



### Paso 4: Separación por Potencias de $y'$ (Ecuaciones Definitorias)
Tratamos a $y'$ como una variable independiente. Para que la igualdad se cumpla, cada coeficiente del polinomio debe ser cero de forma independiente:

1.  **$(y')^3$:** $-\xi_{yy} = 0 \implies \xi$ es lineal en $y$.
2.  **$(y')^2$:** $\eta_{yy} - 2\xi_{xy} = 0$.
3.  **$(y')^1$:** $2\eta_{xy} - \xi_{xx} = 0$.
4.  **$(y')^0$:** $\eta_{xx} = 0 \implies \eta$ es lineal en $x$.

### Paso 5: Selección de un Generador
De las múltiples soluciones (esta EDO tiene 8 simetrías), elegimos la más simple por inspección del sistema:
* **$\xi = 0$**
* **$\eta = 1$**
(Esto satisface las 4 ecuaciones: $0=0, 0=0, 0=0, 0=0$). Generador: $\mathbf{X} = \partial_y$.

### Paso 6: Cambio a Variables Canónicas ($r, s$)
Buscamos transformar el generador en una traslación pura ($\mathbf{X} = \partial_s$):
* **Invariante ($r$):** $\mathbf{X}r = 0 \cdot r_x + 1 \cdot r_y = 0 \implies r = x$.
* **Variable de traslación ($s$):** $\mathbf{X}s = 0 \cdot s_x + 1 \cdot s_y = 1 \implies s = y$.

### Paso 7: Reducción de Orden e Integración
La EDO original $y'' = 0$ en las nuevas coordenadas $(r, s)$ sigue siendo:
$$\frac{d^2s}{dr^2} = 0$$

1. Definimos $v = \frac{ds}{dr}$, entonces $\frac{dv}{dr} = 0$.
2. Primera integración: $v = C_1 \implies \frac{ds}{dr} = C_1$.
3. Segunda integración: $s = C_1 r + C_2$.

### Paso 8: Solución Final
Deshacemos el cambio de variables ($s=y$, $r=x$):
$$\mathbf{y = C_1 x + C_2}$$



### 💡 El Momento "¡Ajá!"
Lo fascinante aquí es que el método no "adivina" la solución. Al separar por potencias de $y'$, el álgebra nos obliga a encontrar las funciones $\xi$ y $\eta$ que dejan la curvatura ($y''$) invariante. Elegir $\mathbf{X} = \partial_y$ significa que la EDO no cambia si la desplazamos verticalmente, lo cual es lógicamente consistente con una familia de rectas paralelas.

</details>

<details>
<summary><b>📅 19/02/2026: Resolución Sistemática: y'' = y' (El efecto de la pendiente en la simetría)</b></summary>

### Enunciado del Ejercicio
Resolver mediante el método de Lie la EDO de segundo orden:
$$y'' = y'$$

---

### Paso 1: Identificación de la Función $f$
Identificamos la función $f$ y sus derivadas parciales:
* **$f(x, y, y') = y'$**
* $f_x = 0$
* $f_y = 0$
* $f_{y'} = 1$

### Paso 2: Planteamiento de la Condición de Invariancia
Aplicamos la fórmula: $\eta^{(2)} - \xi f_x - \eta f_y - \eta^{(1)} f_{y'} = 0$.
Sustituyendo los valores de $f$ y sus derivadas:
$$\eta^{(2)} - \eta^{(1)} = 0 \quad (\text{evaluado en } y'' = y')$$

### Paso 3: Expansión y Sustitución
Sustituimos las fórmulas de las prolongaciones $\eta^{(1)}$ y $\eta^{(2)}$. 
*Ojo:* En la fórmula de $\eta^{(2)}$, donde aparezca $y''$, debemos escribir $y'$.

$$\underbrace{\eta_{xx} + (2\eta_{xy} - \xi_{xx})y' + (\eta_{yy} - 2\xi_{xy})(y')^2 - \xi_{yy}(y')^3 + (\eta_y - 2\xi_x - 3\xi_y y')y'}_{\eta^{(2)}} - \underbrace{(\eta_x + (\eta_y - \xi_x)y' - \xi_y(y')^2)}_{\eta^{(1)}} = 0$$

### Paso 4: Separación por Potencias de $y'$ (Ecuaciones Definitorias)
Agrupamos los términos según el grado de $y'$ para obtener el sistema de ecuaciones:

1.  **$(y')^3$:** $-\xi_{yy} = 0$
2.  **$(y')^2$:** $\eta_{yy} - 2\xi_{xy} - 3\xi_y + \xi_y = 0 \implies \eta_{yy} - 2\xi_{xy} - 2\xi_y = 0$
3.  **$(y')^1$:** $(2\eta_{xy} - \xi_{xx}) + (\eta_y - 2\xi_x) - (\eta_y - \xi_x) = 0 \implies 2\eta_{xy} - \xi_{xx} - \xi_x = 0$
4.  **$(y')^0$:** $\eta_{xx} - \eta_x = 0$



### Paso 5: Selección de un Generador
Buscamos la solución más simple. Probamos con una simetría de traslación en $y$ (ya que la ecuación no depende explícitamente de $y$):
* Si probamos **$\xi = 0$**:
    * De (1), (2) y (3): $\eta_{yy} = 0$ y $2\eta_{xy} = 0$.
    * De (4): $\eta_{xx} - \eta_x = 0 \implies \eta = e^x$ o $\eta = 1$.
* Elegimos **$\xi = 0, \eta = 1$** (Traslación en $y$). Generador: $\mathbf{X} = \partial_y$.

### Paso 6: Cambio a Variables Canónicas ($r, s$)
Para $\mathbf{X} = \partial_y$:
* **$r = x$** (Invariante)
* **$s = y$** (Variable de traslación)

### Paso 7: Reducción e Integración
La EDO $y'' = y'$ en las nuevas coordenadas se mantiene como:
$$\frac{d^2s}{dr^2} = \frac{ds}{dr}$$

1. Sea $v = \frac{ds}{dr}$: $\frac{dv}{dr} = v$.
2. Separamos variables: $\frac{dv}{v} = dr \implies \ln|v| = r + C \implies v = C_1 e^r$.
3. Sustituimos $v$: $\frac{ds}{dr} = C_1 e^r$.
4. Integramos de nuevo: $s = C_1 e^r + C_2$.

### Paso 8: Solución Final
Deshacemos el cambio ($s=y, r=x$):
$$\mathbf{y = C_1 e^x + C_2}$$



### 💡 El Momento "¡Ajá!"
En el Paso 4 hemos visto cómo la estructura de la EDO ($y'' = y'$) "contamina" las ecuaciones definitorias. A diferencia del ejemplo anterior ($y''=0$), aquí los términos de $\eta^{(1)}$ se restan de los de $\eta^{(2)}$, alterando los coeficientes de $(y')^1$ y $(y')^0$. Es un recordatorio de que la simetría está íntimamente ligada a cómo cambian las derivadas entre sí.

</details>

<details>
<summary><b>📅 19/02/2026: Resolución Sistemática: y'' = (y')²/y (La potencia de las simetrías en EDOs No Lineales)</b></summary>

### Enunciado del Ejercicio
Resolver mediante el método sistemático de Lie la EDO no lineal de segundo orden:
$$y'' = \frac{(y')^2}{y}$$

---

### Paso 1: Identificación de la Función $f$
Identificamos la función $f$ y sus derivadas parciales:
* **$f(x, y, y') = \frac{(y')^2}{y}$**
* $f_x = 0$
* $f_y = -\frac{(y')^2}{y^2}$
* $f_{y'} = \frac{2y'}{y}$

### Paso 2: Planteamiento de la Condición de Invariancia
Aplicamos la fórmula: $\eta^{(2)} - \xi f_x - \eta f_y - \eta^{(1)} f_{y'} = 0$.
Sustituimos $f$ y sus derivadas:
$$\eta^{(2)} - \eta \left( -\frac{(y')^2}{y^2} \right) - \eta^{(1)} \left( \frac{2y'}{y} \right) = 0 \quad (\text{evaluado en } y'' = \frac{(y')^2}{y})$$

### Paso 3: Expansión y Sustitución Crítica
Sustituimos las prolongaciones. Donde aparezca $y''$, escribimos $\frac{(y')^2}{y}$.

$$\underbrace{\eta_{xx} + (2\eta_{xy} - \xi_{xx})y' + (\eta_{yy} - 2\xi_{xy})(y')^2 - \xi_{yy}(y')^3 + (\eta_y - 2\xi_x - 3\xi_y y')\frac{(y')^2}{y}}_{\eta^{(2)}} + \frac{\eta(y')^2}{y^2} - \frac{2y'}{y}\underbrace{(\eta_x + (\eta_y - \xi_x)y' - \xi_y(y')^2)}_{\eta^{(1)}} = 0$$

### Paso 4: Separación por Potencias de $y'$ (Ecuaciones Definitorias)
Agrupamos términos. Este paso revela la "arquitectura" de la simetría:

1.  **$(y')^3$:** $-\xi_{yy} - \frac{3\xi_y}{y} + \frac{2\xi_y}{y} = 0 \implies -\xi_{yy} - \frac{\xi_y}{y} = 0$
2.  **$(y')^2$:** $(\eta_{yy} - 2\xi_{xy}) + \frac{\eta_y - 2\xi_x}{y} + \frac{\eta}{y^2} - \frac{2(\eta_y - \xi_x)}{y} = 0 \implies \eta_{yy} - 2\xi_{xy} - \frac{\eta_y}{y} + \frac{\eta}{y^2} = 0$
3.  **$(y')^1$:** $(2\eta_{xy} - \xi_{xx}) - \frac{2\eta_x}{y} = 0$
4.  **$(y')^0$:** $\eta_{xx} = 0$



### Paso 5: Selección de un Generador
Buscamos una solución sencilla. Probamos con la **Escala en $y$** (ya que la ecuación es homogénea en $y$):
* Probamos **$\xi = 0, \eta = y$**.
* Verificamos en las ecuaciones:
    1. $0 = 0$ (OK)
    2. $\eta_{yy} (0) - 2(0) - \frac{1}{y} + \frac{y}{y^2} = 0 \implies -1/y + 1/y = 0$ (OK)
    3. $2(0) - 0 - 0 = 0$ (OK)
    4. $0 = 0$ (OK)
* Generador: $\mathbf{X} = y\partial_y$.

### Paso 6: Cambio a Variables Canónicas ($r, s$)
Para $\mathbf{X} = y\partial_y$:
* **$r = x$** (Invariante, pues $\mathbf{X}x = 0$)
* **$s = \ln(y)$** (Porque $y\frac{\partial}{\partial y}(\ln y) = y \cdot \frac{1}{y} = 1$)

### Paso 7: Reducción e Integración
Transformamos la EDO a las nuevas coordenadas:
1. $s = \ln y \implies \frac{ds}{dr} = \frac{y'}{y}$
2. $\frac{d^2s}{dr^2} = \frac{y''y - (y')^2}{y^2}$
3. Sustituimos la EDO original $y'' = (y')^2/y$:
   $$\frac{d^2s}{dr^2} = \frac{\frac{(y')^2}{y}y - (y')^2}{y^2} = \frac{(y')^2 - (y')^2}{y^2} = 0$$

¡La EDO no lineal se ha convertido en **$\frac{d^2s}{dr^2} = 0$**!

4. Integración: $s = C_1 r + C_2$.

### Paso 8: Solución Final
Deshacemos el cambio ($s = \ln y, r = x$):
$$\ln y = C_1 x + C_2 \implies \mathbf{y = e^{C_1 x + C_2}}$$
O de forma más elegante: **$y = Ae^{Bx}$**.



### 💡 El Momento "¡Ajá!"
Es impactante ver cómo una ecuación no lineal desaparece por completo al elegir las coordenadas correctas. La simetría $y\partial_y$ (escala) nos dice que lo importante no es el valor de $y$, sino su **tasa de cambio relativa**. Por eso el logaritmo "linealiza" el problema. Como *Solution Architect*, esto es el equivalente a normalizar una base de datos para que las consultas complejas se vuelvan simples sumas.

</details>


<details>
<summary><b>📅 19/02/2026: Resolución Sistemática: y'' + ω²y = 0 (El Oscilador Armónico y sus simetrías)</b></summary>

### Enunciado del Ejercicio
Resolver mediante el método de Lie la ecuación del oscilador armónico simple, pilar fundamental de la mecánica clásica y cuántica:
$$y'' = -\omega^2 y$$

---

### Paso 1: Identificación de la Función $f$
Identificamos la función $f$ (la fuerza por unidad de masa en términos de Hooke) y sus derivadas:
* **$f(x, y, y') = -\omega^2 y$**
* $f_x = 0$ (Invariancia temporal: el sistema es autónomo).
* $f_y = -\omega^2$ (La fuerza depende linealmente del desplazamiento).
* $f_{y'} = 0$ (Sistema conservativo: no hay fricción).

### Paso 2: Planteamiento de la Condición de Invariancia
Aplicamos la fórmula: $\eta^{(2)} - \xi f_x - \eta f_y - \eta^{(1)} f_{y'} = 0$.
$$\eta^{(2)} + \omega^2 \eta = 0$$

### Paso 3: Expansión de la Segunda Prolongación
Sustituimos la fórmula de $\eta^{(2)}$ y, donde aparezca $y''$, escribimos $-\omega^2 y$:
$$\eta_{xx} + (2\eta_{xy} - \xi_{xx})y' + (\eta_{yy} - 2\xi_{xy})(y')^2 - \xi_{yy}(y')^3 + (\eta_y - 2\xi_x - 3\xi_y y')(-\omega^2 y) + \omega^2 \eta = 0$$

### Paso 4: Separación por Potencias de $y'$ (Ecuaciones Definitorias)
1.  **$(y')^3$:** $-\xi_{yy} = 0$
2.  **$(y')^2$:** $\eta_{yy} - 2\xi_{xy} + 3\omega^2 y \xi_y = 0$
3.  **$(y')^1$:** $2\eta_{xy} - \xi_{xx} - \omega^2 y (\eta_y - 2\xi_x) = 0$
4.  **$(y')^0$:** $\eta_{xx} - \omega^2 y (\eta_y - 2\xi_x) + \omega^2 \eta = 0$

### Paso 5: Selección de un Generador (La Simetría de Superposición)
Probamos la simetría de **Escala en $y$** ($\xi = 0, \eta = y$):
* Generador: $\mathbf{X} = y\partial_y$. Esta simetría refleja que el oscilador es **lineal**: si duplicas la amplitud, el sistema sigue la misma física.

### Paso 6: Cambio a Variables Canónicas ($r, s$)
* **$r = x$** (Tiempo)
* **$s = \ln(y)$** (Fase logarítmica)

### Paso 7: Reducción e Integración
Transformamos la EDO $y'' = -\omega^2 y$ usando $s = \ln y$:
1. Reducción a primer orden ($v = s'$): $\frac{dv}{dr} + v^2 + \omega^2 = 0$.
2. Esta es una **ecuación de Riccati** simple. Integrando: $\frac{1}{\omega} \arctan\left(\frac{v}{\omega}\right) = -r + C_1$.

### Paso 8: Solución Final
Deshaciendo el logaritmo y la arcotangente:
$$\mathbf{y = A \cos(\omega x + \phi)}$$



---

### ⚛️ Interpretación Física Profunda (Análisis de Simetría)

Como físico, lo más revelador de este proceso no es el resultado, sino lo que nos dice sobre la **naturaleza del espacio-tiempo** del sistema:

1. **Simetría Temporal ($\partial_x$):** Al no depender $f$ de $x$, el generador $\mathbf{X} = \partial_x$ es una simetría. Según el **Teorema de Noether**, esta invarianza bajo traslaciones temporales implica la **Conservación de la Energía** ($E = \frac{1}{2}m\dot{y}^2 + \frac{1}{2}m\omega^2 y^2$).
2. **El Espacio de Fases:** El paso por la función $\arctan$ en la integración no es casual. El método de Lie está mapeando la oscilación lineal en una **rotación en el plano complejo** ($e^{i\omega t}$). La simetría de escala que hemos usado ($\eta=y$) es en realidad una parte de un grupo más grande (SL(2,R)) que gobierna a los sistemas armónicos.
3. **Linealidad y Superposición:** Que $\eta=y$ sea una simetría válida confirma el principio de superposición. En sistemas no lineales (como el péndulo simple para grandes ángulos), esta simetría se rompe, lo que explica por qué las soluciones dejan de ser senoidales puras.

### 💡 El Momento "¡Ajá!" del Arquitecto
Este ejercicio demuestra que incluso los sistemas más "predecibles" tienen estructuras de simetría profundas. En el diseño de sistemas (o en física), encontrar la **coordenada cíclica** (en este caso la fase) es lo que permite simplificar un problema dinámico en uno estático.

</details>
