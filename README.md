
# 💻 Bitácora de Aprendizaje: Diseño de Circuitos Digitales

### Universidad Nacional de Loja
**Facultad:** Facultad de la Energía, las Industrias y los Recursos Naturales No Renovables  
**Carrera:** Computación  
**Asignatura:** Diseño de Circuitos  
**Estudiante:** Elvis Guayllas  
**Unidad:** 1 - Fundamentos de lógica combinacional  
**Período académico:** Septiembre 2026 - Marzo 2027  

---

## 📖 Introducción

Los circuitos digitales constituyen una parte esencial de los sistemas informáticos. Su funcionamiento se basa en señales binarias que representan dos estados: cero y uno.

En esta bitácora se recopilan los conocimientos adquiridos durante la primera unidad de Diseño de Circuitos, incluyendo representaciones numéricas, operaciones lógicas, simplificación de funciones y construcción de circuitos aritméticos.

El propósito es relacionar los conceptos teóricos con situaciones prácticas que permitan comprender cómo funcionan los componentes digitales de una computadora.

## 🎯 Objetivos

- Identificar los sistemas numéricos utilizados en electrónica digital.
- Comprender el funcionamiento de las compuertas lógicas.
- Aplicar propiedades del álgebra de Boole.
- Simplificar funciones mediante mapas de Karnaugh.
- Analizar sumadores, restadores y comparadores digitales.

---

# 🟢 Semana 1: Representación digital y operaciones lógicas

## 1. El lenguaje binario

Las computadoras utilizan bits para representar información. Cada bit puede adoptar un valor de 0 o 1.

Los sistemas numéricos más utilizados son:

| Sistema | Base | Características |
|---|---|---|
| Binario | 2 | Utiliza 0 y 1 |
| Octal | 8 | Utiliza dígitos del 0 al 7 |
| Decimal | 10 | Utiliza dígitos del 0 al 9 |
| Hexadecimal | 16 | Utiliza dígitos del 0 al 9 y letras A-F |

### Ejemplo práctico: convertir 26 a binario

Dividimos sucesivamente entre dos:

| División | Cociente | Residuo |
|---|---|---|
| 26 / 2 | 13 | 0 |
| 13 / 2 | 6 | 1 |
| 6 / 2 | 3 | 0 |
| 3 / 2 | 1 | 1 |
| 1 / 2 | 0 | 1 |

Leyendo los residuos de abajo hacia arriba:

**26 decimal = 11010 binario**

Comprobación:

26 = 16 + 8 + 2

### Conversión a hexadecimal

Agrupamos los bits de cuatro en cuatro:

0001 1010

Resultado:

**26 decimal = 1A hexadecimal**

## 2. Representación de números negativos

El complemento a dos permite almacenar números enteros negativos usando una cantidad fija de bits.

Ejemplo: representar -6 utilizando 8 bits.

1. Número positivo: `00000110`
2. Invertimos los bits: `11111001`
3. Sumamos uno: `11111010`

Resultado:

**-6 = 11111010 (8 bits)**

## 3. Códigos digitales

Además de representar números, los sistemas digitales utilizan códigos para organizar la información.

| Código | Aplicación |
|---|---|
| BCD | Representación individual de dígitos decimales |
| Gray | Reduce cambios simultáneos entre códigos consecutivos |
| ASCII | Representación de caracteres |

Ejemplo BCD:

El número decimal 47 se representa como:

`0100 0111`

## 4. Compuertas lógicas

Las compuertas lógicas permiten tomar decisiones a partir de señales binarias.

| Compuerta | Función | Ejemplo |
|---|---|---|
| AND | Todas las entradas deben ser 1 | A · B |
| OR | Al menos una entrada es 1 | A + B |
| NOT | Invierte una entrada | A' |
| NAND | Negación de AND | (A · B)' |
| NOR | Negación de OR | (A + B)' |
| XOR | Entradas diferentes | A ⊕ B |
| XNOR | Entradas iguales | (A ⊕ B)' |

### Tabla de verdad de XOR

| A | B | Salida |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### Aplicación real

Una lámpara de advertencia puede encenderse cuando uno de dos interruptores está activo, pero no ambos.

La expresión es:

`L = A XOR B`

**Aprendizaje:** Las compuertas permiten construir sistemas que responden automáticamente a diferentes condiciones.

---

# 🔵 Semana 2: Expresiones booleanas y simplificación

## 1. ¿Qué es el álgebra de Boole?

Es una herramienta matemática utilizada para representar y transformar expresiones lógicas.

Sus variables trabajan con dos posibles valores: verdadero (1) y falso (0).

