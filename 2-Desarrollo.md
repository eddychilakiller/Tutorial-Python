## **Fase 2: Desarrollo de Software y Buenas Prácticas**

### **1. Programación Orientada a Objetos (OOP)**

**Objetivo:** Entender y aplicar los principios de la Programación Orientada a Objetos (OOP) en Python para diseñar software modular, reutilizable y mantenible.

1. **Introducción a la Programación Orientada a Objetos (OOP):**
   - La Programación Orientada a Objetos es un paradigma de programación que utiliza "objetos" para representar datos y métodos asociados que operan sobre esos datos. En Python, todo, incluyendo números, cadenas, y funciones, es un objeto, lo que hace que Python sea un lenguaje orientado a objetos de forma natural.
   - **Conceptos clave de OOP:**
     - **Clase**: Es una plantilla o un blueprint que define una estructura de datos y el comportamiento asociado. Una clase agrupa datos (atributos) y funciones (métodos) que actúan sobre esos datos.
     - **Objeto**: Es una instancia de una clase. Cada objeto tiene un estado (almacenado en sus atributos) y un comportamiento (definido por sus métodos).
     - **Atributos**: Son variables que almacenan el estado del objeto. Cada objeto de una clase puede tener diferentes valores en sus atributos.
     - **Métodos**: Son funciones definidas dentro de una clase que describen el comportamiento de los objetos.

2. **Definición y Uso de Clases y Objetos:**
   - **Definir una clase en Python**:
     - La definición de una clase en Python se realiza usando la palabra clave `class`. Dentro de la clase, se definen los atributos y métodos que serán compartidos por todos los objetos de esa clase.
     - Ejemplo básico de una clase:
       ```python
       class Perro:
           def __init__(self, nombre, edad):
               self.nombre = nombre
               self.edad = edad

           def ladrar(self):
               print(f"{self.nombre} está ladrando")

       # Crear un objeto (instancia) de la clase Perro
       mi_perro = Perro("Firulais", 5)
       mi_perro.ladrar()  # Imprime "Firulais está ladrando"
       ```
     - **`__init__`**: Es un método especial que se ejecuta automáticamente cuando se crea un nuevo objeto de la clase. Se usa para inicializar los atributos del objeto.
     - **`self`**: Es una referencia al objeto actual que permite acceder a los atributos y métodos dentro de la clase. Es obligatorio como primer parámetro en todos los métodos de instancia.

3. **Principios SOLID en Python:**
   - Los principios SOLID son cinco principios que ayudan a diseñar software de manera que sea más comprensible, flexible y mantenible:
     - **S - Single Responsibility Principle (SRP)**: Una clase debe tener una única responsabilidad o razón para cambiar. Esto significa que una clase debe hacer solo una cosa, y hacerlo bien.
     - **O - Open/Closed Principle (OCP)**: Las clases deben estar abiertas para la extensión, pero cerradas para la modificación. Esto se logra diseñando clases que puedan extenderse mediante herencia o composición, sin necesidad de modificar el código existente.
     - **L - Liskov Substitution Principle (LSP)**: Los objetos de una clase derivada deben poder reemplazar objetos de la clase base sin afectar el comportamiento del sistema. Esto significa que las clases derivadas deben ser completamente sustituibles por sus clases base.
     - **I - Interface Segregation Principle (ISP)**: Los clientes no deberían verse obligados a depender de interfaces que no utilizan. En lugar de tener una interfaz general que obligue a las clases a implementar métodos innecesarios, es mejor dividirla en interfaces más específicas y pequeñas.
     - **D - Dependency Inversion Principle (DIP)**: Los módulos de alto nivel no deben depender de módulos de bajo nivel. Ambos deben depender de abstracciones. Además, las abstracciones no deben depender de los detalles; los detalles deben depender de las abstracciones.

