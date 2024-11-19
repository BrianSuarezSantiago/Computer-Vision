# Práctica 5

El presente repositorio contiene ejercicios prácticos y código relacionado con la asignatura 40982 - Visión por Computador. Cada una de las tareas está acompañada de una descripción de la implementación del código y documentación relevante al respecto.


# 📖 Tabla de Contenidos
  - [Paquetes utilizados](#paquetes-utilizados)
  - [Paquetes necesarios](#paquetes-necesarios)
  - [Tarea: Superposición de características faciales en tiempo real](#task)
  - [Guía de instalación](#guia-de-instalacion)
  - [Configuración del entorno de desarrollo](#configuracion-entorno-desarrollo)
  - [Comandos básicos de Anaconda](#comandos-basicos-anaconda)
  - [Errores y problemas comunes](#errores-problemas-comunes)
  - [Vídeos de muestra](#videos-de-muestra)
  - [Colaboradores](#colaboradores)
  - [Disclaimer](#disclaimer)

# 📦 Paquetes utilizados <a name="paquetes-utilizados"></a>

Para ejecutar el código incluido en los diferentes notebooks de Jupyter, es necesario tener instaladas las siguientes librerías:

- OpenCV
- NumPy
- Tkinter
- math
- os
- numpy
- time
- dlib

Asegúrate de disponer instalado los paquetes anteriormente listados, para ello, ejecuta el siguiente comando:

```bash
pip install opencv-python dlib
```

Si el comando anteriormente produce errores, se puede utilizar conda para la instalación del mismo. Para ello, ejecuta el siguiente comando:

 ```bash
conda install -c conda-forge dlib
```

# 📦 Paquetes requeridos <a name="paquetes-necesarios"></a>

Para asegurar el correcto funcionamiento del código, se necesita instalar los siguientes paquetes:

- Retina-Face: un paquete de detección de rostros que proporciona resultados precisos.
```bash
pip install retina-face
```
- IPykernel (Anaconda): solo si encuentras el error 'paquete ipykernel requerido':
```bash
conda install -c anaconda ipykernel
```
- DeepFace: utilizado para tareas de reconocimiento facial basadas en aprendizaje profundo.
```bash
pip install deepface
```
- Imutils: proporciona funciones utilitarias para trabajar con OpenCV.
```bash
pip install --upgrade imutils
```
- CMake: requerido para compilar algunos paquetes, como dlib.
```bash
pip install cmake
```
- Dlib (Conda Forge): una dependencia para algunas tareas relacionadas con rostros y requiere CMake para su instalación.
```bash
conda install -c conda-forge dlib
```
- Dlib (PyPI): una biblioteca en C++ con bindings para Python utilizada para varias tareas de visión por computadora.
```bash
pip install dlib
```
- MTCNN: un paquete de detección de rostros que se puede usar junto con otros métodos.
```bash
pip install MTCNN
```
- TensorFlow es un framework de aprendizaje profundo que puede ser requerido por algunos modelos y tareas de reconocimiento facial.
```bash
pip install tensorflow
```

Asegúrate de instalar estos paquetes en tu entorno para asegurar el correcto funcionamiento del código proporcionado. También se proporcionan las razones para instalar cada paquete para mayor claridad.

# 🎭 Tarea: Superposición de características faciales en tiempo real <a name="task"></a>

Esta tarea implica crear un prototipo de código que utilice datos faciales sin restricciones temáticas. Detectores avanzados proporcionan información sobre componentes faciales, abriendo oportunidades para diversas aplicaciones, incluidos filtros creativos. La solución es un código que ofrece superposiciones de características faciales en tiempo real utilizando entrada de video en vivo. Este prototipo integra sin problemas las bibliotecas OpenCV, Tkinter y NumPy para lograr la tarea. Los usuarios pueden experimentar con superposiciones faciales de una manera creativa e interactiva, eligiendo entre varios modos para una experiencia atractiva.

<ins>Documentación utilizada:</ins>

- https://github.com/italojs/facial-landmarks-recognition/tree/master
- https://python.hotexamples.com/examples/retinaface/RetinaFace/build_model/python-retinaface-build_model-method-examples.html 

> [!NOTE]
> Si los archivos .dat no funcionan, puedes descargarlos desde [este enlace.](http://dlib.net/files/)

# ⚙️ Guía de instalación <a name="guia-de-instalacion"></a>

La guía presentada aquí es una modificación de la guía de instalación original creada por [otsedom.](https://github.com/otsedom/otsedom.github.io/tree/main/VC/P2)

Esta sección detalla los pasos necesarios para configurar el entorno de desarrollo para la práctica.

# Configuración del entorno de desarrollo <a name="configuracion-entorno-desarrollo"></a>

Anaconda te permite crear diferentes entornos, cada uno con sus propios paquetes y versiones específicas. También puedes cambiar fácilmente entre entornos al trabajar con Visual Studio Code. Para ejecutar los notebooks proporcionados en tu computadora después de instalar Anaconda y Visual Studio Code, sigue los siguientes pasos:

1. Inicia Visual Studio Code.

2. Instala la extensión de Python para Visual Studio Code. La puedes encontrar en el [Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

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

# Errores y problemas comunes <a name="errores-problemas-comunes"></a>

Problemas de varias versiones existentes de Python en mac:

1. Destacar y eliminar todas aquellas versiones *deprecadas* y quedarnos únicamente con la última versión estable. Para ello, verificar todas las versiones instaladas en la siguiente ruta:

```bash
/Library/Frameworks/Python.framework/Versions
```

2. Si la instalación de *ultralytics* falla, probar a instalar previamente la librería *setuptools*. Para ello, ejecuta el siguiente comando:

```bash
pip install setuptools
```

3. Si estás en Mac o sin GPU, puedes omitir el índice de CUDA:

```bash
pip install torch torchvision torchaudio
```

# 📽️ Vídeos de muestra <a name="videos-de-muestra"></a>



# 👨🏻‍💻 Colaboradores <a name="colaboradores"></a>

- [Brian Suárez Santiago](https://github.com/BrianSuarezSantiago)

# ⚠️ Disclaimer <a name="disclaimer"></a>

Los archivos recopilados en este repositorio son una modificación de los archivos originales creados por [otsedom.](https://github.com/otsedom/otsedom.github.io/tree/main/VC)

Este repositorio se desarrolla exclusivamente con fines educativos como parte de un curso universitario.

<hr>
<p align="center">
Made with ♥️ in Spain
</p>
