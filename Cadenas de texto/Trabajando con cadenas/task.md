Las comprobaciones de tipos y las conversiones de tipos son esenciales en cualquier lenguaje de programación. Las comprobaciones de tipos permiten a los desarrolladores verificar si un objeto pertenece a un tipo de datos en particular, mientras que las conversiones de tipos permiten a los programadores convertir un objeto de un tipo a otro. Kotlin, al ser un lenguaje de tipado estático, tiene varias características que hacen que las comprobaciones de tipos y las conversiones de tipos sean fáciles y seguras de usar.

Operadores is y !is
Los operadores isy !isen Kotlin se utilizan para realizar comprobaciones de tipos. Permiten a los desarrolladores comprobar si un objeto pertenece a un tipo de datos en particular. El isoperador devuelve verdadero si un objeto pertenece al tipo especificado y falso si no lo pertenece. Por el contrario, el !isoperador devuelve verdadero si un objeto no pertenece al tipo especificado y falso si lo pertenece.

Por ejemplo:

val obj: Any = "Hello, Kotlin"
if (obj is String) {
println(obj.uppercase())
} else {
println("obj is not a String")
}

En el código anterior, utilizamos el isoperador para comprobar si la objvariable es un String. Si es un String, lo convertimos a mayúsculas y lo imprimimos. De lo contrario, imprimimos un mensaje que indica que objno es un String. Este es un buen ejemplo del isoperador, pero recordemos los modismos de Kotlin, una de las ventajas de este lenguaje de programación. Uno de los modismos que se utilizan a menudo en Kotlin es:

when (x) {
is Foo -> ...
is Bar -> ...
else   -> ...
}

Veamos un ejemplo de cómo podemos utilizar esto:

fun processInput(input: Any) {
when (input) {
is Int -> println("Input is an integer")
is String -> println("Input is a string")
is Double -> println("Input is a double")
else -> println("Unknown input")
}
}

En este ejemplo, la función processInputtoma un argumento de tipo Any, lo que significa que puede aceptar cualquier tipo de objeto. Dentro de la función, usamos whenwith ispara verificar el tipo del objeto de entrada. Dependiendo del tipo, imprimimos un mensaje que indica qué tipo de entrada es. Si el objeto de entrada no es uno de los tipos esperados, imprimimos el mensaje "Entrada desconocida".

Lanzamientos inteligentes
Kotlin también tiene una característica conocida como conversiones inteligentes . Las conversiones inteligentes se utilizan para simplificar el código cuando se trabaja con tipos que aceptan valores NULL . Cuando se comprueba un tipo que acepta valores NULL con el isoperador, Kotlin convierte automáticamente el objeto a un tipo que no acepta valores NULL .

Por ejemplo:

fun printLength(obj: Any) {
if (obj is String) {
println(obj.length)
}
}

En el código anterior, verificamos si la objvariable es a Stringmediante el isoperador . Si es a String, imprimimos su longitud. Dado que Kotlin convierte automáticamente la objvariable a un tipo que no acepta valores nulos, no necesitamos usar ningún operador de conversión de tipo.

Operador de reparto "inseguro"
Kotlin tiene un operador de conversión inseguro, que se representa con la as palabra clave . La aspalabra clave se utiliza para convertir un objeto a un tipo que no acepta valores nulos. Si el objeto no se puede convertir al tipo especificado, el asoperador lanza una ClassCastException.

Por ejemplo:

val obj: Any = "Hello, Kotlin"
val str: String = obj as String // Unsafe cast operator
println(str.uppercase())

En el código anterior, utilizamos el asoperador para convertir la objvariable a String. Si objno es String, el asoperador lanza una ClassCastException.

Operador de conversión "seguro" (que acepta valores nulos)
Kotlin también tiene un operador de conversión seguro, que se representa mediante la as?palabra clave. El as?operador se utiliza para convertir un objeto a un tipo que admita valores nulos. Si el objeto no se puede convertir al tipo especificado, el as?operador devuelve null.

Por ejemplo:

fun main() {
val obj: Any = 123
val str: String? = obj as? String // Safe (nullable) cast operator
if (str != null) {
println(str.uppercase())
}
}

En el código anterior, utilizamos el as?operador para convertir la objvariable a a String. Como objno es a String, el as?operador devuelve null. Por lo tanto, la println instrucción no imprime nada.

Comprobaciones y conversiones de tipos genéricos
En Kotlin, también podemos usar verificaciones de tipos y conversiones con genéricos. Cuando trabajamos con genéricos, es posible que necesitemos verificar si un objeto es una instancia de un parámetro de tipo específico o convertirlo a un parámetro de tipo .

Para comprobar si un objeto es una instancia de un parámetro de tipo específico, podemos utilizar el isoperador con el parámetro de tipo entre corchetes angulares. Por ejemplo:

fun <T> exampleFunction(obj: Any) {
if (obj is T) {
// obj is an instance of type parameter T
} else {
// obj is not an instance of type parameter T
}
}

De manera similar, podemos convertir un objeto a un parámetro de tipo utilizando el asoperador con el parámetro de tipo entre corchetes angulares. Sin embargo, si el objeto no es una instancia del parámetro de tipo, ClassCastExceptionse lanzará . Para evitar esto, podemos utilizar el operador de conversión segura as?, que retorna nullsi la conversión no es posible.

fun <T> exampleFunction(obj: Any) {
val tObj: T? = obj as? T
if (tObj != null) {
// obj can be safely cast to type parameter T
} else {
// obj cannot be cast to type parameter T
}
}

Es importante tener en cuenta que en Kotlin se produce el borrado de tipos con los genéricos, lo que significa que el tipo real de un objeto genérico no se conoce en tiempo de ejecución. Por lo tanto, no es posible realizar determinadas operaciones, como crear una nueva instancia de un parámetro de tipo o comprobar si un parámetro de tipo es un subtipo de otra clase.

En resumen, las comprobaciones de tipos y las conversiones con genéricos en Kotlin se pueden realizar utilizando los operadores isy ascon el parámetro de tipo entre corchetes angulares, y as?se puede utilizar el operador de conversión segura para evitar ClassCastExceptions. Sin embargo, es posible que ciertas operaciones no sean posibles debido al borrado de tipos.

Conclusión
En conclusión, la conversión de tipos y la conversión inteligente son características importantes en Kotlin, que permiten verificar y convertir objetos a diferentes tipos. Son útiles cuando se trabaja con objetos de diferentes tipos y se realizan operaciones que requieren un tipo específico. Ahora pasemos a la práctica para recordar mejor este tema.

