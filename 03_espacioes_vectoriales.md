---
layout: page
title: Espacios Vectoriales
---

## Introducción

Consideremos cantidades medibles que pueden definirse con un único valor como son: temperatura, masa, área, volumen, longitud, perímetro, rapidez, entre otras. Sin embargo, existen otras cantidades que no son posibles de definir completamente con un único valor: velocidad, aceleración, fuerza, momento lineal, entre otras

Partiremos de la intuición geométrica que tiene el estudiante de *vector* la cuál va asociada a cantidades mesurables que no son posibles definir con un único valor. Por lo general se hace referencia a que los vectores sob objetos que necesitan de dos valores para ser representados: magnitud y dirección.

En cursos como geometría analítica o mecánica vectorial les presentan los vectores como objetos geométricos que vienen definidos como tuplas de $$ n $$ elementos en un campo (en partícular el campo de los números reales $$ \mathbb{R} $$). Sin embargo esta es una mera representación de los vectores y en este curso veremos como abstraer las propiedades instrinsecas de estos objetos para generar una definición más general que no dependa del concepto geométrico de los vectores.

## Campos

Recordemos que un **campo** es un conjunto $$ K $$ junto con dos operaciones $$ + :K \times K \longrightarrow K $$ denominada "suma" y $$ \cdot :K \times K \longrightarrow K $$ denominada "producto" tales que para cualesquiera $$ a, b, c \in K $$ se cumple que:

1. La suma es asociativa: $$ a + (b + c) = (a + b) + c $$
2. Existe un neutro aditivo: $$ a + 0 = a $$
3. Existencia del inverso aditivo: $$ a + (-a) = 0 $$
4. La suma es conmutativa: $$ a + b = b + a $$
5. El producto es asociativo: $$ a \cdot (b \cdot c) = (a \cdot b) \cdot c $$
6. Existe un neutro multiplicativo: $$ a \cdot 1 = a $$
7. Existencia del inversoo multiplicativo: $$ a \cdot (a^{-1}) = 1 $$, para cualquier $a \in K\setminus \{0\} $$
8. El producto es conmutativo: $$ a \cdot b = b \cdot a $$
9. El producto se distribuye sobre la suma: $$ a \cdot (b + c) = a\cdot b + a\cdot c $$

De forma compacta, podemos decir que un conjunto $K$ tiene estructura de **campo** si la quinteta $$ \left(K, +, 0, \cdot, 1 \right) $$ cumple lo siguiente:

- $$ \left(K, +, 0 \right) $$ tiene estructura de grupo abeliano
- $$ \left(K\setminus\{0\}, \cdot, 1 \right) $$ tiene estructura de grupo abeliano
- Dados $$ a, b, c \in K $$ se tiene que $$ a \cdot (b + c) = a\cdot b + a\cdot c $$

para simplificar la notación siempre que se hable de un campo $$ K $$ se entenderá que se está haciendo referencia a la quinteta $$ \left(K, +, 0, \cdot, 1 \right) $$ con las propiedades previas.

### Ejemplos de campos

Algunos ejemplos de campos son:

- Los números racionales $$ \mathbb{Q} $$
- Los número reales $$ \mathbb{R} $$
- Los número complejos $$ \mathbb{C} $$
- Los campos $$ \mathbb{Z}_p $$ donde $$ p \in \mathbb{Z} $$ es un número primo

## Espacios vectoriales

De los cursos de geometría analítica I y II, el estudiante ha trabajado en los espacios euclidianos $$ \matbb{R}^2 $$ y $$ \matbb{R}^3 $$, principalemnte. En general el espacio euclidiano de dimensión $$ n $$ está definido como:

$$ \mathrm{R}^n = \{(x_1, \ldots, x_n) | x_i \in \mathbb{R}, para toda i = 1, \ldots, n \}$$ 

además se puede definir una operación "suma" $$ \oplus :\mathrm{R}^n \times \mathrm{R}^n \longrightarrow \mathrm{R}^n $$ como sigue:

$$ (x_1, \ldots, x_n) \oplus (y_1, \ldots, y_n)  = (x_1 + y_1, \ldots, x_m + y_n) $$

para cualesquiera (x_1, \ldots, x_n), (y_1, \ldots, y_n)  \in \mathbb{R}^n $$ y donde la $$ + $$ hace referencia a la suma en los números reales.

La operación suma definida previamente cumple las siguientes cuatro propiedades (las cuales son herencia del campo de los número reales):

1. La suma es asociativa
2. Existe un neutro aditivo
3. Existencia del inverso aditivo
4. La suma es conmutativa

También es posible definir una "producto por un escalar" $$ \odot : \mathbb{R} \times \mathrm{R}^n \longrightarrow \mathrm{R}^n $$ como sigue:

$$ \alpha \odot (x_1, \ldots, x_n)  = (x_1, \ldots, x_n) = (\alpha \cdot x_1, \ldots, \alpha \cdot x_n) $$

para cualesquiera (x_1, \ldots, x_n)  \in \mathbb{R}^n $$, $\alpha \in \mathbb{R} $$ y donde la $$ \cdot $$ hace referencia al producto en los números reales. Notemso que está función definida no es una operación en el sentido formal de la definición, sin embargo, por cuestiones prácticas realizaremos un abuso en la notación al llamarla operación.

