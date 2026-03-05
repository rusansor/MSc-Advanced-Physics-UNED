# Capítulo 1: Definición de Grupo y Caracterización de Rotaciones
**Referencia:** [Grupos de Lie - Capítulo 1 (Javier García)](https://www.youtube.com/watch?v=4NE-KNwHKSI)

---

### Descripción del Contenido
En este capítulo introductorio, Javier García define formalmente qué es un **Grupo** en matemáticas y establece la misión del curso: caracterizar las rotaciones en el plano. Se presenta la derivación de la matriz de rotación mediante trigonometría clásica (método pasivo) y se introducen las propiedades que definen al grupo especial ortogonal $SO(2)$. Este capítulo sirve como base comparativa para el "método moderno" (infinitesimal) que se verá en las siguientes lecciones.

---

## 1. ¿Qué es un Grupo?
Un grupo $(G, \cdot)$ es un conjunto de elementos dotados de una operación que debe cumplir tres propiedades fundamentales:

1.  **Asociatividad (A):** $(a \cdot b) \cdot c = a \cdot (b \cdot c)$
2.  **Elemento Identidad (B):** Existe un único elemento $e \in G$ tal que $g \cdot e = e \cdot g = g$ para todo $g$.
3.  **Elemento Inverso (C):** Para cada $g \in G$, existe un único $g^{-1}$ tal que $g \cdot g^{-1} = g^{-1} \cdot g = e$.

> **Bonus Track:** Si además se cumple la propiedad conmutativa ($a \cdot b = b \cdot a$), el grupo se denomina **Abeliano**. Los grupos de Lie de interés en física (como las rotaciones en 3D) generalmente **no** son abelianos.

---

## 2. Caracterización de una Rotación (Método 1: Trigonometría)
El objetivo es encontrar una forma automática de transformar las coordenadas de un punto al rotar el sistema de referencia.

### Rotación Pasiva
Se utiliza el enfoque de **rotación pasiva**: el punto $P$ se queda quieto, pero el observador (los ejes) gira un ángulo $\alpha$.
* Ejes originales: $X, Y$ (Coordenadas $x, y$).
* Ejes rotados: $X', Y'$ (Coordenadas $x', y'$).

### Derivación Matemática
Usando las identidades trigonométricas de la suma de ángulos:
$$\cos(a+b) = \cos a \cos b - \sin a \sin b$$
$$\sin(a+b) = \sin a \cos b + \sin b \cos a$$

Llegamos a la relación entre las coordenadas del observador original y el rotado:
$$x = x' \cos \alpha - y' \sin \alpha$$
$$y = x' \sin \alpha + y' \cos \alpha$$

---

## 3. La Matriz de Rotación $R$
La relación anterior se puede expresar de forma matricial como:
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \cos \alpha & -\sin \alpha \\ \sin \alpha & \cos \alpha \end{pmatrix} \begin{pmatrix} x' \\ y' \end{pmatrix}
$$

### Propiedades de la Matriz $R$:
1.  **Determinante:** $\det(R) = \cos^2 \alpha + \sin^2 \alpha = 1$. (Esto indica que la transformación conserva el volumen/área y la orientación).
2.  **Ortogonalidad:** Se demuestra que la inversa de la matriz es igual a su traspuesta: $R^{-1} = R^T$, lo que implica:
    $$R \cdot R^T = I$$

---

## 4. Generalización y Notación de Einstein
Para trabajar en $N$ dimensiones, se sustituyen las letras $(x, y)$ por índices $(x_1, x_2, \dots, x_n)$.

### Criterio de Suma de Einstein
Javier introduce la notación simplificada donde un índice repetido implica una suma:
$$x'_i = R_{ij} x_j \quad \equiv \quad x'_i = \sum_{j} R_{ij} x_j$$

---

## 5. El Grupo $SO(2)$
El conjunto de todas estas matrices de rotación en 2D forma el grupo llamado **$SO(2)$**:
* **S (Special):** Porque su determinante es $+1$.
* **O (Orthogonal):** Porque cumple $R^T R = I$.
* **2:** Porque actúa sobre un espacio de dimensión 2.

Es un **Grupo de Lie** porque sus elementos dependen de un parámetro continuo ($\alpha$) y forman una variedad continua (un círculo en este caso).

---

## Conceptos Clave para Repaso
* **Variedad:** Un conjunto continuo de elementos (como las infinitas matrices de rotación posibles según el ángulo).
* **Grupo Uniparamétrico:** Aquel que solo depende de un parámetro (en $SO(2)$, solo necesitamos el ángulo $\alpha$).
* **Diferencia entre matriz e identidad:** En ecuaciones matriciales, el "1" representa la matriz identidad $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$.
