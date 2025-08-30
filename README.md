# **UNIVERSIDAD AUTÓNOMA DEL ESTADO DE HIDALGO**  
**Instituto de Ciencias Básicas e Ingeniería**  
**Centro de Investigación en Tecnologías de Información y Sistemas**  
**Licenciatura en Ciencias Computacionales**  
**Razonamiento Aproximado**  
**Octavo Semestre**

---

## **Reporte de Práctica/Proyecto**

**Título:**  
**“Tar01_RazAprx”**

**Integrante:**  
Gómez Daniel Aimar Jair

**Catedrático:**  
Dr. Virgilio López Morales  

---

## **Resumen**
Este proyecto se enfocó en crear un modelo que calcula propinas tomando en cuenta dos variables: el nivel de **servicio (S)** y la **calidad percibida (Q)**, cada una con un peso diferente.  
El modelo divide las propinas en tres tramos: **bajo**, **medio** y **alto**, lo que ayuda a entender cómo cambia la propina dependiendo de la experiencia del cliente.  
Además, se programó un script en Python para graficar y analizar casos prácticos.

---

## **Introducción**
El objetivo fue implementar una función con respecto al servicio y la calidad, donde dado un valor de servicio y calidad se asigna una propina.  

La lógica principal es que el **servicio** tenga un mayor peso que la **calidad**, ya que se puede inferir que al visitar un restaurante de lujo, damos por sentado que la comida será de calidad; por lo tanto, el servicio tendrá más peso.

---

## **Planteamiento del problema**
La pregunta central fue:  
> ¿Cómo calcular una propina justa cuando el servicio y la calidad varían en una escala del 1 al 10?

Para resolverlo, se creó una **métrica ponderada** y, con tres pares de valores para `S` y `Q`, se calculó la propina para cada caso.

---

## **Objetivos**
- **General:**  
  Desarrollar un algoritmo sencillo para calcular propinas tomando en cuenta servicio y calidad.

- **Específicos:**  
  - Establecer umbrales que dividan la propina en tramos.  
  - Calcular las pendientes de cada tramo.  
  - Graficar los resultados para una mejor interpretación.  

---

## **Metodología**

### **1. Definición de parámetros**
- Peso del servicio:  
  $$
  w_s = 0.8
  $$

- Peso de la calidad:  
  $$
  w_c = 0.2
  $$

- Propina mínima:  
  $$
  y_{\min} = 5\%
  $$

- Propina fija:  
  $$
  y_{\fijo} = 15\%
  $$

- Propina máxima:  
  $$
  y_{\max} = 25\%
  $$

---

### **2. Cálculo de la métrica ponderada**
$$
M = (w_s \cdot S) + (w_c \cdot Q)
$$

---

### **3. Definición de umbrales**
$$
M_{\min} = 1, \quad
M_1 = 5, \quad
M_2 = 8, \quad
M_{\max} = 10
$$

---

### **4. Cálculo de pendientes**
- **Tramo bajo:**  
  $$
  m_1 = \frac{0.15 - 0.05}{5 - 1} = 0.025
  $$

- **Tramo alto:**  
  $$
  m_3 = \frac{0.25 - 0.15}{10 - 8} = 0.05
  $$

---

### **5. Implementación en Python**
Se creó un script con **NumPy** y **Matplotlib** para:  
- Calcular la propina según la métrica.  
- Graficar el comportamiento de la propina frente al servicio.  
- Marcar los casos analizados.

---

## **Resultados**

### **Casos prácticos**
| Caso | S   | Q   | Métrica (M) | Propina (y)   |
|-------|------|------|-------------|---------------|
| **A** | 2.9  | 8.0  | 3.92        | 0.123 (12.3%) |
| **B** | 5.0  | 8.0  | 5.60        | 0.150 (15.0%) |
| **C** | 8.5  | 6.0  | 8.00        | 0.150 (15.0%) |

---

### **Gráfica de resultados**
- Curvas para **Q=8** y **Q=6**.  
- Líneas verticales que marcan los cambios de tramo.  
- Puntos que muestran dónde se encuentran los tres casos evaluados.  

*(Aquí se pueden insertar las gráficas generadas con Matplotlib).*

---

## **Discusión**
El modelo muestra que:
- **En el tramo bajo**, la propina sube poco a poco conforme mejora el servicio.  
- **En el tramo medio**, la propina se mantiene en un estándar del 15%.  
- **En el tramo alto**, la propina vuelve a subir y puede alcanzar hasta el 25%.

Esto confirma que el peso del servicio es mayor, pero que la calidad también influye, logrando un cálculo más equilibrado.

---

## **Conclusiones**
- Se logró construir un modelo práctico y fácil de usar para calcular propinas.  
- El uso de ponderaciones y umbrales hace que el cálculo sea más justo y entendible.  
- Las gráficas ayudan mucho a visualizar y explicar el comportamiento del modelo.  

Para mejorar, se podría usar información real de clientes y ajustar las pendientes y los umbrales según los datos.

---

## **Bibliografía**
- Swokowski, E. W. (2011). *Álgebra y Trigonometría con Geometría Analítica*. Cengage Learning.  
- Documentación de [NumPy](https://numpy.org/) y [Matplotlib](https://matplotlib.org/).
