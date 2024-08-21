## **Fase 1: Fundamentos Sólidos en Python**

### **1. Instalación y Configuración para Entornos de Desarrollo**

**Objetivo:** Configurar tu entorno de desarrollo para escribir, ejecutar y depurar código en Python de manera eficiente.

1. **Instalación de Python:**
   - **Descargar e instalar Python**: Ve a la página oficial de Python ([python.org/downloads](https://www.python.org/downloads/)) y descarga la última versión estable para tu sistema operativo (Windows, macOS, Linux). Durante la instalación, asegúrate de marcar la opción "Add Python to PATH" para que puedas ejecutar Python desde la línea de comandos.

2. **Configuración de un Editor de Código:**
   - **Elección de un editor de código**: Los editores más populares para Python son Visual Studio Code (VS Code) y PyCharm. VS Code es más ligero y tiene una gran cantidad de extensiones, mientras que PyCharm es un IDE más completo con características específicas para Python.
   - **Instalación de Visual Studio Code**:
     - Descarga e instala VS Code desde [code.visualstudio.com](https://code.visualstudio.com/).
     - Una vez instalado, agrega la extensión de Python desde la tienda de extensiones de VS Code. Esto te permitirá tener soporte para autocompletado, linting (detección de errores), depuración y más.
   - **Configuración de PyCharm**:
     - Descarga PyCharm Community (gratuito) o Professional (pago) desde [jetbrains.com/pycharm](https://www.jetbrains.com/pycharm/).
     - Durante la configuración inicial, asegúrate de seleccionar la versión de Python que instalaste previamente.

3. **Uso de la Terminal y Python REPL:**
   - **Terminal/Command Line**: Familiarízate con la terminal (Command Prompt en Windows, Terminal en macOS/Linux). Aprende a ejecutar comandos básicos como navegar entre directorios (`cd`), listar archivos (`ls` o `dir`) y ejecutar scripts de Python (`python script.py`).
   - **Python REPL**: El Python REPL (Read-Eval-Print Loop) es un entorno interactivo donde puedes ejecutar comandos Python directamente. Simplemente escribe `python` en la terminal para iniciarlo. Aquí puedes probar fragmentos de código rápidamente.

4. **Configuración de Entornos Virtuales:**
   - **¿Qué es un entorno virtual?** Un entorno virtual te permite crear un espacio aislado para tus proyectos, donde puedes instalar librerías específicas sin afectar las globales. Esto es crucial cuando trabajas en múltiples proyectos que pueden requerir diferentes versiones de paquetes.
   - **Crear un entorno virtual**:
     - En tu terminal, navega al directorio donde quieres crear tu proyecto y ejecuta: `python -m venv nombre_del_entorno`.
     - Activa el entorno:
       - En Windows: `nombre_del_entorno\Scripts\activate`
       - En macOS/Linux: `source nombre_del_entorno/bin/activate`
     - Una vez activado, verás que el nombre del entorno aparece en tu terminal (ej. `(nombre_del_entorno) C:\proyecto>`).
   - **Instalar paquetes dentro del entorno**:
     - Usa `pip` (Python's package installer) para instalar paquetes: `pip install nombre_paquete`.
     - Para desactivar el entorno: `deactivate`.

5. **Control de Versiones con Git y GitHub:**
   - **¿Qué es Git?** Git es un sistema de control de versiones que te permite rastrear cambios en tu código, revertir a versiones anteriores y colaborar con otros desarrolladores.
   - **Instalación de Git**: Descarga e instala Git desde [git-scm.com](https://git-scm.com/).
   - **Configuración inicial de Git**:
     - Configura tu nombre de usuario y correo electrónico: `git config --global user.name "Tu Nombre"`, `git config --global user.email "tuemail@dominio.com"`.
   - **Uso básico de Git**:
     - Inicializa un repositorio Git en un proyecto: `git init`.
     - Añade archivos al control de versiones: `git add .` (esto añade todos los archivos en el directorio).
     - Crea un commit (un punto en el historial del proyecto): `git commit -m "Mensaje del commit"`.
     - **Uso de GitHub**:
       - Crea una cuenta en [GitHub](https://github.com/).
       - Crea un nuevo repositorio en GitHub.
       - Enlaza tu repositorio local con GitHub: `git remote add origin https://github.com/usuario/repo.git`.
       - Sube tus cambios a GitHub: `git push origin master`.

### **2. Sintaxis y Estructuras de Control**

**Objetivo:** Aprender la sintaxis básica de Python y cómo utilizar estructuras de control para tomar decisiones y repetir acciones en tu código.

1. **Variables y Tipos de Datos:**
   - **Variables**: Son contenedores que almacenan valores. Se definen simplemente asignando un valor a un nombre. Ejemplo: `x = 10`.
   - **Tipos de Datos**:
     - **Enteros (`int`)**: Números sin decimales, e.g., `10`.
     - **Flotantes (`float`)**: Números con decimales, e.g., `10.5`.
     - **Cadenas de texto (`str`)**: Texto encerrado entre comillas simples o dobles, e.g., `'Hola'` o `"Hola"`.
     - **Listas (`list`)**: Secuencias ordenadas de elementos, e.g., `[1, 2, 3]`.
     - **Tuplas (`tuple`)**: Secuencias ordenadas e inmutables, e.g., `(1, 2, 3)`.
     - **Diccionarios (`dict`)**: Colecciones de pares clave-valor, e.g., `{'nombre': 'Juan', 'edad': 25}`.
     - **Booleanos (`bool`)**: Representa `True` o `False`.

2. **Operadores en Python:**
   - **Aritméticos**: `+`, `-`, `*`, `/`, `%` (módulo), `**` (potencia).
   - **Comparación**: `==`, `!=`, `>`, `<`, `>=`, `<=`.
   - **Lógicos**: `and`, `or`, `not`.
   - **Asignación**: `=`, `+=`, `-=`, `*=`, `/=`.

3. **Estructuras de Control:**
   - **Condicionales (`if`, `elif`, `else`)**:
     - Ejemplo básico: 
       ```python
       edad = 18
       if edad >= 18:
           print("Eres mayor de edad")
       else:
           print("Eres menor de edad")
       ```
   - **Bucles (`for`, `while`)**:
     - **`for`**: Itera sobre una secuencia (como una lista o un rango).
       - Ejemplo:
         ```python
         for i in range(5):
             print(i)
         ```
     - **`while`**: Repite un bloque de código mientras una condición sea verdadera.
       - Ejemplo:
         ```python
         contador = 0
         while contador < 5:
             print(contador)
             contador += 1
         ```

4. **Comprensión de Listas:**
   - Una forma concisa de crear listas basadas en secuencias o condiciones.
   - Ejemplo:
     ```python
     cuadrados = [x**2 for x in range(10)]
     ```
   - **Filtrado en comprensión de listas**:
     - Ejemplo: `pares = [x for x in range(10) if x % 2 == 0]`.

### **3. Funciones y Modularidad**

**Objetivo:** Entender cómo encapsular lógica en funciones para reutilización y cómo organizar tu código en módulos para mantenerlo limpio y manejable.

1. **Definición y Uso de Funciones:**
   - **Definición de una función**:
     - Usa `def` para definir una función. Ejemplo:
       ```python
       def saludar(nombre):
           print(f"Hola, {nombre}")
       ```
     - **Llamada a una función**: `saludar("Ana")` imprimirá "Hola, Ana".
   - **Parámetros y Argumentos**:
     - **Parámetros**: Variables que se definen en la firma de la función.
     - **Argumentos**: Valores reales que se pasan a la función cuando se llama.
   - **Valores de retorno**:
     - Usa `return` para devolver un valor desde la función. Ejemplo:
       ```python
       def sumar(a, b):
           return a + b
       ```
     - Llama a la función y captura el valor devuelto: `resultado = sumar(3, 4)`.

2. **Ámbito de las Variables (Scope):**
   - **Variables locales**: Definidas dentro de una función y accesibles solo dentro de ella.
   - **Variables globales**: Definidas fuera de cualquier función y accesibles desde cualquier parte del código.
   - **Uso de `global` para modificar una variable global