4. **Herencia, Polimorfismo y Encapsulamiento:**
   - **Herencia**:
     - La herencia permite crear nuevas clases a partir de clases existentes. La nueva clase (subclase o clase hija) hereda los atributos y métodos de la clase base (superclase o clase padre), lo que promueve la reutilización de código.
     - Ejemplo:
       ```python
       class Animal:
           def __init__(self, nombre):
               self.nombre = nombre

           def hacer_sonido(self):
               pass

       class Perro(Animal):
           def hacer_sonido(self):
               return "Guau!"

       class Gato(Animal):
           def hacer_sonido(self):
               return "Miau!"

       # Uso de la herencia
       mi_perro = Perro("Firulais")
       print(mi_perro.hacer_sonido())  # Imprime "Guau!"
       ```
     - **Uso de `super()`**: La función `super()` se utiliza para llamar a un método de la superclase desde la subclase. Esto es útil para extender la funcionalidad de los métodos heredados sin sobrescribir completamente su comportamiento.

   - **Polimorfismo**:
     - El polimorfismo permite utilizar una interfaz común para interactuar con objetos de diferentes tipos. En el ejemplo anterior, el método `hacer_sonido` puede ser llamado en cualquier instancia de `Animal` (ya sea `Perro` o `Gato`), y el resultado será diferente dependiendo de la clase específica del objeto.
     - Esto permite que las funciones y métodos manejen objetos de diferentes clases de manera uniforme.

   - **Encapsulamiento**:
     - El encapsulamiento es la técnica de restringir el acceso a ciertos componentes de un objeto para que no puedan ser modificados directamente desde fuera de la clase. En Python, se puede indicar que un atributo es "privado" usando un guion bajo `_` antes del nombre del atributo (aunque esto es más una convención que una regla estricta).
     - Ejemplo:
       ```python
       class CuentaBancaria:
           def __init__(self, saldo):
               self._saldo = saldo  # Atributo "privado"

           def depositar(self, cantidad):
               if cantidad > 0:
                   self._saldo += cantidad

           def retirar(self, cantidad):
               if 0 < cantidad <= self._saldo:
                   self._saldo -= cantidad

           def obtener_saldo(self):
               return self._saldo

       cuenta = CuentaBancaria(1000)
       cuenta.depositar(500)
       print(cuenta.obtener_saldo())  # Imprime 1500
       ```

### **2. Manejo de Errores y Excepciones**

**Objetivo:** Aprender a manejar errores y excepciones de manera robusta para crear software confiable y fácil de depurar.

1. **Introducción a las Excepciones:**
   - Las excepciones en Python son eventos que ocurren durante la ejecución de un programa y que interrumpen su flujo normal. Pueden ser causadas por errores de programación, como dividir por cero, intentar acceder a un archivo inexistente o tratar de convertir una cadena en un número.
   - **Excepciones comunes en Python**:
     - `ZeroDivisionError`: Ocurre cuando se intenta dividir por cero.
     - `FileNotFoundError`: Ocurre cuando se intenta acceder a un archivo que no existe.
     - `IndexError`: Ocurre cuando se intenta acceder a un índice fuera del rango de una lista.
     - `KeyError`: Ocurre cuando se intenta acceder a una clave inexistente en un diccionario.
     - `TypeError`: Ocurre cuando se opera sobre tipos de datos incompatibles.
     - `ValueError`: Ocurre cuando una función recibe un argumento de tipo correcto, pero con un valor inapropiado.

