# Lectura de datos con readln
En este tema, aprenderá cómo podemos leer la información ingresada por el usuario e interactuar con ella. Muy a menudo, los programas solicitan al usuario información específica. También veremos cómo administrar variables con la función `readln()` y trabajar con diferentes tipos.

## Entrada estándar
La entrada estándar es un flujo de datos que se introduce en el programa. El sistema operativo lo admite. De forma predeterminada, la entrada estándar obtiene los datos del teclado, pero también es posible obtenerlos de un archivo.

No todos los programas necesitan utilizar la entrada estándar, pero aun así, es probable que la utilices con bastante frecuencia. Una forma típica de resolver problemas de programación es la siguiente:

- Leer datos de la entrada estándar;

- Procesar datos para obtener un resultado;

- Envíe el resultado a la salida estándar.

Antes de comenzar a escribir programas que hagan algo útil, necesita comprender cómo leer datos de la entrada estándar.

## Usando `readln`
En Kotlin, para leer datos de la entrada estándar, se puede utilizar la función readln(). Lee la línea completa como una cadena:
```kotlin
val line = readln()
```
La variable línea tiene el tipo String porque la expresión `readln()` devuelve un valor de este tipo.

Si trabaja con versiones anteriores del lenguaje Kotlin, debe utilizar `readLine()!!` en lugar de `readln()`. Estas funciones hacen lo mismo, pero `readln()` es más cortas y preferida, por lo que si trabaja con Kotlin 1.6 o una versión posterior, utilice `readln()`.
```kotlin
val line = readLine()!! // antes de Kotlin 1.6
```
Probablemente estés un poco confundido con los signos de exclamación. Esta construcción garantiza que la entrada al compilador no esté vacía. Hablaremos de esto con más detalle más adelante.

Aquí hay un programa simple que lee una línea de la entrada estándar y la envía a la salida estándar:
```kotlin
fun main() {
    
    val line = readln()
    
    println(line)
    
}
```
A continuación se muestra un ejemplo de datos de entrada válidos:
```
Hello, Kotlin
```
La salida sería la siguiente:
```
Hello, Kotlin
```
Por defecto, para ver la información sobre los datos ingresados es necesario presionar _Enter_.

Ahora, veamos cómo puedes leer diferentes tipos de datos usando `readln()`.

## `toInt()` y `toLong()`
A veces necesitamos obtener datos numéricos del usuario. Por ejemplo, supongamos que necesitamos obtener información sobre la edad del usuario o el año de graduación. Para convertir la entrada en un número entero, utilice `toInt()`:
```kotlin
println("Introduzca un número: ")

val number = readln().toInt()

print("Ha introducido el número: ")

print(number)
```
A continuación se muestra un ejemplo de datos de entrada válidos:

`56`

La salida es:
```
Introduzca un número:
56
Ha introducido el número: 56
```
En caso de que necesitemos procesar un número mayor, por ejemplo, el costo de un yate grande y lujoso, utilizamos la función `toLong()`:
```kotlin
println("¿Cuánto cuesta tu yate?")

val cost = readln().toLong()

print("Ha introducido: ")

print(cost)
```
La salida es:
```
¿Cuánto cuesta tu yate?
10000000000
Has introducido: 10000000000
```

## `toDouble()` y `toBoolean()`
¿Qué sucede si necesitamos obtener valores más precisos? Por ejemplo, supongamos que necesitamos saber el precio exacto de un litro de gasolina. En este caso, no podemos utilizar `toInt()` o `toLong()` ya que probablemente no dispongamos de un número entero. Para ello, utilice la función `toDouble()`:
````Kotlin
println("Introduce un número decimal:")

val number = readln().toDouble()

println("Has introducido el número: ")

print(number)
````
La salida es:
````
Introduce un número decimal:
0.5673421
Has introducido el número:
0.5673421
````
La misma lógica funciona para Boolean: use la función `toBoolean()`:
````kotlin
println("La tierra es plana. Escribe true o false:")

val answer = readln().toBoolean()

print("La tierra es plana: ")

print(answer)
````
La salida es:
````
La tierra es plana. Escribe true o false:
false
La tierra es plana: false
````
## Entradas múltiples
¿Es posible recibir y procesar múltiples entradas? La respuesta es sí: todo lo que necesitamos hacer es declarar algunas variables diferentes, todas con el valor de la función `readln()`. Si desea ingresar varios valores y sus tipos de datos son diferentes, entonces debe presionar _Enter_ para separar los diferentes tipos.

Consideremos un ejemplo que ilustra la entrada y salida de múltiples valores:
````kotlin
val a = readln()

val b = readln().toInt()

val c = readln()

print(a)

print(" ")

print(b)

print(" ")

print(c)
````
A continuación se muestra un ejemplo de valores válidos `String` e `Int` de entrada:
''''
You earned
100
points!
''''
La salida es:
````
You earned 100 points!
````
Como puedes ver, obtener múltiples valores de distintos tipos de datos no es difícil. Solo necesitas declarar varias variables, asignarles la función `readln()` deseada y mostrarlas correctamente en la consola.

## Lectura de múltiples valores en una línea
Si necesita leer dos valores en una línea, puede utilizar esta construcción:
````kotlin
val (a, b) = readln().split(" ")

println(a)

println(b)
````
A continuación se muestra un ejemplo de datos de entrada:
````
Hello, Kotlin
````
La salida sería la siguiente:
````
Hello,
Kotlin
````
Esta construcción divide la cadena de entrada en espacios y almacena las palabras en las variables a y b. Hablaremos de esto con más detalle más adelante.

De la misma manera, puedes leer hasta cuatro valores por línea:
````kotlin
val (a, b, c, d) = readln().split(" ")

println(a)
println(b)
println(c)
println(d)
````
A continuación se muestra un ejemplo de datos de entrada:
````
Have a nice Kotlin
````
La salida sería la siguiente:
````
Have
a
nice
Kotlin
````
## Conclusión
Como puede ver, recibir una entrada es muy sencillo. Todo lo que necesitamos es declarar una variable con el valor de la función `readln(). La función readln() convierte automáticamente la entrada al tipo `String`. Su programa puede manejar entradas de cadena, número y booleano mediante la conversión de tipos. Para convertir, utilice las funciones `toInt()`, `toLong()`, `toDouble()` y `toBoolean()`. También puede ingresar y generar múltiples valores del mismo tipo o de tipos diferentes.