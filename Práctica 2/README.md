# Práctica 2

El presente repositorio contiene ejercicios prácticos y código relacionado con la asignatura 40982 - Visión por Computador. Cada una de las tareas está acompañada de una descripción de la implementación del código y documentación relevante al respecto.


# 📖 Tabla de Contenidos
  - [Paquetes utilizados](#paquetes-utilizados)
  - [Tarea 1: Conteo de píxeles blancos y detección máxima](#tarea-1)
  - [Tarea 2: Sobel antes y después del ajuste de escala](#tarea-2)
  - [Tarea 2 Extra: Umbralización de la imagen Sobel y resultados de Canny](#tarea-2-extra)
  - [Tarea 3: Exhibición de lo aprendido en estas dos prácticas ante quienes no cursan la asignatura](#tarea-3)
  - [Tarea 4: Resaltado de colores en transmisión de vídeo en tiempo real](#tarea-4)
  - [Guía de instalación](#guia-de-instalacion)
  - [Configuración del entorno de desarrollo](#configuracion-entorno-desarrollo)
  - [Comandos básicos de Anaconda](#comandos-basicos-anaconda)
  - [Colaboradores](#colaboradores)
  - [Disclaimer](#disclaimer)

# 📦 Paquetes utilizados <a name="paquetes-utilizados"></a>

Para ejecutar el código incluido en los diferentes notebooks de Jupyter, es necesario tener instaladas las siguientes librerías:

- OpenCV
- NumPy
- Matplotlib

Asegúrate de disponer instalado los paquetes anteriormente listados, para ello, ejecuta el siguiente comando:

```bash
pip install opencv-python numpy matplotlib
```

# Tarea 1: Conteo de píxeles blancos y detección máxima <a name="tarea-1"></a>

Esta tarea consiste en analizar la distribución de píxeles blancos en una imagen obtenida mediante detección de bordes con el operador *Canny*. Calcula y visualiza el número de píxeles blancos por columna y por fila, destacando aquellos que superan un umbral especificado.

![Task 1 Output](./Assets/Task1.png)

# Tarea 2: Sobel antes y después del ajuste de escala <a name="tarea-2"></a>

Esta tarea tiene como objetivo visualizar los bordes verticales y horizontales en una imagen y su combinación utilizando el operador de Sobel para la detección de bordes.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/4.x/d7/d4d/tutorial_py_thresholding.html

- https://numpy.org/doc/stable/reference/generated/numpy.where.html

- https://www.tutorialspoint.com/opencv/opencv_sobel_operator.htm

![Task 2 Output](./Assets/Task2.png)

# Tarea 2 Extra: Umbralización de la imagen Sobel y resultados de Canny <a name="tarea-2-extra"></a>

Esta tarea explora la detección de bordes, la umbralización y el análisis del conteo de píxeles utilizando tanto el operador de Sobel como las técnicas de detección de bordes de Canny en una imagen de entrada, con énfasis en identificar y visualizar las filas y columnas más destacadas en la imagen.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/4.x/dc/da5/tutorial_py_drawing_functions.html

![Task 2 Extra Output](./Assets/Task2-Extra.png)

# Tarea 3: Exhibición de lo aprendido en estas dos prácticas ante quienes no cursan la asignatura <a name="tarea-3"></a>

Esta tarea propone realizar un demostrador que capture las imágenes de la cámara y ponga en práctica lo aprendido en las dos primeras prácticas de la asignatura ante aquellos quienes no han cursado la asignatura. Para ello, se propone un repertorio de habilidades en el que se muestran los siguientes efectos alternando entre ellas con eventos de ratón o teclado combinando las funciones vistas hasta este momento aplicadas sobre la entrada de la cámara.

**<ins>Efectos disponibles:</ins>**

1. Mostrar imagen original.
2. Convertir a escala de grises.
3. Aplicar Canny (detección de bordes).
4. Umbralización binaria.

![Task 3 Output](./Assets/Task3.png)

# Tarea 4: Resaltado de colores en transmisión de vídeo en tiempo real <a name="tarea-4"></a>

Esta tarea consiste en crear un programa que permita a los usuarios resaltar de manera interactiva objetos de colores específicos en una transmisión de cámara web en vivo a través de una función de movimiento que crea un efecto de desenfoque cuando se detecta movimiento, simulando una experiencia fantasmagórica. Los usuarios pueden cambiar entre diferentes colores presionando las teclas correspondientes. Cuando se selecciona un color, el programa detecta objetos de ese color en tiempo real utilizando la cámara del ordenador y los resalta en la transmisión de vídeo.

<ins>Documentación utilizada:</ins>

- https://handmap.github.io/hsv-vs-rgb/

- https://www.geeksforgeeks.org/multiple-color-detection-in-real-time-using-python-opencv/

- https://omes-va.com/operadores-bitwise/

- https://www.geeksforgeeks.org/python-opencv-cv2-puttext-method/

**<ins>Resultados de capturas realizadas</ins>**

- Azul:<br>
  * Cola de peluche<br><img src="./Assets/Blue.png" alt="Teddy Tail" width="300px" height="200px"/><br>

- Marrón:<br>
  * Postre<br><img src="./Assets/Brown.png" alt="Brown hair" width="300px" height="200px"/><br>

- Verde:<br>
  * Cuerpo peluche<br><img src="./Assets/Green.png" alt="Teddy Body" width="300px" height="200px"/><br>

- Gris:<br>
  * Camiseta<br><img src="./Assets/Gray.png" alt="T-shirt" width="300px" height="200px"/><br>

- Naranja:<br>
  * Figura<br><img src="./Assets/Orange.png" alt="Figure" width="300px" height="200px"/><br>

- Rojo:<br>
  * Hucha<br><img src="./Assets/Red.png" alt="Figure" width="300px" height="200px"/><br>

- Blanco:<br>
  * Mueble<br><img src="./Assets/White.png" alt="Furniture" width="300px" height="200px"/><br>

- Amarillo:<br>
  * Sombrero y pico de peluche<br><img src="./Assets/Yellow.png" alt="Teddy hat and beak" width="300px" height="200px"/><br>

- Rosa:<br>
  * Gel de baño<br><img src="./Assets/Pink.png" alt="Teddy hat and beak" width="300px" height="200px"/><br>

# ⚙️ Guía de instalación <a name="guia-de-instalacion"></a>

La guía presentada aquí es una modificación de la guía de instalación original creada por [otsedom](https://github.com/otsedom/otsedom.github.io/tree/main/VC/P2).

Esta sección detalla los pasos necesarios para configurar el entorno de desarrollo para la práctica.

# Configuración del entorno de desarrollo <a name="configuracion-entorno-desarrollo"></a>

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

# Comandos básicos de Anaconda <a name="comandos-basicos-anaconda"></a>

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

# 👨🏻‍💻 Colaboradores <a name="colaboradores"></a>

- [Brian Suárez Santiago](https://github.com/BrianSuarezSantiago)

# ⚠️ Disclaimer <a name="disclaimer"></a>

Los archivos recopilados en este repositorio son una modificación de los archivos originales creados por [otsedom](https://github.com/otsedom/otsedom.github.io/tree/main/VC)

Este repositorio se desarrolla exclusivamente con fines educativos como parte de un curso universitario.

<hr>
<p align="center">
Made with ♥️ in Spain
</p>