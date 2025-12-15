
📘 FUNDAMENTOS CLAVE DE PROGRAMACIÓN CON KOTLIN
Expresiones, Operadores, Funciones y Jetpack Compose

📌 INTRODUCCIÓN

Este documento presenta los conceptos fundamentales de programación en Kotlin, enfocados en el uso de expresiones, operadores y funciones, así como su aplicación práctica en Jetpack Compose para el desarrollo de interfaces modernas en Android.

El objetivo es fortalecer la lógica de programación y promover el uso de código limpio, reutilizable y modular.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1️⃣ ¿QUÉ ES UNA EXPRESIÓN?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

En Kotlin, una expresión es una combinación de valores, variables, operadores y/o llamadas a funciones que el compilador evalúa para producir un único valor.

A diferencia de una declaración, que solo ejecuta una acción, toda expresión siempre devuelve un resultado.

🔹 Tipos Comunes de Expresiones

• Expresiones Aritméticas
Devuelven un valor numérico (Int, Double).

• Expresiones Lógicas o Booleanas
Devuelven true o false.

• Expresiones de Cadena
Usan concatenación o template strings y devuelven un String.

🔹 Ejemplos de Expresiones en Kotlin
📐 Expresión Aritmética
val radio: Double = 5.0
val area = 3.14 * radio * radio


Resultado: 78.5

🔐 Expresión Lógica
val edad: Int = 25
val activo: Boolean = true
val esValido = (edad >= 18) && activo


Resultado: true

💬 Expresión de Cadena
val nombre = "Alice"
val saludo = "Hola, $nombre!"


Resultado: "Hola, Alice!"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

2️⃣ TIPOS DE OPERADORES EN KOTLIN

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Los operadores son funciones especiales que permiten realizar cálculos, comparaciones o combinaciones lógicas entre valores.

🔢 Operadores Aritméticos
Operador	Función	Ejemplo	Resultado
+	Suma	10 + 3	13
-	Resta	10 - 3	7
*	Multiplicación	10 * 3	30
/	División entera	10 / 3	3
%	Módulo	10 % 3	1
🔍 Operadores Relacionales

Devuelven siempre un valor Boolean.

Operador	Significado	Resultado
==	Igual a	true / false
!=	Diferente de	true / false
>	Mayor que	true / false
<=	Menor o igual que	true / false
🔗 Operadores Lógicos
Operador	Nombre	Función
&&	AND	Ambas condiciones deben ser true
		
!	NOT	Niega el valor booleano

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

3️⃣ EJERCICIOS PRÁCTICOS CON FUNCIONES

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Una función es un bloque de código reutilizable que usa expresiones y operadores para resolver un problema específico.

🧮 Ejercicio 1: Calculadora de IVA (19%)

Descripción:
Calcula el precio final aplicando un 19% de IVA.

fun calcularIva(precioBase: Double): Double {
    val iva = precioBase * 0.19
    val precioFinal = precioBase + iva
    return precioFinal
}


Ejemplo de uso:

println(calcularIva(100.0))


Resultado: 119.0

🔐 Ejercicio 2: Verificación de Contraseña

Descripción:
Devuelve true si la contraseña tiene más de 8 caracteres y no contiene "123".

fun esSegura(contraseña: String): Boolean {
    return (contraseña.length > 8) && (!contraseña.contains("123"))
}

🔢 Ejercicio 3: Número Par o Impar
fun esPar(numero: Int): Boolean {
    return (numero % 2) == 0
}

👤 Ejercicio 4: Saludo Condicional por Rol
fun verificarAcceso(usuario: String, rol: String): String {
    return if (rol == "Admin" || rol == "Editor") {
        "Bienvenido, $usuario. Acceso completo."
    } else {
        "Acceso denegado."
    }
}

🌡️ Ejercicio 5: Conversión de Temperatura
fun celsiusAFahrenheit(celsius: Double): Double {
    return (celsius * 9.0 / 5.0) + 32.0
}


Resultado para 20.0: 68.0

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

4️⃣ ACTIVIDADES EN CLASE – JETPACK COMPOSE

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📝 Ejercicio 1: Componente Text Reutilizable
@Composable
fun TextUi(text: String){
    Text(
        text = text,
        color = Color.Red,
        fontSize = 20.sp,
        fontFamily = FontFamily.Cursive,
        fontWeight = FontWeight.Bold,
        textAlign = TextAlign.Center,
        modifier = Modifier
            .fillMaxWidth()
            .background(Color.Blue)
    )
}


Uso del componente:

TextUi(text = "Mi nombre es Fabricio Quillupangui")
TextUi(text = "Mi edad es 28 años")
TextUi(text = "Estudio Desarrollo de Software")

🧮 Ejercicio 2: Calculadora Básica con Compose
📥 Campo de Texto
@Composable
fun CreateTextField(valor: String, label: String, onValue: (String)-> Unit){
    TextField(
        value = valor,
        onValueChange = onValue,
        label = { Text(text = label) }
    )
}

🔘 Botón Reutilizable
@Composable
fun ButtonUi(text: String, onClick:()-> Unit){
    Button(onClick = onClick) {
        Text(text = text)
    }
}

🧠 Lógica Principal
var numero1 by rememberSaveable { mutableStateOf("") }
var numero2 by rememberSaveable { mutableStateOf("") }
var resultado by rememberSaveable { mutableStateOf("") }


Se implementan operaciones de:
✔ Suma
✔ Resta
✔ Multiplicación
✔ División (con validación de división por cero)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🧠 CONCEPTO CLAVE FINAL

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Este proyecto demuestra:

✔ Uso correcto de expresiones y operadores
✔ Creación de funciones reutilizables
✔ Manejo de estado con rememberSaveable
✔ Desarrollo de interfaces con Jetpack Compose
✔ Aplicación de componentes reutilizables
✔ Código limpio, organizado y modular