2. **Uso de `try`, `except`, `else`, y `finally`:**
   - El manejo de excepciones en Python se realiza con las estructuras `try` y `except`. Dentro del bloque `try`, se coloca el código que podría generar una excepción. Si ocurre una excepción, el flujo del programa se transfiere inmediatamente al bloque `except`.
   - Ejemplo básico:
     ```python
     try:
         resultado = 10 / 0
     except ZeroDivisionError:
         print("No se puede dividir por cero")
     ```
   - **Bloque `else`**:
     - El bloque `else` se ejecuta si no se produce ninguna excepción en el bloque `try`. Esto es útil para separar el código que debería ejecutarse solo si todo salió bien en el bloque `try`.
     - Ejemplo:
       ```python
       try:
           resultado = 10 / 2
       except ZeroDivisionError:
           print("No se puede dividir por cero")
       else:
           print(f"El resultado es {resultado}")
       ```
   - **Bloque `finally`**:
     - El bloque `finally` se ejecuta siempre, haya ocurrido o no una excepción. Es útil

 para liberar recursos o realizar limpiezas necesarias, como cerrar archivos o conexiones de red.
     - Ejemplo:
       ```python
       try:
           archivo = open('mi_archivo.txt', 'r')
           contenido = archivo.read()
       except FileNotFoundError:
           print("El archivo no existe")
       finally:
           archivo.close()
       ```

3. **Creación de Excepciones Personalizadas:**
   - Puedes definir tus propias excepciones en Python creando una clase que herede de `Exception`. Esto es útil cuando necesitas manejar situaciones específicas que no están cubiertas por las excepciones estándar de Python.
   - Ejemplo:
     ```python
     class ErrorSaldoInsuficiente(Exception):
         pass

     def retirar_dinero(saldo, cantidad):
         if cantidad > saldo:
             raise ErrorSaldoInsuficiente("Saldo insuficiente para la operación")
         saldo -= cantidad
         return saldo

     try:
         nuevo_saldo = retirar_dinero(100, 150)
     except ErrorSaldoInsuficiente as e:
         print(e)
     ```

