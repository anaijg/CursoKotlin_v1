A veces, necesitas poner los valores de las variables en un texto. Afortunadamente, Kotlin puede ayudarte con eso usando plantillas de cadenas . En este tema, analizaremos su propósito.

Supongamos que necesitamos mostrar un mensaje sobre la temperatura de hoy en grados Celsius:

The temperature in ... is ... degrees Celsius.

En lugar de eso, ...necesitamos mostrar ciertos valores.

Si tenemos dos variables cityy temp, podemos construir la cadena resultante con concatenaciones :

val city = "Paris"
val temp = "24"

println("The temperature in " + city + " is " + temp + " degrees Celsius.")

Es una solución sencilla, pero ¿es perfecta? No, es bastante complicada.

Kotlin ofrece una forma más cómoda de hacer lo mismo utilizando plantillas de cadenas. ¿Cómo funcionan? Para agregar un valor de variable a una cadena, escriba el signo de dólar $antes del nombre de una variable:

val city = "Paris"
val temp = "24"

println("The temperature in $city is $temp degrees Celsius.")

El código se vuelve más legible. Ambos fragmentos de código imprimen el mismo mensaje:

The temperature in Paris is 24 degrees Celsius.

Si no queremos imprimir una cadena, podemos crear una variable:

val value = "55"
val currency = "dollars"
val price = "$value $currency" // "55 dollars"

Recomendamos utilizar plantillas de cadenas para crear cadenas con valores variables. Intente utilizarlas en lugar de la concatenación de cadenas.

Plantillas para expresiones
Puede utilizar plantillas de cadena para colocar el resultado de una expresión arbitraria en una cadena. Para ello, incluya la expresión completa entre llaves {...}después del signo de dólar $. Por ejemplo:

val language = "Kotlin"
println("$language has ${language.length} letters in the name")

Imprime:

Kotlin has 6 letters in the name

Aquí {language.length}hay una expresión que se evaluará. Si omite las llaves, el resultado será diferente:

Kotlin has Kotlin.length letters in the name

Por lo tanto, utilice siempre llaves para las expresiones en las plantillas de cadenas para evitar estos errores. No las agregue si desea generar solo un valor variable, aunque funcione.

Modismo
Los modismos son plantillas para un código claro y legible. Estos patrones aclaran el código para otras personas, por lo que es una buena idea usarlos. Todos los modismos están avalados por la comunidad, por lo que su uso te acercará al código genuino de estilo Kotlin. Puedes encontrar una lista exhaustiva de modismos en la documentación de Kotlin .

El modismo que veremos es la interpolación de cadenas :

val language = "Kotlin"
println("Have a nice $language!")        // nice code
println("Have a nice " + language + "!") // bad practice

Conclusión
¿Qué es lo que hay que recordar de este tema? Hay dos puntos principales:

Utilice plantillas de cadena para insertar valores de variables en una cadena: "this string has $value".

Si desea obtener una expresión arbitraria, utilice llaves: "The length is ${str.length}".

