A veces, es necesario utilizar una variable que no se debe modificar durante la ejecución del programa. Estas variables se conocen como variables `val` en Kotlin, donde se declaran con la palabra clave `val`. La diferencia entre una variable `var` y una variable `val`es que no podemos modificar el valor de una variable `val`una vez asignado.

# Variables `val`
# Variables `val`

El siguiente código introduce dos variables val: `pi`, que representa una constante matemática conocida, y `helloMsg`, que representa una cadena de texto.
````kotlin
val pi = 3.1415
val helloMsg = "Hello"

println(pi)       // 3.1415
println(helloMsg) // Hello
````
Ambas variables no se pueden modificar, pero sí se puede acceder a ellas tantas veces como necesitemos.

El compilador producirá un error si intentamos modificar el valor de una variable val, por lo que un intento de compilar el código a continuación dará como resultado un error.
````kotlin
val pi = 3.1415
pi = 3.1416 // error line
````
Si se utiliza una variable `val` antes de asignarle un valor, el compilador también producirá un error:
````kotlin
val boolFalse: Boolean
println(boolFalse) // error line
````
Con el código anterior, obtendrá el error `Variable 'boolFalse' must be initialized`. Para solucionarlo, asigne un valor antes de acceder a la variable:
````kotlin
val boolFalse: Boolean // not initialized
boolFalse = false      // initialized
println(boolFalse)     // no errors here
````
Tenga en cuenta que el valor de una variable `val` se puede reasignar a una variable `var` sin ninguna restricción y el valor de una variable regular se puede cambiar tantas veces como sea necesario:
````kotlin
val count = 10
var cnt = count
cnt = 20 // no errors here, cnt is not a constant
````
# Variables `val` y mutabilidad
Es importante tener en cuenta que `val` no es sinónimo de inmutable . En el siguiente ejemplo, utilizaremos una `MutableList`, que es un conjunto ordenado de elementos del mismo tipo. Si quieres avanzar y aprender más sobre `MutableList`, puedes aprender un tema sobre `MutableList`, pero no es una necesidad en este momento.
````kotlin
// list creation
val myMutableList = mutableListOf(1, 2, 3, 4, 5)
// trying to update the list
myMutableList = mutableListOf(1, 2, 3, 4, 5, 6) // error line
````
La segunda línea no se compilará, ya que estamos intentando reasignar una variable `val`. Sin embargo, hay un punto esencial que recordar.

Siempre es posible cambiar el estado interno de una variable `val`: si bien está prohibido reasignar la variable, su contenido se puede modificar de otras maneras.

Entonces, el siguiente código es correcto:
````kotlin
// list creation
val myMutableList = mutableListOf(1, 2, 3, 4, 5)
// adding a new element
myMutableList.add(6)   // it works
// printing the list
println(myMutableList) // [1, 2, 3, 4, 5, 6]
````
Como puedes ver, este código cambió el estado interno de `myMutableList` agregando otro número entero. Cuando invocamos la función `add()`, no cambiamos la variable en sí, sino la lista que representa.

Si está familiarizado con el lenguaje de programación Java, puede que le resulte más fácil pensar en las variables val de Kotlin como variables `final` de Java. Son bastante similares: ambas prohíben reasignar un valor a la variable, pero permiten cambiar el estado interno del objeto.

# Variables constantes
En Kotlin, también hay un modificador `const` que se utiliza antes de la palabra clave `val` para declarar una constante en tiempo de compilación . El valor de una variable `const` se conoce en tiempo de compilación y no se modificará en tiempo de ejecución:
````kotlin
const val MY_STRING = "This is a constant string"
````
El siguiente código le dará un error, ya que el valor es desconocido antes de la ejecución del programa y no es una constante:
````kotlin
const val MY_STRING = readln() // not a constant String!!!
````
Existen algunas restricciones sobre cuándo cse puede aplicar el modificador `const`. En primer lugar, solo se puede utilizar con una variable `String` o de tipo primitivo :
````kotlin
const val CONST_INT = 127
const val CONST_DOUBLE = 3.14
const val CONST_CHAR = 'c'
const val CONST_STRING = "I am constant"
const val CONST_ARRAY = arrayOf(1, 2, 3) // error: only primitives and strings are allowed
````

Además, las variables const deben declararse en el nivel superior, fuera de cualquier función:
````kotlin
const val MY_INT_1 = 1024 // correct line

fun main() {
    const val MY_INT_2 = 2048 // error: Modifier 'const' is not applicable to 'local variable'
}
````
# Cuándo utilizar variables `val`
Esperamos que ahora entiendas cómo funciona la palabra clave `val` para las variables. Es hora de saber cuándo usarla.

Una buena práctica es utilizar variables `val`por defecto. Luego, cuando parezca necesario para el código, cambiarlas por variables `var`:
````kotlin
var a = 1024
val b = 256
val c = 128
a += b * c
````
Este enfoque permite escribir programas con el mínimo número de variables mutables , lo que genera menos errores.

# Convenciones de nombres
Al declarar variables en Kotlin, la mejor práctica es seguir las convenciones de nomenclatura de Kotlin para garantizar que su código sea fácilmente legible y mantenible.

- Para las variables `val`, utilice el formato camelCase . Comience con una letra minúscula y escriba en mayúscula la primera letra de cada palabra subsiguiente. A continuación, se muestran algunos ejemplos:
````kotlin
val numberOfWheels: Int

val isConnectionAvailable: Boolean

val userFirstName: String
````
- Las variables `const` son constantes de tiempo de compilación. Dado que representan valores estáticos e inmutables, sus nombres deben estar en mayúsculas, con guiones bajos que separen las palabras. Esta convención hace que sean fácilmente distinguibles como constantes dentro del código. Así es como se deben nombrar las variables `const`:
````kotlin
const val MAX_USER_COUNT = 50

const val COMPANY_NAME = "TechCorp"

const val VERSION_CODE = 3
````
# Conclusión
En Kotlin, las variables constantes se declaran con la palabra clave `val`.

Puede tratar las variables `val` como variables normales, excepto por la reasignación de valores.

La palabra clave `val` prohíbe cambiar el valor de la variable, pero puede cambiar el estado interno de lo que representa la variable.

Para las constantes de nivel superior en tiempo de compilación, puede utilizar el modificador `const`.

Utilizar variables `val` siempre que sea posible es una buena práctica que te permitirá evitar errores.