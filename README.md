# Compilador miniC 🖥️✨

## Descripción
¡Bienvenidos al proyecto del compilador **miniC**! 🚀 Desarrollado en **2024** por **Andrés Martínez Lorca**, este compilador traduce programas escritos en **miniC** (una versión simplificada del lenguaje C) a código ensamblador **MIPS**. Construido con herramientas como **Flex** y **Bison**, este proyecto abarca desde el análisis léxico hasta la generación de código, incluyendo características avanzadas como bucles `for`, operadores relacionales y manejo de errores sintácticos. ¡Una aventura completa en el mundo de los compiladores! 🎉

## Características 🌟
- **Análisis Léxico** 🔍: Reconoce tokens como palabras reservadas, identificadores, números y cadenas con expresiones regulares. Detecta errores como strings mal formados o caracteres no válidos.
- **Análisis Sintáctico** 🛠️: Utiliza **Bison** para verificar la validez sintáctica del código miniC, resolviendo conflictos como `if`/`if-else` con precedencias.
- **Análisis Semántico** ✅: Gestiona identificadores con una tabla de símbolos, verificando declaraciones duplicadas, uso de variables no declaradas y constantes.
- **Generación de Código** 💻: Convierte el código miniC en ensamblador MIPS, manejando operaciones, registros temporales y etiquetas únicas.
- **Funcionalidades Adicionales**:
  - Soporte para bucles `do-while` 🔄.
  - Operadores relacionales (`==`, `!=`, `>`, `>=`, `<`, `<=`) ⚖️.
  - Bucles `for` con múltiples formatos, incluyendo condiciones de parada 📈.
  - Manejo de errores sintácticos con mensajes claros 📢.

## Estructura del Proyecto 📂
- **Archivos Clave**:
  - `listaSimbolos.c`/`listaSimbolos.h`: Gestiona la tabla de símbolos para el análisis semántico.
  - Archivos Flex/Bison: Implementan el analizador léxico y sintáctico.
  - Código de generación: Traduce a MIPS usando una lista de operaciones (`Operacion`).
- **Documentación**: Consulta `DOCUMENTACIÓN.pdf` para detalles sobre la implementación, pruebas y ejemplos de entrada/salida.

## Instrucciones de Instalación ⚙️
1. **Requisitos Previos**:
   - **Flex** y **Bison** instalados.
   - Java Development Kit (JDK) 8 o superior (para herramientas auxiliares, si aplica).
   - Entorno con soporte para compilar y ejecutar código MIPS (como MARS o SPIM).
2. **Clonar el Repositorio**:
   ```bash
   git clone https://github.com/andreesmrtnz/CompiladorPython.git
   cd minic-compiler
   ```
3. **Compilar el Compilador**:
   ```bash
   make
   ```
   Esto genera el ejecutable `minic`.
4. **Ejecutar el Compilador**:
   ```bash
   ./minic programa.mc > programa_salida.s
   ```
   - `programa.mc`: Archivo de entrada en miniC.
   - `programa_salida.s`: Código MIPS generado.

## Ejemplo de Uso 🎮
1. Crea un archivo `hola_mundo.mc`:
   ```c
   main() {
       print("Hola mundo");
   }
   ```
2. Compila y genera el código MIPS:
   ```bash
   ./minic hola_mundo.mc > hola_mundo.s
   ```
3. Ejecuta el código MIPS en un simulador como MARS:
   ```plaintext
   Hola mundo
   ```

## Ejemplos Adicionales 📝
- **Factorial**:
  ```c
  main() {
      var n = 10;
      var factorial = 1;
      var i = 1;
      while (i <= n) {
          factorial = factorial * i;
          i = i + 1;
      }
      print("Factorial(", n, ") = ", factorial);
  }
  ```
  Salida: `Factorial(10) = 3628800`
- **Bucle For**:
  ```c
  main() {
      var a;
      for a inz 0 to 10 {
          print("a=", a, "\n");
      }
  }
  ```
  Salida: Imprime valores de `a` de 0 a 10.

## Puntuación del Proyecto 🏆
El proyecto suma un total de **10.5 puntos** (máximo 10):
- Funcionalidad obligatoria: **8 puntos**
- Errores sintácticos: **0.5 puntos**
- Bucle `do-while`: **0.5 puntos**
- Operadores relacionales: **0.5 puntos**
- Bucle `for`: **1 punto**

## Licencia 📜
Este proyecto está licenciado bajo la **Licencia MIT**. Consulta el archivo `LICENSE` para más detalles.

## Agradecimientos 🙌
Desarrollado por **Andrés Martínez Lorca** en **2024** como parte de la asignatura de Compiladores en la Universidad de Murcia. ¡Gracias por explorar este proyecto! Si te ha gustado, déjame una ⭐ en GitHub. 😊