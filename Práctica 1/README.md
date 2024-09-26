# Práctica 1

El presente repositorio contiene ejercicios prácticos y código relacionado con la asignatura 40982 - Visión por Computador. Cada una de las tareas está acompañada de una descripción de la implementación del código y documentación relevante al respecto.

# 📖 Tabla de Contenidos
  - [Paquetes utilizados](#Paquetes-utilizados)
  - [Tarea 1: Textura de tablero de ajedrez](#Tarea-1:-Textura-de-tablero-de-ajedrez)
  - [Tarea 2: Crear una Imagen al estilo Mondrian](#Tarea-2:-Crear-una-imagen-al-estilo-Mondrian)
  - [Tarea 3: Resolver una de las tareas anteriores usando funciones de dibujo de OpenCV](#Tarea-3)
  - [Tarea seleccionada: Imagen al estilo Mondrian](#Tarea-3:-Tarea-seleccionada)
  - [Tarea 4: Modificar planos de la imagen](#Tarea-4:-Modificar-planos-de-la-imagen)
  - [Tarea 5: Resaltar los Píxeles más Brillantes y Oscuros](#Tarea-5:-Resaltar-pixeles)
  - [Tarea 6: Propuesta de Pop Art usando una Cámara Web o Entrada de Video](#Tarea-6:-Propuesta-de-Pop-Art)
  - [Invertir los Colores del Flujo de la Cámara](#Tarea-6:-Invertir-los-colores)
  - [Gradiente Interactivo en la Cámara](#Tarea-6:-Gradiente-Interactivo)
  - [Tarea Extra: Resaltar Píxeles Oscuros y Brillantes](#Tarea-Extra:-Resaltar-pixeles)
  - [Guía de Instalación](#Guia-de-Instalacion)
  - [Configuración del Entorno de Desarrollo](#Configuracion-Entorno-Desarrollo)
  - [Comandos Básicos de Anaconda](#Comandos-basicos-Anaconda)
  - [Colaboradores](#Colaboradores)
  - [Disclaimer](#Disclaimer)

# 📦 Paquetes utilizados <a name="Paquetes-utilizados"></a>

Para ejecutar el código incluido en los diferentes notebooks de Jupyter, es necesario tener instaladas las siguientes librerías:

- OpenCV
- NumPy
- Matplotlib

Asegúrate de disponer instalado los paquetes anteriormente listados, para ello, ejecuta el siguiente comando:

```bash
pip install opencv-python numpy matplotlib
```

# Tarea 1: Textura de tablero de ajedrez <a name="Tarea-1:-Textura-de-tablero-de-ajedrez"></a>

Esta tarea consiste en crear una textura de un tablero de ajedrez de dimensión 8x8 y mostrarla utilizando la librería *Matplotlib*.

<ins>Documentación utilizada:</ins>

- https://www.geeksforgeeks.org/matplotlib-pyplot-tick_params-in-python/

- https://www.geeksforgeeks.org/matplotlib-pyplot-xticks-in-python/

# Tarea 2: Crear una imagen al estilo Mondrian <a name="Tarea-2:-Crear-una-imagen-al-estilo-Mondrian"></a>

Esta tarea genera una obra inspirada en el pintor neerlandés [Piet Mondrian](https://es.wikipedia.org/wiki/Piet_Mondrian). El código crea aleatoriamente rectángulos de diferentes colores y tamaños para asemejarse al estilo de dicho artista.

<ins>Documentación utilizada:</ins>

- https://docs.python.org/3/library/random.html


# Tarea 3: Resolver una de las tareas anteriores usando funciones de dibujo de OpenCV <a name="Tarea-3"></a>

## <ins>Tarea seleccionada:</ins> Imagen al estilo Mondrian <a name="Tarea-3:-Tarea-seleccionada"></a>

Esta tarea genera una obra inspirada en el artista Piet Mondrian. Utilizando las funciones de dibujo proporcionadas por la librería *OpenCV*, se crea un lienzo, el cual se divide en rectángulos aleatorios con colores variados y se añade un borde negro al mismo.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/4.x/dc/da5/tutorial_py_drawing_functions.html

# Tarea 4: Modificar planos de la imagen <a name="Tarea-4:-Modificar-planos-de-la-imagen"></a>

Esta tarea demuestra cómo manipular los planos de una imagen recortando y rotando una porción de la misma. Adicionalmente, invierte los colores de una imagen.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/3.4/d2/de8/group__core__array.html

- https://docs.opencv.org/3.4/d3/df2/tutorial_py_basic_ops.html

- https://docs.opencv.org/3.4/da/d54/group__imgproc__transform.html

- https://omes-va.com/operadores-bitwise/

# Tarea 5: Resaltar los píxeles más brillantes y oscuros <a name="Tarea-5:-Resaltar-pixeles"></a>

Aquí encontrarás el código que identifica y resalta los píxeles más brillantes y más oscuros de una imagen. Las posiciones de estos píxeles se visualizan.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/4.x/d6/d6e/group__imgproc__draw.html#gaf10604b069374903dbd0f0488cb43670

- https://numpy.org/doc/stable/reference/generated/numpy.argmin.html

# Tarea 6: Propuesta de Pop Art usando una Cámara Web o Entrada de Video <a name="Tarea-6:-Propuesta-de-Pop-Art"></a>

## Invertir los Colores del Flujo de la Cámara <a name="Tarea-6:-Invertir-los-colores"></a>

En esta tarea, encontrarás el código que invierte los colores de una transmisión de cámara en tiempo real, creando un efecto visual interesante.

<ins>Documentación utilizada:</ins>

- https://omes-va.com/operadores-bitwise/

## Gradiente Interactivo en la Cámara <a name="Tarea-6:-Gradiente-Interactivo"></a>
Esta tarea implica una transmisión de cámara interactiva donde el movimiento del ratón del usuario controla un efecto de gradiente aplicado a la transmisión de video. El código utiliza OpenCV para lograr este efecto.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/3.4/d5/dc4/tutorial_adding_images.html

# Tarea Extra: Resaltar Píxeles Oscuros y Brillantes <a name="Tarea-Extra:-Resaltar-pixeles"></a>

Esta tarea consiste en capturar fotogramas de video de una transmisión de cámara y identificar los píxeles más oscuros y más brillantes en cada fotograma. Resalta el píxel más oscuro y el más brillante tal como se hizo en la Tarea 5.

# ⚙️ Guía de Instalación <a name="Guia-de-Instalacion"></a>

La guía presentada aquí es una modificación de la guía de instalación original creada por [otsedom](https://github.com/otsedom/otsedom.github.io/tree/main/VC/P1).

Esta sección detalla los pasos necesarios para configurar el entorno de desarrollo para la práctica.

# Configuración del Entorno de Desarrollo <a name="Configuracion-Entorno-Desarrollo"></a>

Anaconda te permite crear diferentes entornos, cada uno con sus propios paquetes y versiones específicas. También puedes cambiar fácilmente entre entornos al trabajar con Visual Studio Code. Para ejecutar los notebooks proporcionados en tu computadora después de instalar Anaconda y Visual Studio Code, sigue los siguientes pasos:

1. Inicia Visual Studio Code.

2. Instala la extensión de Python para Visual Studio Code. La puedes encontrar en el [Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

3. Abre el Anaconda Prompt.

4. Crea un entorno con la configuración deseada. Para crear un entorno que pueda ejecutar los notebooks de esta práctica con una versión reciente de Python (por ejemplo, 3.11.5), como en el siguiente comando:

```bash
    conda create --name NOMBRE_ENTORNO python=3.11.5
```

5. Activa el entorno e instala un par de paquetes adicionales:

```bash
    conda activate NOMBRE_ENTORNO
    pip install opencv-python
    pip install matplotlib
```

Una vez que el entorno esté creado y activado:

1. Ejecuta el IDE Visual Studio Code y Anaconda Prompt.

2. En Visual Studio Code, abre el archivo de cada una de las tareas con extensión '.ipynb'

3. En Visual Studio Code, abre la Paleta de Comandos usando la combinación `Ctrl+Shift+P` en Windows/Linux o `⌘+Shift+P` en Mac.

4. Selecciona el entorno recién creado escribiendo `Python: Select Interpreter` y eligiendo el entorno previamente creado.

    * En algunas máquinas, al ejecutar el comando anterior mencionado, puedes encontrarte con un error `interpreter not found` Puedes resolver esto seleccionando el modo "Trust" en lugar de "Restricted" en la esquina inferior izquierda del IDE.
    
    * Asegúrate de haber seleccionado el entorno correcto en la esquina superior derecha de Visual Studio Code.

Si encuentras errores, esto podría deberse a que necesitas instalar elementos necesarios para el uso de notebooks instalando "ipykernel." Esto se puede solucionar ejecutando el siguiente comando, no desde el entorno creado, sino desde el entorno base:

```bash
conda install -n NOMBRE_ENTORNO ipykernel --update-deps --force-reinstall
```

Una vez que llegues a este punto, deberías poder ejecutar el notebook para esta primera práctica.

# Comandos básicos de Anaconda <a name="Comandos-basicos-Anaconda"></a>

Durante el proceso de creación de entornos, es posible que encuentres errores o necesites eliminar y recrear un entorno o listar los entornos existentes. Aquí tienes un breve resumen de los comandos más comunes:
- Listar los entornos existentes:

```bash
conda info --envs
```
- Eliminar un entorno (reemplaza "NOMBRE_ENTORNO" con el nombre de tu entorno):

```bash
conda remove --name NOMBRE_ENTORNO --all
```

- Generar un archivo de texto con los elementos presentes en el entorno activado:

```bash
conda list --explicit > spec-file.txt
```

# 👨🏻‍💻 Colaboradores <a name="Colaboradores"></a>

- [Brian Suárez Santiago](https://github.com/BrianSuarezSantiago)

# ⚠️ Disclaimer <a name="Disclaimer"></a>

Los archivos recopilados en este repositorio son una modificación de los archivos originales creados por [otsedom](https://github.com/otsedom/otsedom.github.io/tree/main/VC).

Este repositorio se desarrolla exclusivamente con fines educativos como parte de un curso universitario.

<hr>
<p align="center">
Made with ♥️ in Spain
</p>