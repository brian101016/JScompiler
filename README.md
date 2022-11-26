# JScompiler

Actualmente dispone de tres funcionalidades clave:

## `find`
El comando `find` te permite realizar una búsqueda como analizador léxico. <br/>
Para utilizarlo, simplemente escriba `find` y posteriormente ingrese el texto a analizar. <br/>
Para finalizar el proceso, escriba `exit`.

### Flujo de información
El analizador léxico te permite identificar el uso correcto de
- Paréntesis ( )
- Llaves { }
- Corchetes [ ] <br/>
Ya sea cuando se omite una apertura o cuando hace falta algún cierre del mismo.

### Tokens
Actualmente, el comando `find` puede identificar las 32 palabras reservadas (a excepción del comando `exit` que inmediatamente termina el proceso):
- `void`
- `bool`
- `int`
- `float`
- `string`
- `array`
- `if`
- `else`
- `while`
- `do`
- `for`
- `break`
- `continue`
- `return`
- `class`
- `new`
- `constructor`
- `const`
- `null`
- `object`
- `struct`
- `queue`
- `foreach`
- `iterator`
- `switch`
- `case`
- `default`
- `goto`
- `import`
- `export`
- `find`
- `exit`

### Información mostrada
Al identificar uno o más tokens, el analizador léxico mantendrá un registro de ello en la **consola de errores** (parte inferior),
donde contará las veces que se ha ingresado dicho token en concreto. También mostrará algún error que exista con respecto al flujo de información.

## Variables
Para declarar una variable ingrese `int` y posterior a esto el nombre de la variable. Dentro de la consola de errores se mostrará información
pertinente a la declaración de la o las variables (así como cualquier error que pueda surgir). <br/> <br/>

Para declarar múltiples variables dentro de la misma sentencia, se puede hacer uso de comas `,` para separar las declaraciones.

## Expresiones
El compilador permite el uso de expresiones matemáticas y la resolución de éstas. Una expresión puede ser `3 + 1` (que arroja 4), o también puede ser
`a = (8 * 2) + 4` (que arroja 20). <br/> <br/>

Los operadores válidos (y sus nombres) para las expresiones son los siguientes:
- `+` SUMA
- `++` AUMENTAR EN 1*
- `-` RESTA
- `--` DISMINUIR EN 1*
- `*` MULTIPLICAR
- `/` DIVIDIR (*NOTA: la división entre 0 regresa 0*)
- `%` RESIDUO
- `^` EXPONENTE
- `>` MAYOR QUE
- `<` MENOR QUE
- `>=` MAYOR IGUAL
- `<=` MENOR IGUAL
- `==` IGUAL A
- `!=` DESIGUAL A
- `&` AND BINARIO
- `|` OR BINARIO
- `~` XOR BINARIO
- `&&` AND LÓGICO
- `||` OR LÓGICO
- `~~` XOR LÓGICO <br /> <br/>

**NOTA:** Todos estos operadores pueden ser conjugados con un operador `=` al final,
lo que resulta en la asignación de la variable de cual sea el resultado de la expresión normalmente <br/>
(ej1. `bar = 2`, tenemos que `bar ^= 4` que equivale a `bar = bar ^ 4 = 2 ^ 4 = 16`) <br/>
(ej2. `bar = 1`, tenemos que `bar ~~= 1` que equivale a `bar = bar ~~ 1 = 1 ~~ 1 = false`) <br/> <br/>

**NOTA 2:** Los operadores `++` y `--` únicamente funcionan con variables y regresan el valor modificado de dicha variable:
Ej. `foo = 2`, entonces `foo ++ + 2` arroja 5 y ahora `foo` vale 3.
