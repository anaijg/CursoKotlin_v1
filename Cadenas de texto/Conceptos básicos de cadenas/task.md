Como ya sabes, Kotlin tiene muchos tipos de datos como String, Int, y Double. En este tema, nos centraremos en el Stringtipo. Este es un tipo muy útil, ya que incluso un programa sencillo del tipo "¡Hola mundo!" utiliza cadenas. Una cadena es una secuencia de cero o más caracteres entre comillas dobles, por ejemplo, "John", "". Seguramente utilizarás cadenas de forma habitual en tus proyectos futuros. En este tema, veremos algunos conceptos básicos importantes sobre cómo trabajar con cadenas.

La longitud de una cuerda
A menudo, necesitará obtener la longitud de un String. La longitud de la cadena se determina por la cantidad de caracteres que se incluyen entre comillas dobles. Para ello, simplemente utilice .lengthque da un valor del Inttipo:

val language = "Kotlin"
println(language.length) // 6

val empty = ""
println(empty.length) // 0

Concatenación de cadenas
Otra operación común Stringes la concatenación . Se utiliza para construir una cadena a partir de otras cadenas.

Se pueden concatenar dos cadenas con +:

val str1 = "ab"
val str2 = "cde"
val result = str1 + str2 // "abcde"

Cuando concatenamos dos cadenas, se crea una nueva cadena.

val one = "1"
val two = "2"
val twelve = one + two
println(one)      // 1, no changes
println(two)      // 2, no changes
println(twelve)   // 12

Puedes concatenar varias cadenas en la misma expresión:

val firstName = "John"
val lastName = "Smith"
val fullName = firstName + " " + lastName

Presta atención ,str1 + str2 no es lo mismo str2 + str1porque la concatenación no es una operación conmutativa, a diferencia de la suma.

Añadiendo valores a cadenas
También +funciona para agregar valores de distintos tipos a un String. El valor se convierte automáticamente en a Stringy luego se concatena al destino String:

val stringPlusBoolean = "abc" + 10 + true
println(stringPlusBoolean) // abc10true

val code = "123" + 456 + "789"
println(code) // 123456789

Una expresión debe comenzar con un String.

Observa el ejemplo que aparece a continuación. No funcionaría porque el primer operando es un número:

val errorString = 10 + "abc" // an error here!

Consideremos una situación diferente:

val stringAndNumbers = "abc" + 11 + 22
println(stringAndNumbers) // abc1122

¿Por qué funcionó? Primero, agrega 11a la cadena "abc"y luego agrega 22a la cadena "abc11".

Puedes concatenar un carácter con a Stringpara obtener un nuevo String:

val charPlusString = 'a' + "bc"
println(charPlusString) // abc
val stringPlusChar = "de" + 'f'
println(stringPlusChar) // def

Además, puedes agregar cualquier valor al resultado, porque los caracteres más una cadena te dan un resultado String:

val charPlusStringPlusInt = 'a' + "bc" + 123
println(charPlusStringPlusInt) // abc123

Hablaremos sobre cómo trabajar con caracteres más adelante, pero por ahora, solo recuerda que puedes concatenar caracteres y cadenas para obtener un Stringvalor. Si te interesa saber cómo funcionan los caracteres con números enteros, consulta este tema .

Repitiendo la cadena
Si necesita repetir una cadena dos o más veces, entonces mantenga sus bucles: Kotlin proporciona la repeatfunción:

print("Hello".repeat(4)) // HelloHelloHelloHello

Ahora, imagina que tu amigo desarrollador senior te dio un secreto sobre cómo convertirte en el mejor programador:

Por hacer: comer, dormir, codificar, repetir

![img.png](img.png)

Intentemos transformar este trozo de papel en un fragmento de código que imprima su agenda para todos los días de la semana:

println("Eat. Sleep. Code.\n".repeat(7)) // \n gives you a line feed (new line)

Y aquí tenéis vuestro calendario semanal:

Eat. Sleep. Code.
Eat. Sleep. Code.
Eat. Sleep. Code.
Eat. Sleep. Code.
Eat. Sleep. Code.
Eat. Sleep. Code.
Eat. Sleep. Code.

¡No hay tiempo para posponerlo!

Cuerda cruda
A veces, necesitas algunos símbolos especiales, como tabulaciones o comillas, en tu cadena. Puedes hacerlo con la ayuda de secuencias de escape . Por ejemplo:

// prints 'H' is the first letter of "Hello world!" string.
println("\'H\' is the first letter of \"Hello world!\" string.")

Parece un poco pesado. Si necesitas escribir un texto bastante largo con saltos de línea y caracteres especiales, puede resultar difícil de leer.

Para estos casos, puedes usar una cadena sin formato . Una cadena sin formato puede contener nuevas líneas y cualquier otro carácter. Solo tienes que encerrar el texto entre comillas triples ( """):

val largeString = """
This is the house that Jack built.

    This is the malt that lay in the house that Jack built.
       
    This is the rat that ate the malt
    That lay in the house that Jack built.
       
    This is the cat
    That killed the rat that ate the malt
    That lay in the house that Jack built.
""".trimIndent() // removes the first and the last lines and trims indents
print(largeString)

Este texto imprime:

This is the house that Jack built.

This is the malt that lay in the house that Jack built.

This is the rat that ate the malt
That lay in the house that Jack built.

This is the cat
That killed the rat that ate the malt
That lay in the house that Jack built.

Como puede ver, también usamos la función .trimIndent(). Corta todas las líneas de la sangría mínima común y elimina la primera y la última línea si están vacías. Por ejemplo:

val unevenString = """
123
456
789""".trimIndent()
print(unevenString)
println()

val rawString = """123
456
789
""".trimIndent()
print(rawString )

Este código imprime:

123
456
789

123
456
789

Conclusión
¡Ahora ya conoces las Stringoperaciones más básicas! Estas funciones son bastante simples pero absolutamente cruciales en la programación. En realidad, hay muchas otras Stringoperaciones útiles, pero las conocerás un poco más adelante. ¡Buena suerte con tus tareas!