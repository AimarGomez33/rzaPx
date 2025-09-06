# Reporte de práctica  
**Manejo de matrices y ecuación cuadrática en MATLAB**

---

## Resumen

El presente trabajo tuvo como objetivo familiarizarse con el entorno MATLAB, ejecutando operaciones básicas con matrices, verificando comparaciones lógicas y resolviendo una ecuación cuadrática mediante la fórmula general.  
Se utilizaron comandos fundamentales (`det`, `inv`, `isinf`, `isnan`, `any`, `all`), se realizaron verificaciones numéricas y se utilizó la representación gráfica para comprobar resultados.  
Las actividades mostraron la utilidad de MATLAB en el análisis matemático, la lógica de programación y la visualización de datos.

---

## Introducción

El manejo de matrices y la solución de ecuaciones cuadráticas son pilares básicos en el estudio de las matemáticas aplicadas y la computación. MATLAB ofrece un entorno que permite resolver este tipo de problemas de manera directa y visual, facilitando tanto el cálculo como la interpretación gráfica.  

En esta práctica se ingresaron matrices, se calcularon transpuestas, determinantes e inversas, además de realizar comparaciones lógicas. Finalmente, se aplicó la fórmula general para resolver una ecuación cuadrática y se representó gráficamente para validar las raíces obtenidas.

---

## Desarrollo

### 1.1) Ingreso de matrices

Se definieron las matrices:

```matlab
M1 = [ 1  -3   5;
      -5   4   7;
       8   3  -2];

M2 = [ 9  -5   4;
      -1  -6  -7;
       2   3  -3];

M3 = [-5  -4   6;
      -2   8   1;
       4   5  -7];
```

---

### 1.2) Operaciones con matrices

- **Transpuestas:** se calcularon `Mi.'`.  
- **Determinantes:**  
  - det(M1) = -402  
  - det(M2) = 472  
  - det(M3) = 93  
- **Inversas:** todas las matrices son invertibles y se calcularon con `inv(Mi)`.

---

### 1.3) Script `Matrices01.m`

Se guardaron los cálculos de transpuestas, determinantes e inversas en un archivo MATLAB.

---

### 1.4) Cálculo de `Cal01`

\[ Cal01 = (M1 .* M2) + (M4 ./ M5) \]

```matlab
Cal01 = (M1 .* M2) + (M4 ./ M5);
```

- El primer término corresponde a la multiplicación elemento a elemento.  
- El segundo término genera cocientes celda por celda.  
- La suma refleja ajustes positivos o negativos dependiendo del signo de `M4./M5`.

---

### 1.5) Comparaciones

- `Comp1 = M1 > M2` y `Comp2 = M1 < M2` → comparaciones directas elemento a elemento.  
- `Comp3 = M1 == M2` → devuelve 1 solo cuando los elementos son iguales.  
- `Comp4 = (M1+M2) >= (M2+M3)` → se simplifica a `M1 >= M3` porque `M2` se cancela.  
- `Comp5 = M1([2 3]) > M3([2 3])` → usa índices lineales, no filas completas.

---

### 1.6) Comparaciones lógicas

- **Comp6:** `isinf(...)` resultó todo 0, ya que no hubo divisiones entre cero.  
- **Comp7:** `isnan(...)` resultó todo 0, ya que no hubo indeterminaciones.  
- **Comp8:** `any(Comp7)` dio `[0 0 0]` porque ninguna columna tenía valores verdaderos.  
- **Comp9:** `all(M2-3)` dio `[1 1 0]` debido a la presencia de un cero en la tercera columna.

---

### 1.8 y 1.9) Scripts adicionales

- Los resultados de 1.4 a 1.6 se guardaron en `Matrices2.m`.  
- Se utilizó `clear` para limpiar la memoria de trabajo.

---

## Actividad 1.2 — Ecuación cuadrática

Se resolvió la ecuación:

\[ -1.5x^2 + 6x - 5.63 = 0 \]

Definiendo coeficientes en MATLAB:

```matlab
a = -1.5;
b = 6;
c = -5.63;
```

**Soluciones con fórmula general:**

```matlab
x1 = (-b + sqrt(b^2 - 4*a*c)) / (2*a);
x2 = (-b - sqrt(b^2 - 4*a*c)) / (2*a);
```

Resultados aproximados:  
- x1 ≈ 1.5033  
- x2 ≈ 2.4966  

**Verificación:**

```matlab
v1 = a*x1^2 + b*x1 + c;   % ≈ 0
v2 = a*x2^2 + b*x2 + c;   % ≈ 0
```

**Gráfica de la ecuación:**

```matlab
x = [x1-2 : 0.01 : x2+2];
y = a*x.^2 + b*x + c;
plot(x,y);
grid;
```

- La parábola abre hacia abajo (porque a < 0).  
- Los cortes con el eje X coinciden con x1 y x2.  
- Con *Data tips* se confirmó que los valores gráficos coinciden con los calculados.

---

## Comentarios finales

### 1. Utilidad de las actividades y novedades visualizadas  
Las actividades fueron útiles porque reforzaron el uso de operaciones básicas en MATLAB. Lo más novedoso fue comprobar que los resultados se pueden verificar gráficamente, lo cual hace más fácil interpretar los cálculos. La herramienta *Data tips* ayudó a confirmar de manera visual los puntos de intersección.

### 2. Esclarecimiento de dudas sobre métodos y lógica de programación  
Se aclararon dudas sobre la diferencia entre operaciones algebraicas y elemento a elemento (`*` vs `.*`, `/` vs `./`). También se entendió mejor cómo funcionan las funciones lógicas (`any`, `all`, `isinf`, `isnan`) y la importancia de la indexación lineal en MATLAB.

### 3. Análisis y manipulación de códigos  
Al cambiar valores en las matrices M4 y M5 se pueden generar divisiones por cero y observar resultados `Inf` o `NaN`.  
En la cuadrática, modificar los coeficientes permite experimentar con raíces múltiples o complejas.  
Ajustar el rango de graficación cambia la forma en que se visualiza la parábola y mejora la interpretación.

---

## Conclusiones

1. Con MATLAB es muy fácil hacer operaciones con matrices que manualmente serían complicadas.  
2. Se entendió mejor la diferencia entre operadores algebraicos y elemento a elemento.  
3. La ecuación cuadrática fue un buen ejemplo de cómo unir cálculo, verificación y gráfica.  
4. Las funciones lógicas (`isinf`, `isnan`, `any`, `all`) son muy útiles para validar y depurar resultados.  
5. Manipular el código ayuda a comprender mejor y fomenta el aprendizaje activo.  

---

## Referencias

- MathWorks. *MATLAB Documentation*. Disponible en: [https://www.mathworks.com/help/matlab](https://www.mathworks.com/help/matlab)  
- Apuntes de clase: Razonamiento Aproximado, U.A.E.H.  
- Notas personales del laboratorio.
