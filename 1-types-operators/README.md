# Tipos y operadores

## Tipos de datos
La información que se guardará en memoria necesitará estar relacionada con un Tipo de dato. Más adelante veremos como guardar esta información pero ahora repasaremos los Tipos de datos que hay.
#### Number
Se utilizan para representar números.
Se declaran sin usar ningún tipo de coma (a palo seco).
`1`
`77`
`929`

#### Strings
Se utilizan para representar texto.
Se escriben encerrandolo en comillas

`'Hello world'`

`"Ramón García"`

`"Esto no es un String'`

`Esto tampoco es un String`

#### Booleanos
Representar un valor verdadero o falso

`false`

`true`

*No hay más posibles valores!*

### <span style="color:blue">Preguntas Tipos de datos</span>
Qué tipo de dato es:

`'true'`

`0`

`Como estás`
## Variables
Cuando estamos programando, es importante almacenar la información que estamos tratando.
Si pensamos en Facebook, nos interesa guardar el nombre del usuario, el número de notificaciones pendientes o 
el estado de estar ausente o no.

Supongamos que queremos almacenar el numero de usuario que nos entran en un formulario de login.
Esta información será almacenada en una especie de contenedor que llamaremos vinculaciones (También conocidas como variables aunque no es correcto).

Crear un nuevo ligamiento (contenedor) recibe el nombre de declaración.
Una delcaración de ligamiento tendrá el siguiente formato:

`let {nombre_contenedor} = {valor_contenedor}`

Con el ejemplo de guardar el usuario, quedará tal que así:

`let nombreUsuario = "Leo Messi"`

Podemos printar el valor de este contenedor:

`console.log(nombreUsuario)` -> `"Leo Messi"`

El valor puede ser reescrito una vez declarado `nombreUsuario`.

`nombreUsuario = "El bicho"` 

`console.log(nombreUsuario)` -> `"El bicho"`


También existen otras vinculaciones como

`var edad = 18` que se comporta de manera muy similar a let.

`const MENSAJE = "No pasar"` donde el valor no podrá ser reescrito.

Si probamos a reescribir el valor de un const:
`MENSAJE = "Si pasar"` -> `ERROR`

### <span style="color:blue">Preguntas Variables</span>

¿Darán error estas declaraciones?

`dni = '41630322T'`

`let miEdad = 'Roberto'`

`const MAIL = 'lewandowksi@gmail.com'`

## Operadores
Los **operadores aritméticos** nos permitirán operar los diferentes tipos de datos.
***Ejemplos:***

`console.log(3+3)` -> `6`

`console.log(4*4)` -> `16`

`console.log(11%2)` -> `1`   *(Residuo de dividir 11/2)*

También se podrán operar Strings:

`console.log("Juan" + "Alberto")` -> `"JuanAlberto"`

`console.log("Ramón " + "Garcia")` -> `"Ramon Garcia"`

`console.log("a" + " " + "b" + " " + "c")` -> `"a b c"`




Sabemos que un valor es booleano si es true o false pero para obtener un valor booleano necesitaremos hacer uso de los operadores lógicos.

| Operador | Descripción |
| --- | --- |
| `==` | Compara dos valores y devuelve `true` si son iguales. |
| `!=` | Compara dos valores y devuelve `true` si son diferentes. |
| `>` | Compara dos valores y devuelve `true` si el primero es mayor que el segundo. |
| `<` | Compara dos valores y devuelve `true` si el primero es menor que el segundo. |
| `>=` | Compara dos valores y devuelve `true` si el primero es mayor o igual que el segundo. |
| `<=` | Compara dos valores y devuelve `true` si el primero es menor o igual que el segundo. |

***Ejemplos:***

`console.log(10 > 0)` -> `true`
`console.log(100 == 200)` -> `false`
`console.log(7 >= 7)` -> `true`
`console.log(2 != 2)` -> `false`

| Operador | Descripción |
| --- | --- |
| `&&` | Devuelve `true` si ambas condiciones son verdaderas. |
|  `||`  | Devuelve `true` si al menos una de las condiciones es verdadera. |
| `!` | Invierte el valor de la condición. Si es verdadera, devuelve `false`; si es falsa, devuelve `true`. |

***Ejemplos:***

`console.log(1+1 == 2 && 7*2 != 15)` -> `true`

`let primeraCondicion = 11 == 11`

`let segundaCondicion = 1 > 3`

`console.log( primeraCondicion && segundaCondicion )` -> `false`

`console.log( primeraCondicion || segundaCondicion )` -> `true`

`console.log( primeraCondicion && !segundaCondicion )` -> `true`

`console.log( !(!primeraCondicion && !segundaCondicion) )` -> `true`

### <span style="color:blue">Preguntas Operadores</span>

`console.log( 1 == 1 )`

`console.log( true || false )`

`console.log( false || false )`

`console.log( !(24 * 2 == 48) )`