La operación de producto por un escalar cumple las siguientes cuatro propiedades (debido, nuevamente, a la herencia del campo de los números reales):

5. $$ 1 \odot (x_1, \ldots, x_n) = (x_1, \ldots, x_n) $$
6. $$ (\alpha \cdot \beta) \odot (x_1, \ldots, x_n) = \alpha \odot \left(\beta \odot (x_1, \ldots, x_n) \right) $$
7. $$ \alpha \odot \left((x_1, \ldots, x_n) \oplus (y_1, \ldots, y_n) \right)  = \left( \alpha \odot (x_1, \ldots, x_n) \right) \oplus \left( \alpha \odot (y_1, \ldots, y_n) \right) $$
8. $$ (\alpha + \beta) \odot (x_1, \ldots, x_n) = \left( \alpha \odot (x_1, \ldots, x_n) \right) \oplus \left( \beta \odot (x_1, \ldots, x_n) \right) $$

Buscando abstraer y generalizar estas propiedades para otros tipos de conjuntos en los cuales se les pueda definir operaciones "suma" y "producto por un escalar" se obtiene la siguiente definición.

**Definición** Un espacio vectorial $$ V $$ sobre un campo $$ K $$ consiste en una cuarteta $$ (V, K, \oplus, \odot) $$ con $$ V $$ un conjunto, $$ K $$ un campo, $$ \oplus $$ una operación llamada suma y $$ \odot $$ una "operación" llamada producto por escalar, respectivamente, tal que se cumplen las siguientes propiedades:

1. **La suma es asociativa:** Para cualesquiera $$ x, y, z \in V $$ se tiene $$ x \oplus (y \oplus z ) = (x \oplus y) \oplus z $$
2. **Existe un neutro aditivo:** Existe un elemento $$ e \in V $$ tal que $$ x \oplus e = x $$, para todo $$ x \in V $$
3. **Existencia del inverso aditivo:** Para todo elemento $$ x \in V $$, existe un elemento $$ y \in V $$ tal que $$ x \oplus y = e $$
4. **La suma es conmutativa:** Para cualesquiera $$ x, y \in V $$ se tiene $$ x \oplus y = x \oplus y $$
5. **Existencia del neutro en el producto por escalar:** Para todo elemento $$ x \in V$ se cumple que $$ 1 \odot x = x $$, donde $$ 1 $$ es el neutro multiplicativo en el campo.
6. **Asociatividad del producto por un escalar:** Para todo elemento $$ x \in V $$ y escalares $\alpha, \beta \in K $$ se tiene $$ (\alpha \cdot \beta) \odot x = \alpha \odot \left(\beta \odot x \right) $$
7. **Distribución del producto por un escalar sobre la suma:** Para cualesquiera $$ x, y \in V $$ y escalar elementos $\alpha \in K $$ se tiene $$ \alpha \odot \left(x \oplus y \right)  = \left( \alpha \odot x \right) \oplus \left( \alpha \odot y \right) $$
8. **Distribución de la suma escalar:** Para todo elemento $$ x \in V $$ y escalares $\alpha, \beta \in K $$ se tiene $$ (\alpha + \beta) \odot x = \left( \alpha \odot x \right) \oplus \left( \beta \odot x \right) $$

> **Notación:**

> La suma vectorial $$ \oplus $$ la representaremos como $$x \oplus y = x + y$$ siempre que no exista confución sobre cuando es una suma escalar (en el campo) y cuando es una suma vectorial (en el espacio vectorial).

> El neutro aditivo en la suma vectorial lo representaremos como $$ e =  0 $$ siempre que no exista cinfución sobre cuando es el neutro aditivo escalar (en el campo) y cuando es el neutro aditivo vectorial (en el espacio vectorial)

> El producto por un escalar $$ \odot $$ lo representaremos como $$ \alpha \odot x = \alpha x $$ siempre que no exista confución sobre cuando es un producto escalar (en el campo) y cuando es un producto por un escalar (en el espacio vectorial). 

### Ejemplos

- Los espacios euclidianos $$ \mathbb{R}^n $$ con la suma y producto por un escalar definidos entrada a entrada
- En términos generales cualquier tupla de $$ n $$ elementos sobre un campo K $$ ( \mathbb{K}^n) $$ con la suma y producto por un escalar definidos entrada a entrada
- El conjunto de los polinomios con coeficientes en un campo $$ K $$ ($$\mathbb{P} (K)$$) con las operaciones suma y producto por un escalar usuales de los polinomios
- El conjunto de todas las funciones de un conjuto no vacío $$ S $$ a un campo $$ K $$ con las operaciones de suma u producto por un escalar definidas como sigue:

$$ (f + g)(s) = f(s) + g(s) \qquad \text{y} \qquad \left(cf\right) = c\left(f(s)\right) $$

- El conjunto de matrices de $$ m \times n$$ con coeficientes en un campo $$ K $$ ($$M_{m \times n} (K) $$) con la suma y producto por un escalar usuales de las matrices

