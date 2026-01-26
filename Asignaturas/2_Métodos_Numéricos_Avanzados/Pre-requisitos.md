# Plan de Preparación y Ejecución: Métodos Numéricos Avanzados (Curso 2026)

Este documento detalla mi estrategia personal para abordar la asignatura del Máster. Como programador profesional, mi enfoque se centra en la construcción de una librería propia de algoritmos numéricos ("from scratch") para asegurar la máxima precisión, eficiencia y comprensión de los fenómenos físicos.

## Fase 1: Construcción de mi Librería Base (Pre-Máster)
*En esta etapa voy a desarrollar los "ladrillos" de software que reutilizaré durante todo el curso. Mi objetivo es no depender de librerías externas para los solvers, implementando los algoritmos basándome en el Burden & Faires (9ª Ed).*

| Capítulo | Secciones | Mi Acción Técnica | Objetivo y Dependencia |
| :--- | :--- | :--- | :--- |
| **Cap. 1** | 1.1 | **Lectura conceptual.** | Entender la Serie de Taylor para justificar analíticamente el error en mis futuras memorias. |
| **Cap. 2** | 2.1 → 2.3 | **Implementar Newton (2.3).** | Tras ojear la bisección como base, programaré un buscador de raíces robusto. Lo necesito para el Trabajo 1. |
| **Cap. 4** | 4.1 → 4.4 | **Implementar Simpson (4.3).** | Entenderé la discretización de derivadas (4.1) y programaré un integrador numérico. Lo usaré en el Trabajo 5. |
| **Cap. 5** | 5.2 → 5.4 | **Implementar RK4 (5.4).** | Basándome en la lógica de Euler, programaré el método Runge-Kutta de 4º orden. Es el motor de mis EDOs. |
| **Cap. 6** | 6.1, 6.4 | **Implementar Gauss/LU.** | Programaré un solver de sistemas lineales con pivoteo parcial. Es la base de los Trabajos 2, 3, 4 y 5. |
| **Cap. 7** | 7.3 | **Implementar Gauss-Seidel.** | Desarrollaré este método iterativo para matrices dispersas. Imprescindible para el Trabajo 3. |

---

## Fase 2: Ejecución de los Trabajos del Máster (Curso 2026)
*Aplicación de mi librería a los problemas físicos específicos del programa. En esta fase combinaré mis módulos previos para resolver ecuaciones diferenciales complejas.*

| Trabajo | Cap. Estudio | Mi Enfoque en la Entrega | Dependencias de mi Fase 1 |
| :--- | :--- | :--- | :--- |
| **T1: Contorno** | **Cap. 11** | Resolveré problemas de contorno mediante el **Método del Disparo**. | Requiere mi **RK4 (Cap 5)** y mi **Newton (Cap 2)**. |
| **T2: Autovalores** | **Cap. 9** | Implementaré el **Algoritmo QR** para cálculos de autovalores físicos. | Requiere mi lógica de **Matrices (Cap 6)**. |
| **T3: Elípticas** | **Cap. 12.1** | Resolveré la ecuación de Laplace mediante mallas de diferencias finitas. | Requiere mi **Gauss-Seidel (Cap 7)**. |
| **T4: Calor/Ondas** | **Cap. 12.2-3** | Programaré **Crank-Nicolson** y haré un análisis de estabilidad con apoyo del G.D. Smith. | Requiere mi **Solver Lineal (Cap 6)**. |
| **T5: El. Finitos** | **Cap. 12.4** | Aplicaré la formulación débil para resolver problemas en geometrías complejas. | Requiere mi **Integrador (Cap 4)** y **Solver (Cap 6)**. |

---

## Mis Notas Estratégicas para el Éxito

### 1. Validación de Código
Cada vez que termine un módulo de mi librería (Fase 1), compararé mis resultados con los ejemplos resueltos del **Burden & Faires** y con funciones equivalentes de librerías profesionales (SciPy/Matlab). El objetivo es garantizar que mis algoritmos tienen un error residual controlado antes de usarlos en los trabajos del Máster.

### 2. Análisis de Estabilidad y Convergencia
Especialmente para el Bloque 4, dedicaré tiempo extra a profundizar en el texto de **G.D. Smith**. Necesito justificar en mis memorias la elección de los pasos de tiempo ($\Delta t$) y espacio ($\Delta x$) basándome en el análisis de Von Neumann para evitar inestabilidades numéricas.

### 3. Calidad de las Memorias Científicas
Como ya domino la parte de implementación, enfocaré mi esfuerzo en la UNED en:
*   Generar gráficas de nivel profesional (Matplotlib/Plotly) para visualizar la evolución de las soluciones.
*   Documentar el código siguiendo estándares profesionales (limpieza, modularidad y comentarios técnicos).
*   Realizar un análisis crítico de los resultados, comparando la solución numérica con soluciones analíticas conocidas cuando sea posible.

---
**Plan actualizado para el año académico 2026.**
