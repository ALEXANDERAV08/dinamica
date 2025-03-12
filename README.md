# dinamica
# APUNTES_DINAMICA_DE_SISTEMAS-PRIMER_CORTE_25-01
Apuntes dinamica de sistemas 
# TRANSFORMADA DE LAPLACE
## 1. Sistema
Se define como sistema a una combinacion de componentes que trabajan conjuntamente para alcanzar un objetivo especifico, estos omponentes pueden ser representados mediante reglas o principios que 
relacionan las salidas con las entradas, siguiendo ciertas reglas o principios que determinan como las entradas se transforman en salidas.

![image](https://github.com/user-attachments/assets/c700e3b6-761f-4ef2-a49b-c98a3f75df17)

## 2. Sistemas Dinamicos 
Un sistema dinamico es aquel donde lo que sucede ahora (su salida) esta influenciada por lo que ocurrio antes (su entrada) si su salida depende solo de la entrada actual, el sistema se conoce como 
ESTATICO En resumen un sistema dinamico es aque donde las salidas estan influenciadas por entradas anteriores, mientras que un sistema que solo responde a las entradas del momento presente se denomina 
sistema estatico

## 3.Proceso
Un proceso es el conjunto de acciones organizadas que permiten crear o desarrollar un producto o alcanzar un objetivo. En el campo del control, a veces se utiliza como equivalente a planta, aunque en 
un sentido más preciso no son términos intercambiables.

## 4. Planta
Una planta se refiere al conjunto de componentes físicos que permiten ejecutar un proceso, como maquinaria o infraestructura. Este conjunto puede ser descrito mediante modelos matemáticos y representado 
como uno o varios sistemas interconectados que permiten entender y controlar su comportamiento.

# MODELOS DINAMICOS 
Los modelos dinámicos en control buscan describir matemáticamente cómo las variables de interés cambian con el tiempo. Se representan mediante funciones 

f(t) y sus derivadas, como $\frac{dt}{df(t)}$, para cuantificar la tasa de cambio de dichas variables.

## RECORDANDO CALCULO DIFERENCIAL

![image](https://github.com/user-attachments/assets/e2269848-5c80-44d9-91c3-eaab9efa32f8)

La derivada de una funcion **f(x)** mide la tasa de cambio instantaneo en un punto y se define como:

$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$

Esto representa la pendiente de la recta a la curva en x.

# REGLAS DE DERIVACION

**Regla de Potencia**

si $f(x) = x^n$ , entonces

$f'(x) = nx^n-1$

**Ejemplo:**

si $f(x) = x^3$, entonces $f'(x) = 3x^2$

**Regla del Producto**

si $f(x)=u(x)v(x)$, entonces.

$f'(x)=u'v+uv'$

**Ejemplo:**

si $f(x)=x^2 sen(x)$, entonces.

$f'(x)=2xsen(x) + x^2 cos(x)$

**Regla del Cociente:**

si $f(x)=\frac{u(x)}{v(x)}$, entonces.

$f'(x)=frac{u'v - uv'}{v^2}$

**Ejemplo:**

si $f(x)=\frac{x}{x+1} $, entonces 

$f'(x)=\frac{(1)(x+1)-(x)(1)}{(x+1)^2}$     $= \frac{1}{(x+1)^2}$

**Regla de la Cadena:**

si y=f(g(x)), entonces.

$\frac{dy}{dx}=f'(g(x))* g'(x)$$

**EJEMPLO**

Si $f(x)=sen(x^2)$, entonces.

$f'(x)=cos(x^2)*2x = 2xcos(x^2)$

## Derivadas de funciones comunes

![image](https://github.com/user-attachments/assets/1ed3d45d-15d2-4197-b809-18af999a78bd)

## Sistemas lineales y no lineales

- un sistema se considera lineal cuando cumplu con el principio de superposicion, lo que significa que la respuesta a la suma de dos entradas es igual a la suma de las respuestas individuales.
- También cumple con la proporcionalidad, es decir, si la entrada se escala por un factor, la salida también lo hace en la misma proporción.
- Un sistema no lineal no cumple con la superposición ni con la proporcionalidad.
- Los sistemas no lineales pueden linealizarse alrededor de un punto de operación para facilitar su análisis.

**Sistemas lineales**
- Circuito RC (Resistor y Capacitor en serie): La salida (voltaje en el capacitor) es proporcional a la entrada (voltaje aplicado).
  
  ![image](https://github.com/user-attachments/assets/c1e1fe3a-0239-4453-bd46-7555c5be15db)

- Sistema de masa-resorte sin fricción: La fuerza es proporcional al desplazamiento, cumpliendo la ecuación 𝐹=𝑘𝑥
  
![image](https://github.com/user-attachments/assets/2835da89-c729-4fd5-90f7-18e64294a8e0)

**Sistemas no Lineales**
-Sistema de péndulo: La ecuación de movimiento incluye términos senoidales, lo que lo hace no lineal.
![image](https://github.com/user-attachments/assets/a38d5fbb-ea5d-4d43-9cd4-4615fb6be534)

## MODELAMIENTO Y VALIDACION
El modelamiento consiste en representar un sistema fisico mediante ecuacines metematicas basadas en principios fisicos, como la mecanica, la termodinameica o la electronica sin embargo estos 
modelos pueden representar dudas debido a simplificaciones.
La **validacion** es el proceso de comprobar que el modelo matematico representa decuadamente el comportamiento real del sistema. para ell se comparan las salidas del modelo con las mediciones
experimentales y si la diferencia no es aceptable se ajusta el modelo.

## Transformada de LaPlace
La trnsforma de laplace es una tecnica que transforma funciones que dependen del tiempo en una forma mas simplificada y facil de manejar, especialmente cuando se trabaja con ecuaciones diferenciales, en vez de resolver estas ecuaciones directamente,la transformada de laplace las convierte en ecuaciones algebraicas simples.
basicamente toma una funcion en el tiempo y la transforma el dominio de la frecuencia donde se puede hacer calculos mas sencillos. 

![image](https://github.com/user-attachments/assets/bd13df49-0c43-4438-a19b-47a7421f2281)

$$\mathcal{L}\{f(t)\} = F(s) = \int_{0}^{\infty} e^{-st} f(t) \, dt$$

**Ejemplo transformada de una funcion exponencial**

$f(t) = e^-3t$

**su transformada de Laplace es:**

$\mathcal{L} \{ e^{-3t} \} = \frac{1}{s+3}, \quad \text{para } s > -3$

**Ejemplo Transformada de una derivada**

Si x(t) es una funcion con transformada X(s), entonces.

$\mathcal{L}\frac{dx}{dt} = sX(s)-x(0)$

Si x(0)=2 y queremos la transformada de $\frac{dx}{dt}$

$\mathcal{L}\frac{dx}{dt} = sX(s)-2$

**RESOLVER ECUACION DIFERENCIAL CON LAPLACE**

**Dada la ecuación diferencial:**

$\frac{d^2x}{dt^2} + 4x = 0$,      $x(0)=1$,        $x'(0)=0$.

**Tomamos la transformada de Laplace:**

$s^2x(s) - sx(0) - x'(0) + 4x(s) = 0$

**Sustituyendo valores iniciales:**

$s^2x(s) - s + 4x(s) = 0$

**Factorizamos:**

$(s^2+4)X(s)=s$

**Despejamos X(s):**

$X(s)\frac{s}{s^2+4}$

**Aplicamos la transformada inversa:**

$x(t)=cos(2t)$

## Transformada Inversa de Laplace

La transformada inversa de Laplace se usa para encontrar la función en el dominio del tiempo x(t) a partir de su representación en el dominio de Laplace X(s).

![image](https://github.com/user-attachments/assets/b3301102-039a-4dd1-b061-603062096ef7)

$x(t) = \mathcal{L}^{-1} \{X(s)\} = \frac{1}{2\pi j} \int_{c - j\infty}^{c + j\infty} X(s) e^{st} \, ds$

Sin embargo, en la práctica se usa la descomposición en fracciones parciales y la transformada inversa de Laplace.

**Ejemplo Transformada inversa de una función racional**

$X(s)\frac{2}{s^2+3}$

**Buscamos su transformada inversa. Sabemos que:**

$\mathcal{L^{-1}}(\frac{1}{s+a}) = e^-at$

**Por lo tanto:**
$x(t) = 2e^{-3t}, \quad t \geq 0.$

**Ejemplo Transformada inversa con fracciones Parciales**

**Dado**

$X(s)\frac{s+2}{s^2+4s+5}$

**Factorizamos el denominador:**

$s^2+4s+5 = (s+2)^2 + 1$

**sabemos que la inversa de:**

$\frac{s+a}{(s+a)^2+b^2}$   es  $e^{-at} cos(bt)$

**Por lo que:**

$x(t) = e^{-2t} cos(t)$,  $t≥0$

## Propiedades

**linealidad**
![image](https://github.com/user-attachments/assets/8fca1b01-fa6d-4b33-9642-77e5f7d9dc5b)

**desplazamiento en t**
![image](https://github.com/user-attachments/assets/21b8b292-f20a-4afa-9116-0a54111fb3ab)

**Desplazamiento en s**
![image](https://github.com/user-attachments/assets/6b02223e-c286-4e07-9ad0-cf57fbdc0985)

**Escalon en t**
![image](https://github.com/user-attachments/assets/69ad49bf-1d0b-4b06-87eb-6b28b312fe9d)

## Descomposicion en Fracciones Parciales

La descomposición en fracciones parciales es un método algebraico utilizado para descomponer una fracción racional en una suma de fracciones más simples. Es 
especialmente útil en integración y en la Transformada de Laplace.

**CASOS DE DESCOMPOSICION EN FRACCIONES PARCIALES**
**CASO 1:**
Cuando Q(s) tiene raíces reales distintas:
Si el denominador se puede factorizar en términos lineales distintos, se descompone como:

![image](https://github.com/user-attachments/assets/01a9e712-3b70-45b3-9551-2f816a0c68d5)

Donde la fraccion se escribe como la suma de términos de la forma:

![image](https://github.com/user-attachments/assets/f85ddce9-9f92-4a58-b2b3-8c9900cf37c3)

**CASO 2:**
Cuando Q(s) tiene raíces repetidas:
Si un factor se repite 
m veces en el denominador, se debe incluir términos hasta la potencia repetida:

![image](https://github.com/user-attachments/assets/efc428f6-cbb5-4b96-9380-93b4ebf912ec)

**EJEMPLO**

$G(s)\frac{2s^+6s+5}{(s+2)+(s+1)^2}$  =  $\frac{A}{S+2} + \frac{B}{S+1} + \frac{C}{(S+1)^2}$ 

$2S^2+6S+5=A(S+1)^2 + B(S+2)(S+1)^2 + C(S+2)$

1. $2 = A + B$

2. $6 = 2A + 3B + C$

3. $5 = A + 2B + 2C$

**DESPEJAR A DE LA PRIMERA ECUACION:**
A=2-B
**SISTITUIR EN LA SEGUNDA ECUACION:**
2. 2(2-B)+3B+C=6

   4-2B+3B+C=6

   4+B+C=6

   B+C=2

**SUSTITUIR EN LA TERCERA ECUACION**

3.  2-B+2B+2C=5

    B+C=2

**OPERAMOS LOS DOS RSULTADOS**

B+C=2 * (-1)

B+2C=3

**C= 1**

**Remplazamos en las demas ecuaciones**

B+C=2

B+1=2

B=2-1

**B=1**

A+B=2

A+1=2

A=2-1

**A=1**

**CASO 3:**
**Cuando Q(s) tiene raices complejas**

Si un término del denominador no puede factorizarse en términos lineales reales, como 
s^2+a^2, se usa:

![image](https://github.com/user-attachments/assets/5094142b-87f0-4a0e-a79c-4bb7d37c6e5c)


$G(s)= \frac{P(s)}{Q(s)} = \frac{P(s)}{(s^2+b_1 s +c_1)(s^2+b_2 s +c_2)...........(s^2+b_n s + c_n )}$


$G(s)= \frac{A_s+B}{s^2+b_1 s +c_1} + \frac{C_s+D}{s^2+b_2 s +c_2}+........ \frac{M_s+N}{s^2+b_n s +c_n}$

**EJERCICIO**

$G(s)= \frac{S^2+2S+3}{(S^2+2S+2)(S^2+2S+5)}$

$\frac{A_s+B}{S^2+2S+2} + \frac{C_s+D}{S^2+2S+5}$

$S^2+2S+3 = (A_s+B)(S^2+2S+5)+(C_S+D)(S^2+2S+2)$

1.   A + C = 0
2.  2A + B + 2C + D = 1
3.  5A + B + 2C + 2D = 2
4.  5B + 2D = 3

**Despejamos A:**

A = -C

**Remplazamos en la ecuacion numero 2.**

2(-C) + B + 2C + D = 1

-2C + B +2C + D = 1

***B + D = 1**

**Operamos con la ecuacion cuatro**

B + D = 1  *(-2)

5B + 2D = 3

R:
3B = 1

**B** = $\frac{1}{3}$

**En la ecuacion numero tres**

5(-C) + 2B + 2C + 2D = 2

-5C + 2B + 2C + 2D = 2

2B - 3C + 2D = 0

**Operamos B + D = 1 Con 2B - 3C + 2D = 2**

B + D = 1  (-2)

2B - 3C + 2D = 2

-3C = 0

**C = 0**

## SOLUCION ECUACIONES DIFERENCIALES

**FRACCIONES PARCIALES METODO RESUMIDO**

El método resumido consiste en utilizar las raíces del denominador para simplificar el sistema de ecuaciones necesario para encontrar las constantes en la 
descomposición en fracciones parciales. Al sustituir valores estratégicos de s, se eliminan términos, reduciendo los cálculos.

**CASO 1:**
Raices Reales Diferentes dada una duncion racional de la forma:

$F(s)=\frac{A(s)}{B(s)}$

done B(s) se suede descomponer en factores leneales distintos, se escribe como:

$F(s)=\frac{a_1}{s+p_1} + \frac{a_2}{s+p_2} +............+\frac{a_n}{s+p_n}$

para encontar los coeficientes $a_k$, multiplicamos ambos lados por $(s + p_k)$ y evaluamos en s = -p_k lo que permite cancelar los terminos 
innecesarios y despejar $a_k$:

$a_k = \left((s + p_k) \frac{A(s)}{B(s)} \right)_{s = -p_k}$

**Ejemplo caso 1**
Descomponer en fracciones parciales:

$F(s)\frac{5_s + 3}{(s + 2)(s - 1)}$

**Paso 1: Plantear la descomposición**

$\frac{5_s + 3}{(s + 2)(s - 1)} = \frac{a_1}{s + 2} + \frac{a_2}{s - 1}$

**Paso 2: Multiplicar por el denominador común**

$5s + 3 = a_1(s - 1) + a_2(s + 2)$

**Paso 3: Evaluar en s=−2 y s=1**

**Para s=−2:**

$5(-2) + 3 = a_1(-2 - 1) + a_2(0)$

$-10 + 3 = -3a_1$      $a_1 = \frac{7}{3}$

**Para s = 1:**

$5(1) + 3 = a_1(0) + a_2(1 + 2)$

$5 + 3 = 3a_2$        $a_2 = \frac{8}{3}$

**Resultado Final**

$\frac{5s + 3}{(s + 2)(s - 1)} = \frac{7}{3(s + 2)} + \frac{8}{3(s - 1)}$

## Transformada Inversa de Laplace para el Caso 1: Raíces reales diferentes 

La Transformada Inversa de Laplace para el Caso 1: Raíces reales diferentes se basa en la descomposición en fracciones parciales de la función de transferencia F(s).
Dado:

$F(s) = \frac{A(s)}{B(s)} = \sum_{k=1}^{n} \frac{a_k}{s + p_k}$

La transformada inversa de Laplace de cada término de la suma se obtiene usando la propiedad básica:

$\mathcal{L}^{-1} \left( \frac{1}{s + p_k} \right) = e^{-p_k t}$

Por lo tanto, aplicando la transformada inversa a F(s):

$f(t) = \sum_{k=1}^{n} a_k e^{-p_k t}$

Este resultado muestra que la solución en el dominio del tiempo es una combinación lineal de exponentes decrecientes, donde los coeficientes akdependen de la expansión en 
fracciones parciales.

**CASO 2:**