4. **Logging para Depuración y Monitoreo:**
   - **¿Qué es el logging?** Logging es el proceso de registrar mensajes (logs) que pueden ayudar a depurar un programa, monitorear su funcionamiento, o analizar su comportamiento en producción.
   - **Configuración básica del módulo `logging`**:
     - Python incluye un módulo `logging` que permite registrar mensajes en diferentes niveles de severidad: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`.
     - Ejemplo básico de configuración:
       ```python
       import logging

       logging.basicConfig(level=logging.INFO)
       logging.info("Este es un mensaje informativo")
       logging.warning("Este es un mensaje de advertencia")
       logging.error("Este es un mensaje de error")
       ```
     - **Logging en archivos**: Puedes configurar el logging para que los mensajes se guarden en un archivo en lugar de imprimirse en la consola:
       ```python
       logging.basicConfig(filename='app.log', level=logging.INFO)
       logging.info("Este mensaje se guarda en un archivo")
       ```
   - **Aplicación práctica de logging en una aplicación**:
     - Logging es extremadamente útil en aplicaciones grandes y en producción, donde es necesario rastrear el comportamiento del sistema, diagnosticar problemas, y tomar decisiones basadas en el análisis de logs.

### **3. Testing y Calidad del Código**

**Objetivo:** Aprender a escribir pruebas automatizadas para asegurar que tu código funciona correctamente, y adoptar buenas prácticas para mantener un código limpio y mantenible.

1. **Introducción a las Pruebas Unitarias:**
   - Las pruebas unitarias son pruebas automatizadas que verifican el correcto funcionamiento de pequeñas unidades de código, como funciones o métodos. Su objetivo es asegurar que cada parte del código funcione de manera aislada y según lo esperado.
   - **Beneficios de las pruebas unitarias**:
     - Detectar errores en etapas tempranas del desarrollo.
     - Facilitar el mantenimiento del código, ya que se puede refactorizar con confianza.
     - Documentar el comportamiento esperado del código.
   - **El módulo `unittest`**:
     - Python incluye el módulo `unittest` que proporciona un framework para escribir y ejecutar pruebas unitarias.
     - Ejemplo básico de una prueba unitaria:
       ```python
       import unittest

       def sumar(a, b):
           return a + b

       class TestSumar(unittest.TestCase):
           def test_sumar(self):
               self.assertEqual(sumar(3, 4), 7)
               self.assertEqual(sumar(-1, 1), 0)

       if __name__ == '__main__':
           unittest.main()
       ```

2. **Uso de `pytest` para Pruebas Unitarias:**
   - **`pytest`** es un framework más avanzado y flexible que `unittest`, ampliamente utilizado en la industria por su simplicidad y extensibilidad.
   - **Ventajas de `pytest`**:
     - Sintaxis simple y clara.
     - Soporte para fixtures, que son funciones que preparan el entorno de prueba.
     - Fácil integración con otras herramientas como `coverage.py` para medir la cobertura de código.
   - **Escribir pruebas con `pytest`**:
     - Ejemplo básico:
       ```python
       def sumar(a, b):
           return a + b

       def test_sumar():
           assert sumar(3, 4) == 7
           assert sumar(-1, 1) == 0
       ```
     - **Ejecutar pruebas**: Para ejecutar las pruebas, simplemente corre `pytest` en la terminal dentro del directorio de tu proyecto.

3. **Cobertura de Código con `coverage.py`:**
   - **¿Qué es la cobertura de código?** La cobertura de código mide el porcentaje de código que es ejecutado durante las pruebas. Un alto porcentaje de cobertura es un indicador de que las pruebas son exhaustivas, aunque no garantiza que el código esté libre de errores.
   - **Instalación y uso de `coverage.py`**:
     - Instala `coverage` con `pip install coverage`.
     - Para medir la cobertura: `coverage run -m pytest`.
     - Genera un reporte de cobertura: `coverage report` o `coverage html` (para un reporte en formato HTML).
   - **Análisis de la cobertura**:
     - Revisa el reporte para identificar partes del código que no están siendo probadas y que podrían requerir pruebas adicionales.

4. **Integración Continua (CI) y Pruebas Automatizadas:**
   - **¿Qué es la Integración Continua (CI)?** CI es una práctica de desarrollo donde el código es integrado en un repositorio compartido frecuentemente, y se ejecutan automáticamente pruebas y otras verificaciones. Esto ayuda a detectar errores rápidamente y a asegurar la calidad del código.
   - **Herramientas de CI**:
     - **GitHub Actions**: Proporciona una plataforma para definir workflows que ejecuten pruebas y despliegues automáticos en respuesta a eventos como push o pull requests en GitHub.
     - **Jenkins**: Una herramienta de automatización de código abierto que facilita la implementación de CI/CD pipelines personalizados.
   - **Configuración básica de CI**:
     - **GitHub Actions**:
       - Crea un archivo `.github/workflows/ci.yml` en tu repositorio:
         ```yaml
         name: Python CI

         on: [push, pull_request]

         jobs:
           build:
             runs-on: ubuntu-latest
             steps:
               - uses: actions/checkout@v2
               - name: Set up Python
                 uses: actions/setup-python@v2
                 with:
                   python-version: 3.x
               - name: Install dependencies
                 run: |
                   python -m pip install --upgrade pip
                   pip install pytest
               - name: Run tests
                 run: |
                   pytest
         ```
     - Este archivo configura un workflow que se ejecutará cada vez que se haga un push o una pull request, instalando las dependencias y ejecutando las pruebas con `pytest`.

5. **Revisión de Código y Buenas Prácticas:**
   - **Revisión de Código (Code Review)**:
     - La revisión de código es una práctica donde los miembros del equipo revisan el código de sus compañeros antes de fusionarlo en el repositorio principal. Esto ayuda a detectar errores, mejorar la calidad del código y compartir conocimiento dentro del equipo.
     - **Buenas prácticas en la revisión de código**:
       - Mantén las revisiones pequeñas y manejables.
       - Proporciona comentarios constructivos y detallados.
       - Usa herramientas como pull requests en GitHub o Bitbucket para facilitar el proceso.
   - **Escritura de Código Limpio**:
     - Sigue las convenciones de estilo PEP 8 para mantener el código consistente y legible.
     - Escribe funciones pequeñas y bien definidas que hagan una cosa y la hagan bien.
     - Utiliza nombres descriptivos para variables, funciones y clases.
     - Evita el uso de "magia" en el código: escribe código que sea fácil de seguir y entender.


