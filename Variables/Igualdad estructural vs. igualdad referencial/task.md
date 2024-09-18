a sabes que los objetos son estructuras realmente complejas y que las variables solo apuntan a objetos. En esta ocasión, aprenderás sobre la igualdad y cómo entender que las variables apuntan al mismo objeto. Además, finalmente comprenderás por completo el significado de la val palabra clave y evitarás uno de los errores más comunes de los principiantes: asumir que la valpalabra clave garantiza la inmutabilidad.

Comparación
Imagina una situación: recibes dos mensajes idénticos de tu amigo. Los mensajes son "Hola" y "Hola". Los ves y comprendes: los mensajes son los mismos. Si quieres comparar estos mensajes en Kotlin, puedes almacenarlos como valores de cadena:

val msg1 = "Hi"
val msg2 = "Hi"

Luego, puede utilizar el operador de comparación ==. Por ejemplo, print(msg1 == msg2)da true, y print(msg1 == "Hello")da false. Las variables msg1y msg2tienen el mismo estado, lo que se denomina igualdad estructural . También puede comprobar la desigualdad utilizando el operador !=. Por ejemplo, print(msg1 != "Hello")da true.

Tenga en cuenta que algunos tipos de datos complejos pueden no tener el operador ==. Hablaremos de esto más adelante. BoxEn los siguientes ejemplos, tiene este operador.

Veamos un ejemplo de copia de un objeto mutable . Supongamos que tienes una caja que almacena pelotas y puedes agregarle una pelota. Creemos un Box objeto, copiémoslo y cambiemos su original:

val blueBox = Box(3)          // box with 3 balls
val azureBox = blueBox
println(blueBox == azureBox ) // true, it's a copy
blueBox.addBall()             // add a ball to the first box
println(blueBox == azureBox ) // true, the second box also contains 4 balls

Cuando se cambia el primer cuadro, su copia también cambia. Esto se debe a que blueBoxy azureBoxapuntan al mismo objeto. ¿Cómo se comprueba esto? Veamos cómo comprobar la igualdad referencial .

Igualdad referencial
Ya sabes que las variables pueden tener el mismo estado y pueden ser las mismas (apuntar al mismo objeto). En ambos casos, ==devuelve true. Sin embargo, Kotlin proporciona un operador especial ===para comprobar si las variables apuntan al mismo objeto. Por ejemplo:

val blueBox = Box(3)
val azureBox = blueBox
val cyanBox = Box(3)
println(blueBox == azureBox)  // true
println(blueBox === azureBox) // true, azureBox points to the same object
println(blueBox == cyanBox)   // true
println(blueBox === cyanBox)  // false, cyanBox points to another object

Entonces, blueBoxy cyanBoxtienen el mismo estado, pero apuntan a objetos diferentes. En este caso, si cambias el estado de blueBox, cyanBoxsigue igual:

blueBox.addBall()
println(blueBox == cyanBox) // false

También puedes comprobar la desigualdad referencial con el operador !==. Por ejemplo, print(blueBox !== cyanBox) da como resultado true.

Otra cosa interesante sobre el ===operador es la igualdad de objetos inmutables. Veamos el siguiente ejemplo:

var two = 2
var anotherTwo = 2
println(two === anotherTwo) // true

¡Estas variables apuntan al mismo objeto! No te preocupes por esto: como recuerdas, no puedes cambiar un objeto inmutable , por lo que si intentas hacer algo con la variable, apuntará a un nuevo objeto y las demás variables seguirán apuntando al objeto anterior. Intenta cambiar two:

two++
println(two)        // 3
println(anotherTwo) // 2

Por lo tanto, los objetos inmutables son realmente útiles y ayudan a evitar muchos posibles problemas con la copia.

Tipos base e igualdad
Ya estás bastante familiarizado con los objetos en Kotlin: has trabajado mucho con datos de texto y números. En muchos lenguajes de programación, los tipos de datos primitivos, o primitivos , almacenan los tipos de datos simples más utilizados. Su estructura interna está organizada a su manera. Este no es el caso en Kotlin. Como habrás adivinado, los familiares Int, String, Floaty Doubleen Kotlin también son objetos. Pero hay un matiz. Por ejemplo, las variables Into Stringse comportan igual que los tipos de datos primitivos en otros lenguajes de programación, pero al mismo tiempo son objetos, es decir, objetos inmutables. Veamos cómo funciona:

var a: Int = 100
val anotherA: Int = a
println(a == anotherA)  // true
println(a === anotherA) // true
a = 200
println(a == anotherA)  // false
println(a === anotherA) // false

Como puedes ver, cuando cambiamos el valor de la variable a = 200, no cambiamos su objeto: a la variable ase le asigna una nueva referencia al objeto con el valor 200.

Veamos un ejemplo, pero ahora con el Doubletipo de datos:

var d1: Double = 1.5
val d2 = d1
println(d1 === d2) // true
d1 += 1            // d1 is 2.5 now
println(d1 === d2) // false

Como puede ver, el comportamiento es el mismo para estos objetos inmutables. Ahora, veamos un ejemplo con objetos modificables:

val list1: MutableList<Int> = mutableListOf()
val list2: MutableList<Int> = list1
list1.add(1)
println("list1 $list1") // list1 [1]
println("list2 $list2") // list2 [1]
list2.add(5)
println("list1 $list1") // list1 [1, 5]
println("list2 $list2") // list2 [1, 5]

Como se puede ver en este ejemplo, las variables list1y list2hacen referencia al mismo objeto. Cuando se cambia el objeto a través de la primera variable, vemos los datos actualizados a través de la segunda variable.

Conclusión
Repasemos una vez más los puntos principales del tema:

La igualdad estructural de las variables implica igualdad de estados internos.

Puede utilizar los operadores ==y !=para comprobar la igualdad estructural.

La igualdad referencial de variables significa que estas variables apuntan al mismo objeto.

Puede utilizar los operadores ===y !==para comprobar la igualdad referencial.

La valpalabra clave significa que no se puede reasignar la variable, no la inmutabilidad.