## 2. Propiedades fundamentales

| Propiedad | Ejemplo |
|---|---|
| Identidad | A + 0 = A |
| Complemento | A + A' = 1 |
| Idempotencia | A · A = A |
| Absorción | A + AB = A |
| Conmutativa | A + B = B + A |
| Distributiva | A(B + C) = AB + AC |

## 3. Leyes de De Morgan

Estas leyes permiten transformar operaciones negadas.

Primera ley:

`(A · B)' = A' + B'`

Segunda ley:

`(A + B)' = A' · B'`

Son importantes porque facilitan la construcción de circuitos con compuertas universales.

## 4. Ejercicio de simplificación

Consideremos la función:

`F = AB + AB'`

Factorizamos A:

`F = A(B + B')`

Sabemos que:

`B + B' = 1`

Entonces:

`F = A · 1`

Resultado final:

**F = A**

### Interpretación

Inicialmente, la expresión utiliza dos productos y una suma lógica.

Después de simplificar, la salida depende únicamente de A.

Esto demuestra que el álgebra de Boole puede reducir la complejidad de un circuito.

## 5. Formas canónicas

Las funciones booleanas pueden representarse mediante:

**SOP (Suma de Productos):**

Se obtiene combinando los minitérminos donde la salida vale 1.

**POS (Producto de Sumas):**

Se obtiene combinando los maxitérminos donde la salida vale 0.

### Ejemplo

Supongamos la función OR de dos variables:

| A | B | F |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Forma SOP canónica:

`F = A'B + AB' + AB`

Forma simplificada:

`F = A + B`

Forma POS canónica:

`F = (A + B)`

**Aprendizaje:** La simplificación conserva el comportamiento del circuito mientras reduce los elementos lógicos necesarios.

---

# 🟣 Semana 3: Mapas de Karnaugh y compuertas universales

## 1. ¿Para qué sirve un mapa de Karnaugh?

Es un procedimiento gráfico que permite simplificar funciones booleanas agrupando combinaciones que producen el mismo resultado.

Su principal ventaja es facilitar la eliminación de variables innecesarias.

## 2. Reglas principales

- Las agrupaciones deben contener 1, 2, 4, 8 o 16 celdas.
- Se agrupan principalmente los valores iguales a 1 para obtener SOP.
- Los grupos deben ser rectangulares.
- Los extremos opuestos del mapa pueden considerarse adyacentes.
- Una celda puede pertenecer a varios grupos.
- Las condiciones indiferentes pueden aprovecharse cuando simplifican la función.

## 3. Ejercicio con tres variables

Consideremos:

`F(A,B,C) = Σm(0,1,2,3)`

Construimos el mapa:

| A \ BC | 00 | 01 | 11 | 10 |
|---|---|---|---|---|
| 0 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 |

Los cuatro unos forman un grupo.

En ese grupo, B y C cambian de valor, pero A permanece en cero.

Por tanto:

**F = A'**

### Interpretación

Una función que inicialmente incluía tres variables se reduce a una sola inversión lógica.

## 4. Compuertas universales

Las compuertas NAND y NOR son universales porque permiten implementar cualquier función booleana.

### Construcción de NOT con NAND

`A' = A NAND A`

### Construcción de NOT con NOR

`A' = A NOR A`

### Construcción de AND con NAND

Primero se calcula:

`X = A NAND B`

Luego se invierte:

`F = X NAND X`

Resultado:

`F = A · B`

## 5. Condiciones indiferentes

En determinadas funciones existen combinaciones de entrada que nunca se presentan o cuyo resultado no importa.

Estas condiciones suelen representarse mediante la letra X.

En un mapa de Karnaugh pueden considerarse como 0 o 1, según convenga para simplificar.

**Aprendizaje:** El mapa de Karnaugh permite pasar de una expresión extensa a un circuito lógico más sencillo.

---

# 🟠 Semana 4: Circuitos aritméticos combinacionales

## 1. Introducción

Los circuitos aritméticos realizan operaciones matemáticas utilizando valores binarios.

Entre los más importantes se encuentran:

- Semisumadores.
- Sumadores completos.
- Sumadores de varios bits.
- Restadores binarios.
- Comparadores digitales.

## 2. Semisumador

Un semisumador recibe dos bits y produce dos resultados:

- S: resultado de la suma.
- Cout: acarreo de salida.

Expresiones:

`S = A XOR B`

`Cout = A · B`

### Tabla de funcionamiento

| A | B | S | Cout |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

## 3. Sumador completo

Un sumador completo incorpora un tercer bit llamado acarreo de entrada (Cin).

