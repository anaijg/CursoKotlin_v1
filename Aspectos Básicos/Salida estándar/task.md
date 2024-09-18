
La salida estándar es la operación básica que muestra información en un dispositivo. No todos los programas generan dicha salida. De forma predeterminada, la salida estándar muestra los datos en la pantalla, pero es posible redirigirlos a un archivo.



Impresión de texto
Kotlin tiene dos funciones que envían datos a la salida estándar: `println` y `print`.

La función `println` ( print line ) muestra una cadena seguida de una nueva línea en la pantalla. Por ejemplo, el fragmento de código que aparece a continuación imprime cuatro líneas:
````kotlin
println("I")
println("know")
println("Kotlin")
println("well.")
````

Resultado:
````
I

know

Kotlin

well.
````
Como puedes ver, todas las cadenas se imprimen sin comillas dobles .

También puedes imprimir una línea vacía:
````kotlin
println("Kotlin is a modern programming language.")

println() // prints an empty line

println("It is used all over the world!")
````
Resultado:
````
Kotlin is a modern programming language.

It is used all over the world!
````
La función `print` muestra un valor y coloca el cursor después de . Veamos el ejemplo siguiente. Este fragmento de código genera todas las cadenas en una sola línea:
````kotlin
print("I ")

print("know ")

print("Kotlin ")

print("well.")
````
Resultado:
````
I know Kotlin well.
````


## Impresión de números y caracteres
## Impresión de números y caracteres

Con las funciones `println` y `print`, un programa puede imprimir no sólo cadenas sino también números y caracteres .

Imprimamos dos códigos secretos:
````kotlin
print(108)   // prints a number
print('c')   // prints a character
print("Q")   // prints a string
println('3') // prints a character that represents a digit

print(22)
print('E')
print(8)
println('1')
````
Resultado:
````
108cQ3
22E81
````
Al igual que con las cadenas, no hay comillas.

## El operador $
En el lenguaje de programación Kotlin, el operador $ se utiliza a menudo en plantillas de cadenas de texto para insertar los valores de variables o expresiones directamente en una cadena.

Ejemplos de uso:

**Insertar el valor de una variable:**
````kotlin
val name = "Alice"
println("Hello, $name!") // Output: Hello, Alice!
````
**Insertar el valor de una expresión:**
````kotlin
val a = 5
val b = 10
println("Sum of $a and $b is ${a + b}") // Output: Sum of 5 and 10 is 15
````
Tenga en cuenta que cuando desee insertar una expresión más compleja o acceder a las propiedades de un objeto, utilice llaves `{}` alrededor de la expresión.

De esta forma, el operador $ en Kotlin permite la inserción cómoda y rápida de valores de variables y resultados de expresiones directamente en literales de cadena.

# Conclusión

En este tema, hemos cubierto dos funciones básicas para redirigir información a la salida estándar: printlny print. printlnimprime información seguida de una nueva línea, mientras que printlas imprime una tras otra. Recuerde, podemos usar estas funciones para imprimir no solo cadenas, sino también cualquier otro carácter.

