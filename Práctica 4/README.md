# Práctica 4

El presente repositorio contiene ejercicios prácticos y código relacionado con la asignatura 40982 - Visión por Computador. Cada una de las tareas está acompañada de una descripción de la implementación del código y documentación relevante al respecto.


# 📖 Tabla de Contenidos
  - [Paquetes utilizados](#paquetes-utilizados)
  - [Tarea: Reconocimiento de matrículas](#task)
  - [Funcionamiento](#funcionamiento)
  - [Configuracion inicial](#configuracion-inicial)
  - [Dataset](#dataset)
  - [Guía de instalación](#guia-de-instalacion)
  - [Configuración del entorno de desarrollo](#configuracion-entorno-desarrollo)
  - [Comandos básicos de Anaconda](#comandos-basicos-anaconda)
  - [Errores y problemas comunes](#errores-problemas-comunes)
  - [Colaboradores](#colaboradores)
  - [Disclaimer](#disclaimer)

# 📦 Paquetes utilizados <a name="paquetes-utilizados"></a>

Para ejecutar el código incluido en los diferentes notebooks de Jupyter, es necesario tener instaladas las siguientes librerías:

- Ultralytics
- Lap o Lapx

Asegúrate de disponer instalado los paquetes anteriormente listados, para ello, ejecuta el siguiente comando:

```bash
pip install ultralytics lap
```

Si el comando anteriormente produce errores, se puede utilizar conda para la instalación del mismo. Para ello, ejecuta el siguiente comando:

 ```bash
conda install -c conda-forge ultralytics
```

# 🚘 Tarea: Reconocimiento de matrículas <a name="task"></a>

Este código en Python permite realizar la detección y seguimiento de vehículos y placas de matrícula en un video mediante el uso de modelos de inteligencia artificial de YOLO y la biblioteca de OCR Tesseract.

## Funcionamiento <a name="funcionamiento"></a>

Este script procesa cada cuadro de un video para detectar vehículos y sus placas de matrícula. Utiliza modelos de YOLO para identificar objetos y Tesseract OCR para extraer texto de las placas detectadas. Los resultados pueden visualizarse en pantalla o guardarse en un archivo de video.

### Configuración inicial <a name="configuracion-inicial"></a>

- Define la ruta de Tesseract para reconocimiento óptico de caracteres (OCR).

- Carga dos modelos de YOLO: uno para detectar vehículos y otro para detectar placas de matrícula.

- Configura la fuente de video (archivo) y ajusta los parámetros de salida para guardar el video procesado si display es False.

- Itera sobre cada cuadro del video.

- Realiza seguimiento de objetos con persistencia de ID, centrado en clases específicas como "car" o "truck".

- Extrae cada cuadro de los objetos detectados y aplica el modelo de detección de placas de matrícula dentro de estos recortes.

- Utiliza Tesseract para extraer el texto de las placas detectadas y muestra el texto en el cuadro de video.


- Si display es True, muestra el video en pantalla; si no, guarda el video procesado en un archivo.

- Dibuja un rectángulo y muestra la clase e ID de seguimiento sobre cada objeto detectado.

- Libera recursos, ya sea cerrando la ventana de visualización o liberando el archivo de video de salida.

# 📚 Dataset

Los conjuntos de datos empleados para el desarrollo del modelo se han obtenido de las siguientes fuentes:

- https://www.kaggle.com/datasets/fareselmenshawii/license-plate-dataset

- https://www.kaggle.com/datasets/fareselmenshawii/large-license-plate-dataset

- https://github.com/Asikpalysik/Automatic-License-Plate-Detection/tree/main/images

- https://alumnosulpgc-my.sharepoint.com/personal/mcastrillon_iusiani_ulpgc_es/_layouts/15/stream.aspx?id=%2Fpersonal%2Fmcastrillon%5Fiusiani%5Fulpgc%5Fes%2FDocuments%2FRecordings%2FC0142%2EMP4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2Eb356b2e5%2De130%2D4de2%2D933b%2D0de09f9cbe7e


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

# 👨🏻‍💻 Colaboradores <a name="colaboradores"></a>

- [Brian Suárez Santiago](https://github.com/BrianSuarezSantiago)

# ⚠️ Disclaimer <a name="disclaimer"></a>

Los archivos recopilados en este repositorio son una modificación de los archivos originales creados por [otsedom.](https://github.com/otsedom/otsedom.github.io/tree/main/VC)

Este repositorio se desarrolla exclusivamente con fines educativos como parte de un curso universitario.

<hr>
<p align="center">
Made with ♥️ in Spain
</p>