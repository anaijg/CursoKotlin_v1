# ¿Qué es una variable?
Una variable es un almacenamiento de un valor, que puede ser una cadena, un número u otra cosa. Cada variable tiene un nombre (o un identificador ) para distinguirla de otras variables. Puedes acceder a un valor por el nombre de la variable.

Las variables son uno de los elementos más utilizados en los programas, por lo tanto, es importante entender cómo utilizarlas.

# Declarando variables
Antes de poder empezar a utilizar una variable, debes declararla. Para declarar una variable, Kotlin proporciona dos palabras clave :

- **`val`** (para valor) declara una variable de solo lectura (solo un value nombrado), que no se puede cambiar después de haber sido inicializada, por lo que se puede asignar un valor una vez (en realidad esto no es del todo cierto, discutiremos este tema con más detalle más adelante);

- **`var`** (para variable) declara una variable mutable, que puede modificarse (tantas veces como sea necesario).

- **`const`** Se utiliza para variables (con val) que se conocen en tiempo de compilación .


Tanto `val` como `var` son palabras clave que proporcionan una variable!

Cuando declaras una variable, debes agregar su nombre después de una de estas dos palabras clave. Ten cuidado: el nombre de una variable no puede comenzar con un dígito. Por lo general, comienza con una letra. Debes elegir nombres de variables que sean significativos y legibles para que tu código sea fácil de entender.

Para asignar un valor determinado a una variable, debemos utilizar el operador de asignación `=`.

Declaremos una variable inmutable llamada `language` e inicialicémosla con la cadena "Kotlin".
````kotlin
val language = "Kotlin"
````
Ahora podemos acceder a esta cadena por el nombre de la variable. ¡Vamos a imprimirla!

````kotlin
println(language) // prints "Kotlin" without quotes
````
Esta variable no se puede modificar después de haber sido inicializada porque fue declarada como val.


Los nombres distinguen entre mayúsculas y minúsculas: `language` no es lo mismo que `Language`.


Ahora, declaremos una variable mutable llamada `dayOfWeek` e imprimamos su valor antes y después de cambiarla.
````kotlin
var dayOfWeek = "Monday"
println(dayOfWeek) // prints Monday

dayOfWeek = "Tuesday"
println(dayOfWeek) // prints Tuesday
````
En el ejemplo anterior, declaramos una variable con el nombre `dayOfWeeky` y la inicializamos con el valor "Monday". Luego, accedimos al valor por el nombre de la variable y lo imprimimos. Después de eso, cambiamos el valor de la variable a "Tuesday" e imprimimos este nuevo valor.

No es necesario volver a declarar una variable para cambiar su valor. Solo hay que asignarle un nuevo valor mediante el operador `=`.


También es posible declarar e inicializar una variable con el valor de otra variable:
````kotlin
val cost = 3

val costOfCoffee = cost

println(costOfCoffee) // prints 3
````
# Almacenamiento de diferentes tipos de valores
Ya hemos mencionado que las variables pueden almacenar diferentes tipos de valores: cadenas, números, caracteres y otros tipos de datos, que encontraremos más adelante.

Declaremos tres variables inmutables para almacenar un número, una cadena y un carácter y luego imprimamos sus valores.
````kotlin
val ten = 10
val greeting = "Hello"
val firstLetter = 'A'

println(ten) // prints 10
println(greeting) // prints Hello
println(firstLetter) // prints A
````
Sin embargo , existe una restricción para las variables mutables (las declaradas con la palabra clave `var`). Al reasignar sus valores, solo se pueden usar nuevos valores del mismo tipo que el inicial. Por lo tanto, el fragmento de código que se muestra a continuación no es correcto:
````kotlin
var number = 10
number = 11 // ok
number = "twelve" // an error here!
````
¡Por favor recuerde esta restricción!

# Conclusión

Ahora ya sabes que hay dos palabras clave que se usan para declarar variables. En realidad, en muchos casos, es mejor usar variables inmutables (aquellas declaradas con la palabra clave `val`). Antes de usar `var`, debes asegurarte de que `val` no sea adecuado en ese caso. Si realmente no lo es, usa var. Sin embargo, ten en cuenta que cuantas más variables mutables tengas en tu código, más difícil será leerlo y comprenderlo. Recuerda, las variables inmutables ayudan a escribir código más legible. Así que, por favor, ¡usa `val` siempre que sea posible! Puedes reemplazarla fácilmente por `var` cuando sea absolutamente necesario.