Su funcionamiento se expresa mediante:

`S = A XOR B XOR Cin`

`Cout = AB + ACin + BCin`

Ejemplo:

A = 1

B = 0

Cin = 1

Resultado:

`1 + 0 + 1 = 10 (binario)`

Por tanto:

- S = 0
- Cout = 1

## 4. Sumadores de varios bits

Para sumar números de mayor tamaño se conectan varios sumadores completos.

Una arquitectura común es el sumador de acarreo en cascada.

El acarreo de cada etapa pasa a la siguiente.

### Ejemplo con cuatro bits

```text
    0110
  + 0101
  ------
    1011
```

Interpretación decimal:

6 + 5 = 11

## 5. Resta utilizando complemento a dos

La resta binaria se puede convertir en una suma.

La regla utilizada es:

`A - B = A + complemento_a_dos(B)`

### Ejemplo: 9 - 4

Representación de 8 bits:

```text
9 = 00001001
4 = 00000100
```

Complemento a dos de 4:

```text
11111011
+      1
--------
11111100
```

Realizamos la suma:

```text
  00001001
+ 11111100
----------
1 00000101
```

Descartando el acarreo final:

`00000101 = 5`

Por tanto:

**9 - 4 = 5**

## 6. Desbordamiento u overflow

El overflow sucede cuando un resultado con signo supera el rango que puede representar un número determinado de bits.

Por ejemplo, con 4 bits en complemento a dos, los valores permitidos van desde -8 hasta +7.

Si sumamos:

`6 + 3 = 9`

El valor 9 no puede representarse como entero positivo con signo utilizando únicamente 4 bits.

Por tanto, se produce overflow.

## 7. Comparadores binarios

Los comparadores permiten determinar la relación entre dos números.

Sus salidas representan:

| Condición | Significado |
|---|---|
| A > B | A es mayor |
| A = B | Son iguales |
| A < B | A es menor |

### Aplicación

En un sistema de control digital, un comparador puede verificar si un valor supera un límite establecido.

**Aprendizaje:** Los circuitos aritméticos constituyen la base de las operaciones matemáticas que realizan los procesadores.

---

# 🔧 Aplicación integradora: Control de acceso digital

## Descripción del problema

Se desea implementar un sistema sencillo de autorización para el ingreso a un laboratorio.

El acceso será permitido cuando:

- La tarjeta de identificación sea válida.
- Además, se introduzca una clave correcta o exista una autorización del administrador.

## Variables

| Variable | Descripción |
|---|---|
| T | Tarjeta válida |
| C | Clave correcta |
| M | Permiso del administrador |
| F | Acceso autorizado |

## Expresión lógica

`F = T(C + M)`

### Tabla de verdad

| T | C | M | F |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 1 |

## Propuesta de implementación

El circuito se puede construir utilizando:

1. Una compuerta OR que combine C y M.
2. Una compuerta AND que combine T con la salida anterior.
3. Un LED que represente la autorización de acceso.

### Funcionamiento esperado

Cuando la tarjeta no es válida, el acceso permanece bloqueado.

Si la tarjeta es válida, el ingreso dependerá de una clave correcta o del permiso del administrador.

Este ejercicio demuestra cómo los principios del álgebra booleana pueden utilizarse para resolver problemas cotidianos.

---

# 📝 Reflexión sobre la Unidad 1

Durante esta unidad comprendí que los circuitos digitales no consisten únicamente en conectar componentes, sino en analizar el comportamiento que debe tener un sistema.

Las tablas de verdad permiten comprobar todas las combinaciones de entrada, mientras que el álgebra de Boole y los mapas de Karnaugh ayudan a simplificar los circuitos.

También identifiqué la importancia de los sumadores y comparadores, ya que permiten realizar operaciones esenciales dentro de los equipos informáticos.

# ✅ Conclusiones

1. El sistema binario permite representar números e información mediante señales digitales.

2. Las compuertas lógicas son los componentes básicos para construir circuitos combinacionales.

3. El álgebra de Boole y los mapas de Karnaugh ayudan a reducir expresiones lógicas sin modificar su funcionamiento.

4. Las compuertas NAND y NOR permiten implementar diferentes funciones utilizando un mismo tipo de compuerta.

5. Los circuitos aritméticos permiten realizar sumas, restas y comparaciones dentro de sistemas digitales.

6. La aplicación de estos conocimientos facilita el análisis y diseño de soluciones digitales para problemas reales.

---

**Universidad Nacional de Loja - Carrera de Computación**

**Diseño de Circuitos | Unidad 1 | 2026**

