En nuestra vida, siempre estamos rodeados de objetos: conducimos un coche, vemos la televisión, leemos libros, pagamos plátanos con nuestro teléfono inteligente. En Kotlin, cada vez que trabajamos con variables, trabajamos con objetos. Por ejemplo, un entero 5 y una cadena "love" son objetos. Es conveniente porque los programadores son personas y las personas están acostumbradas a tratar con objetos. En este tema, aprenderemos sobre la estructura interna de los objetos, su estado y comportamiento, y sus características distintivas.

# Estado y comportamiento
Los objetos son estructuras complejas que pueden almacenar datos y hacer algo. ¿Cómo se obtiene un objeto? Bueno, un objeto es una parte de la memoria que almacena algún tipo de información. Las variables y los valores solo apuntan a objetos. Por lo tanto, puedes trabajar con objetos con la ayuda de variables. Un ejemplo simple de un objeto es un `String` que almacena un mensaje. Veámoslo más de cerca.

En primer lugar, un mensaje tiene un **estado**: no solo contiene una secuencia de símbolos, sino también el tamaño de la secuencia, es decir, la longitud del mensaje. En Kotlin, algo que te permite acceder al estado de un objeto se llama **propiedad**. ¡Solo pon un punto y escribe el nombre de la propiedad después del objeto, y obtendrás lo que quieres! Supongamos que tienes una variable `String` simple `msg: val msg = "Hi"`. La propiedad length nos da la longitud de la cadena:
````kotlin
val msg = "Hi"
println(msg.length) // 2
````
En Kotlin, algunas funciones están vinculadas a un tipo específico. Esto hace que el uso de los objetos sea más lógico porque las funciones representan el comportamiento de esos objetos. Estas funciones también se denominan **funciones miembro o métodos** . La sintaxis es similar: solo hay que poner un punto. Por ejemplo, podemos repetir nuestro mensaje utilizando la función miembro **repeat()**:
````kotlin
val msg = "Hi"
println(msg.repeat(3)) // "HiHiHi"
````
Se imprimirá:
````
HiHiHi
````
Como puedes ver, incluso el tipo estándar `String` tiene una estructura interna realmente compleja.

# Copia por referencia
En programación, copiar algo es una operación muy común. La utilizamos =en casi todos los casos. Veamos cómo funciona en Kotlin utilizando una analogía sencilla con una cuenta bancaria.

Es posible que tengas varias tarjetas conectadas a una misma cuenta. Si compras algo con una de estas tarjetas, seguirás gastando dinero de esa misma cuenta bancaria, aunque las tarjetas sean diferentes.

En Kotlin se aplican reglas similares. Si creas una variable y le asignas un objeto, otra variable también puede apuntar al mismo objeto. Supongamos que escribiste mensajes de texto como este:
````kotlin
val msg1 = "Hi"
val msg2 = msg1
````
Habrá dos valores que apuntarán a un único objeto "Hi": dos variables `msg1` y `msg2` que apuntan a un solo objeto

En otras palabras, el signo `=` no copia el objeto en sí, sólo copia una referencia a él.

# Mutabilidad
¿Qué sucede si modificas un objeto asignado a múltiples variables modificando el valor de una de ellas? Depende del tipo de objeto. Un objeto puede ser **mutable** o **inmutable**.

Ya sabes que `Int`, `String`, `Float`, y `Double` en Kotlin son objetos. Pero hay un matiz. Por ejemplo, las variables `Int`o  `String` se comportan igual que los tipos primitivos de datos en otros lenguajes de programación, pero al mismo tiempo son objetos, es decir, objetos inmutables. Veamos cómo funciona:
````kotlin
var a: Int = 100
val anotherA: Int = a
println(a == anotherA)  // true
println(a === anotherA) // true
a = 200
println(a == anotherA)  // false
println(a === anotherA) // false
````
Como puedes ver, cuando cambiamos el valor de la variable `a = 200`, no cambiamos su objeto: a la variable a se le asigna una nueva referencia al objeto con el valor 200.

Veamos un ejemplo, pero ahora con el tipo de datos `Double`: 
````kotlin
var d1: Double = 1.5
val d2 = d1
println(d1 === d2) // true
d1 += 1            // d1 is 2.5 now
println(d1 === d2) // false
````
Si el objeto es inmutable, no se puede modificar, pero se puede utilizar otro objeto y asignar este nuevo objeto a la misma variable. Cuando se reasigna la variable, apuntará a un nuevo objeto y las demás variables seguirán apuntando al objeto anterior. Los tipos básicos, como cadenas o números, son inmutables, por lo que es seguro copiarlos por referencia.

# Conclusión
Resumamos los puntos principales del tema:

- Los objetos son estructuras complicadas con estados, propiedades y funciones miembro.

- Un objeto es una parte de la memoria que almacena algo.

- Las variables sólo apuntan a objetos.

- Los objetos pueden ser mutables o inmutables.

- La única forma de cambiar algo en una variable vinculada a un objeto inmutable es reasignándolo.

- Puede copiar libremente objetos inmutables como tipos básicos.

