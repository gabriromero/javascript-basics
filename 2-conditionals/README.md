# Condicionales y flujo de control

## If y el flujo de control
Un programa es como una historia que se lee de arriba a abajo.

```javascript
console.log("Yo voy primero")
let x = "Yo voy segundo"
console.log("Yo voy tercero")
```

Si un programa de 1000 lineas de código devuelve un error en la primera línea, todas las otras lineas no se ejecutarán.

No todos los programas serán como una linea recta de arriba hasta abajo, es posible que queramos hacer varios caminos dependiendo de una situación en cuestión.

A esto le llamaremos <i>ejecución condicional</i> y la palabra clave para usarla será el `if`. Y el esquema será el siguiente:

```javascript
if(condición){
    //Código que se ejecutará solo si la condición es true
}
```

Lo vemos con un ejemplo muy claro:

```javascript
console.log("Siempre se ejecutará")

let condicion = false

if(condicion){
    console.log("No se ejecutará")
}

console.log("También se ejecutará")
```

Ejemplo de <i>login de usuario</i>:

```javascript
let user = "Roberto777"
let password = "secretpw"

if(user == "Roberto777" && password == "secretpw"){
    console.log("Usuario logueado correctamente!")
}

console.log("El usuario no se ha podido loguear...")
```

El ejemplo de <i>login de usuario</i> realmente es correcto?

<br/><br/><br/><br/><br/><br/>

No. Siempre se ejecutará la linea informando que el usuario no se ha podido loguear aun si las credenciales son correctas.

Para solucionarlo, se podria hacer lo siguiente:

```javascript
let user = "Roberto777"
let password = "secretpw"

if(user == "Roberto777" && password == "secretpw"){
    console.log("Usuario logueado correctamente!")
}

if( !(user == "Roberto777" && password == "secretpw") ){
    console.log("El usuario no se ha podido loguear...")
}
```

De esta manera si que el programa se comportará como esperamos.

## Else

Aunque esta implementación hace lo que esperamos, no significa que sea una solución muy sólida.

Vamos a solventar este problema introduciendo una nueva palabra clave, `else`.

`else` se tendrá que usar junto `if` para indicar que hacer con todas esas condiciones que no se están cumpliendo.

Ejemplo claro:

```javascript

let numero = 50

if (numero >= 1000){
    console.log("Es un numero MUY grande")
} 
else{
    console.log("Es un numero pequeño incluso negativo :o")
}

```

Realmente el código de arriba se podría haber hecho sin usar el `else`?

La verdad es que si, pero hacerlo con el else nos ahorarria pensar en una segunda condición que sea diferente a la del primer `if` y hacer del código más legible.

Ejemplo sin usar `else`:
```javascript

let numero = 50

if (numero >= 1000){
    console.log("Es un numero MUY grande")
} 

if (numero < 1000){  // <-- Esta condición nos la ahorramos
    console.log("Es un numero pequeño incluso negativo :o")
}

```

Ahora podemos ver el ejemplo anterior de comprobar credenciales pero usando el `else`:
```javascript
let user = "Roberto777"
let password = "secretpw"

if(user == "Roberto777" && password == "secretpw"){
    console.log("Usuario logueado correctamente!")
}
else{ // <-- No hace falta escribir una condición complementaria
     console.log("El usuario no se ha podido loguear...")
}
```

## Else if
Hasta ahora hemos estado hablando de condiciones booleanas donde el flujo podria ir por un lado (`if`) o por el otro (`else`), pero realmente, podria interesarnos dividir el programa en más de dos caminos?

La respuesta es que si.

Supongamos que una empresa de telefonia nos ofrece un porcentaje de descuento en su tarifa dependiendo de los meses que tengamos de permanencia.

Ejemplo de descuento segun meses de permanencia:
```javascript
let mesesPermanencia = 24

if( mesesPermanencia <= 12 ){
    console.log("0% de descuento. Te aguantas.")
}

if( mesesPermanencia >= 12 &&  mesesPermanencia <= 24 ){
    console.log("5% de descuento. Un buen cliente.")
}

if( mesesPermanencia >= 24 &&  mesesPermanencia <= 36 ){
    console.log("10% de descuento. Nos caes bien!")
}

if( mesesPermanencia > 36 ){
    console.log("15% de descuento. Te queremos!!!")
}

```
En este ejemplo, utilizamos varios `if` para indicar al usuario que tipo de descuento va a recibir.
<br/><br/><br/><br/><br/><br/><br/>
Pero este código, además de ser poco legible, es incorrecto.

¿Que devolveria este código si lo ejecutamos?

La respuesta es la siguiente:

```
5% de descuento. Un buen cliente.
10% de descuento. Nos caes bien!
```

Entonces, el usuario recibe un 5% o un 10% de descuento? Está claro que hay un error.

Esto podría ser arreglado volviendo a hacer la lógica correctamente:

```javascript
let mesesPermanencia = 24

if( mesesPermanencia < 12 ){
    console.log("0% de descuento. Te aguantas.")
}

if( mesesPermanencia >= 12 &&  mesesPermanencia < 24 ){
    console.log("5% de descuento. Un buen cliente.")
}

if( mesesPermanencia >= 24 &&  mesesPermanencia < 36 ){
    console.log("10% de descuento. Nos caes bien!")
}

if( mesesPermanencia >= 36 ){
    console.log("15% de descuento. Te queremos!!!")
}

```

Ahora realmente si que sería correcto.

Para evitar que puedan llegar a ocurrir ese tipo de situaciones y además hacer el código más legible, es recomendado utilizar la palabra clave `else if`, que también irá seguido del if.

En cada `else if` se escribirá una nueva condición.

Es recomendado también acabar con un else para contemplar todos esos casos que nos podriamos haber olvidado.

Vamos a replantear el programa del descuento segun permanencia utilizando `else if`:

```javascript
let mesesPermanencia = 24

if( mesesPermanencia < 12 ){
    console.log("0% de descuento. Te aguantas.")
}
else if( mesesPermanencia >= 12 &&  mesesPermanencia < 24 ){
    console.log("5% de descuento. Un buen cliente.")
}
else if( mesesPermanencia >= 24 &&  mesesPermanencia < 36 ){
    console.log("10% de descuento. Nos caes bien!")
}
else if( mesesPermanencia >= 36 ){
    console.log("15% de descuento. Te queremos!!!")
}
else {
    console.log("Ha ocurrido un error. Te damos un 50% por las molestias.")
}

```

De esta manera nos aseguraremos que una vez una de estas condiciones se cumplan, no haga más comprobaciones denegando que entre por más de una rama.

## Switch

Switch es otra manera de hacer una mezcla de `if` + `else if` + `else` de manera más sofisticada.

Ejemplo de programa que te escoje un tipo Pokémon según color favorito:
```javascript

let colorFavorito = "rojo";

switch (colorFavorito) { // <-- Que valor comparará
  case "rojo":  // <-- Equivalente a if(colorFavorito == "rojo")
    console.log("Tu tipo favorito es fuego");
    break;
  case "verde":
    console.log("Tu tipo favorito es planta");
    break;
  case "azul":
    console.log("Tu tipo favorito es agua");
    break;
  default: // <-- Equivalente a else
    console.log("No tienes ningún tipo favorito :(");
}
```