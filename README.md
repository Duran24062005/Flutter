<div align="center">
    <img src="https://www.intelvue.com/wp-content/uploads/2020/10/Dart-vs-Flutter.jpg" />
    <h1>Flutter Fundamentals</h1>
</div>

## ¿Qué es Flutter?

**Flutter** es un framework de desarrollo de interfaces creado por **Google**, de código abierto, que permite construir aplicaciones nativas para **móvil, web, escritorio y embebidos** a partir de un único código base. Utiliza el lenguaje **Dart**, también desarrollado por Google, y es conocido por su motor de renderizado propio que dibuja cada píxel en pantalla sin depender de los componentes nativos del sistema operativo.

Es uno de los frameworks más populares para desarrollo multiplataforma y se utiliza en aplicaciones móviles, paneles administrativos, herramientas internas, videojuegos simples y apps de escritorio.

---

## ¿Por qué se creó Flutter?

Antes de Flutter, desarrollar para múltiples plataformas implicaba:

* Mantener bases de código separadas para Android (Java/Kotlin) e iOS (Objetive-C/Swift).
* Frameworks híbridos con puentes nativos que afectaban el rendimiento (Cordova, Ionic).
* Inconsistencias visuales entre plataformas.

Flutter busca resolver esto compilando a código nativo y dibujando su propia interfaz con un motor gráfico (Skia/Impeller), logrando **el mismo aspecto y rendimiento en todas las plataformas** desde una sola base de código.

---

## Características principales

### 🚀 Alto rendimiento

Flutter compila a código nativo ARM/x86 (AOT) y utiliza un motor de renderizado propio, evitando los puentes de comunicación que ralentizan a otros frameworks híbridos.

Ideal para:

* Aplicaciones móviles (Android/iOS)
* Aplicaciones web
* Aplicaciones de escritorio (Windows, macOS, Linux)
* Paneles administrativos y dashboards

---

### 🔥 Hot Reload

Su característica más famosa.

Permite:

* Ver cambios en el código reflejados en la app en segundos.
* Mantener el estado de la aplicación mientras se editan widgets.
* Iterar sobre el diseño sin recompilar toda la app.

Todo esto sin perder tiempo en compilaciones completas.

---

### 🧩 Todo es un Widget

En Flutter, cada elemento visual (e incluso muchos elementos no visuales, como el padding o la animación) es un **Widget**.

Los widgets se combinan en forma de árbol para construir la interfaz completa.

---

### 📦 Pub.dev

Flutter/Dart incluye uno de los mejores gestores de paquetes del ecosistema.

Con `pub` puedes:

* Crear proyectos
* Instalar dependencias
* Compilar
* Ejecutar pruebas
* Publicar paquetes

Ejemplo:

```bash
flutter create mi_proyecto
cd mi_proyecto
flutter run
```

---

## ¿Cómo administra la interfaz?

En lugar de usar vistas nativas directamente, Flutter dibuja su propia interfaz usando un sistema de **árbol de widgets**.

Existen tres reglas básicas:

1. Todo en la pantalla es un widget (texto, botón, padding, columna, etc).
2. Los widgets se anidan unos dentro de otros formando un árbol.
3. Cuando el estado cambia, Flutter reconstruye solo la parte del árbol afectada.

Gracias a esto, Flutter logra interfaces reactivas y consistentes en todas las plataformas.

---

## Primer programa

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: Scaffold(
        body: Center(
          child: Text('Hola Mundo'),
        ),
      ),
    );
  }
}
```

Salida:

```
Hola Mundo
```

---

## Variables

En Dart, por convención se usa `final` para valores que no cambiarán.

```dart
void main() {
  final nombre = "Alex";
  print(nombre);
}
```

Variables mutables:

```dart
var edad = 20;
edad += 1;
```

---

## Tipos de datos

### Enteros

```dart
int x = 10;
```

### Decimales

```dart
double precio = 19.99;
```

### Booleanos

```dart
bool activo = true;
```

### Caracteres / Strings

Dart no tiene un tipo `char`; los caracteres se manejan como `String` de longitud 1.

```dart
String letra = 'A';
String nombre = 'Flutter';
```

---

## Funciones

```dart
int sumar(int a, int b) {
  return a + b;
}

void main() {
  var resultado = sumar(5, 3);
  print(resultado);
}
```

---

## Condicionales

```dart
var edad = 20;

if (edad >= 18) {
  print('Mayor');
} else {
  print('Menor');
}
```

---

## Bucles

### for

```dart
for (var i = 1; i < 6; i++) {
  print(i);
}
```

---

### while

```dart
var i = 0;

