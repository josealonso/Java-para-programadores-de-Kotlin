# Java explicado a un programador de Kotlin

### Declaración de variables

```java
final String mensaje = "hola"  // variable de solo lectura
final var mensaje = "hola"  // variable de solo lectura
```

Lo del var es bastante moderno. Antes había que poner el tipo de dato de forma explícita.

```kotlin
val mensaje = "hola"  // variable de solo lectura
var mensaje = "hola"  // variable modificable, como se entiende en Java
var n = 2
var i = 3
```

En Kotlin las asignaciones NO son expresiones:

```kotlin
var n = m = getNumber()     // Error de compilación 
```

Esto se puede hacer en Java.
```java
var n = m = getNumber();
```

### La función principal de la aplicación

```java
public static void main(String[] args) {
    System.out.println("Hello world!");
}
```

- Así se declara la función principal. ¡ Solo tres líneas !
- El punto y coma al final de cada línea es obligatorio. Sí, como en C y C++.
- Las funciones SIEMPRE dentro de clases.

¡ Pues en Kotlin es más corto !
```
fun main() {
    println("Hello world!")
}
```

### Otras funciones

```kotlin
fun max(a: Int, b: Int): Int {
    return if (a > b) a else b
}
```

Y como la función tiene una sola expresión, lo puedo acortar más:

```kotlin
fun max(a: Int, b: Int) = if (a > b) a else b
// En funciones tipo expresión, el tipo devuelto puede ser inferido.
```

**if** es una expresión; en Java es una sentencia.

String int max(int a, int b) {
    return if (a > b) a else b;
}

¿Qué quieres decir con que **if** es una expresión en Kotlin?

```kotlin
val maximumValue = if(x > y) x else y
```

Ah, vale, si eso lo puedo hacer en Java usando el operador ternario
```java
var maximumValue = (x > y) ? x : y;
```
 
- ¿La comparación puede ser nula?
- No, se llama operador ternario. ¿A qué mola?

```kotlin
fun greet() {
    val input = readln()
    val name = if (input.isNotBlank()) input else "unknown person"
    println("Hello, $name!") 
}
```

Se pueden evaluar expresiones dentro del argumento a println:

```kotlin
fun greet() {
    val name = readln()
    println("Hello, ${if (name.isBlank()) "someone" else name}!")
}
```

Falta hablar de argumentos por defecto y de argumentos nombrados

### Clases y records
 
Antes de la versión 14 de Java había que generar los métodos con el IDE o con anotaciones en Lombok.
```java
class Person(String name, int age) { 
    // TODO
};
```

Solo puede haber una clase pública en cada fichero.

Desde Java 14 en una sola línea se puede escribir toda la clase.
```java
record Person(String name, int age) { };
```

Ah, eso también se hace en Kotlin. Pero es más fácil, porque no tiene cuerpo (llaves) y es una clase precedida por la palabra **data**.
```kotlin
data class Person(val name: String, var age: Int)
```

Además, no todos los campos son de solo lectura.

#### Métodos de acceso a los campos de una clase
```java
Person person = new Person("Ivan", 28);
println("Este chico se llama" + person.getName());
```

Yo no uso métodos para referirme a los campos, ya que son propiedades. Tampoco uso **new**
```kotlin
val person = Person("Ivan")
println("Este chico se llama" + person.name);
```

Son propiedades de un objeto, como en Javascript.
Solo paso un parámetro al constructor porque el otro tiene un valor por defecto:

```kotlin
data class Person(val name: String, var age: Int = 20)
```

TODO: ejemplo de  métodos get() y set() en Kotlin.
```

### Herencia e interfaces

### Switch y el moderno match

En Kotlin se usa la palabra **when**
.............

### Conversiones implícitas de tipos

### Excepciones

### Sobrecarga de operadores

### Funciones de extensión

### Clases de utilidad

### Tipos función

.
.
.
.
.

### Tratamiento funcional de errores

No creo que me de tiempo.
 