while (i < 5) {
  print(i);
  i += 1;
}
```

---

### for-in

```dart
for (var i in [1, 2, 3, 4, 5]) {
  print(i);
}
```

---

## Listas

```dart
var numeros = [1, 2, 3, 4];

print(numeros[0]);
```

Agregar elementos:

```dart
var numeros = <int>[];

numeros.add(10);
numeros.add(20);
```

---

## Widgets con estado (Classes)

Parecidos a componentes con propiedades propias.

```dart
class Persona {
  String nombre;
  int edad;

  Persona(this.nombre, this.edad);
}

void main() {
  var p = Persona('Ana', 22);
  print(p.nombre);
}
```

---

## StatelessWidget vs StatefulWidget

Los widgets pueden ser de dos tipos según si manejan estado interno o no.

```dart
enum Estado {
  activo,
  inactivo,
}
```

Muy usados junto con `switch` para renderizar diferentes interfaces.

---

## Switch

Similar a `match` en otros lenguajes.

```dart
var numero = 2;

switch (numero) {
  case 1:
    print('Uno');
    break;
  case 2:
    print('Dos');
    break;
  default:
    print('Otro');
}
```

---

## Manejo de errores

Dart utiliza principalmente excepciones tradicionales, junto con tipos que representan ausencia de valor.

### Null safety

Representa un valor que puede existir o no.

```dart
int? x = 5;
int? y;
```

---

### Try / Catch

Representa la captura de errores en tiempo de ejecución.

```dart
double dividir(double a, double b) {
  if (b == 0) {
    throw Exception('No se puede dividir por cero');
  }
  return a / b;
}

void main() {
  try {
    print(dividir(10, 0));
  } catch (e) {
    print(e);
  }
}
```

---

## ¿Dónde se utiliza Flutter?

Actualmente Flutter se utiliza en proyectos como:

* Aplicaciones móviles multiplataforma
* Paneles administrativos y dashboards
* Herramientas internas de empresas
* Aplicaciones de escritorio
* Prototipos rápidos de producto
* Aplicaciones embebidas (Flutter para IoT)
* MVPs de startups

Grandes empresas como Google, BMW, eBay, Alibaba y ByteDance lo utilizan en partes de su infraestructura para obtener un mejor equilibrio entre velocidad de desarrollo y consistencia visual.

---

## Ventajas

* Un solo código base para múltiples plataformas.
* Hot Reload para iteración rápida.
* Interfaz consistente sin depender de componentes nativos.
* Gran ecosistema de paquetes (pub.dev).
* Excelente documentación.
* Buen rendimiento gracias a la compilación a código nativo.
* Amplia colección de widgets predefinidos (Material y Cupertino).

---

## Desventajas

* Tamaño de la app final mayor que en desarrollo nativo puro.
* Necesidad de escribir código específico para acceder a ciertas APIs nativas.
* Curva de aprendizaje en conceptos propios como el árbol de widgets y la gestión de estado.
* Menor cantidad de bibliotecas en algunos nichos muy específicos comparado con el desarrollo nativo.

---

## ¿Vale la pena aprender Flutter?

Depende de tus objetivos:

* **Sí**, si te interesa el desarrollo de aplicaciones móviles multiplataforma, prototipado rápido, dashboards o herramientas internas con una sola base de código.
* **No es la primera opción** si tu enfoque principal es programación de sistemas de bajo nivel o rendimiento extremo cercano al hardware. En esos campos, lenguajes como **Rust** o **C++** siguen siendo dominantes.

Dado que actualmente estoy retomando **Python para Machine Learning y Visión por Computadora**, debo **priorizar Python hasta dominarlo**. Una vez tenga una base sólida, aprender Flutter puede ser una excelente inversión para construir interfaces de usuario que consuman modelos entrenados en Python, crear aplicaciones móviles o de escritorio que integren esos modelos, o desarrollar herramientas visuales donde la velocidad de desarrollo multiplataforma sea clave.

- [Documentation](https://flutter.dev/)
- [Video Tutorial by MOure Dev](https://www.youtube.com/watch?v=1xipEp4H7Xs)

```
23/07/2026 - By Alexi Dg
```
<div align="center">
    <img src="https://d2ms8rpfqc4h24.cloudfront.net/What_are_Flutter_and_Dart_Where_is_it_Useful1_12100cd269.jpg" alt="flutter logo gif" height="full" />
</div>

![Img](https://docs.flutter.dev/assets/images/dash/dash-fainting.gif)