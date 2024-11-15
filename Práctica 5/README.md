# Cuarta Tarea

Este repositorio contiene ejercicios prácticos y código relacionado con visión por computadora. Cada tarea está acompañada de una descripción, implementación de código y documentación.

**Nota: Este proyecto se desarrolla únicamente para un proyecto universitario.**

## Tabla de Contenidos
- [Cuarta Tarea](#cuarta-tarea)
  - [Tabla de Contenidos](#tabla-de-contenidos)
  - [Paquetes Utilizados](#paquetes-utilizados)
  - [Paquetes Requeridos](#paquetes-requeridos)
  - [Tarea: Superposición de Características Faciales en Tiempo Real](#tarea-superposición-de-características-faciales-en-tiempo-real)
    - [Modos de Aumento de Accesorios](#modos-de-aumento-de-accesorios)
  - [Colaboradores](#colaboradores)
  - [Descargo de Responsabilidad](#descargo-de-responsabilidad)

## Paquetes Utilizados
Para ejecutar el código en los notebooks de Jupyter, asegúrate de tener instalados los siguientes paquetes:
- OpenCV (`cv2`)
- NumPy (`numpy`)
- Tkinter (`tkinter`)
- math (`math`)
- os (`os`)
- numpy (`numpy`)
- time (`time`)
- dlib (`dlib`)

```
pip install numpy opencv-python dlib
```

## Paquetes Requeridos
Para asegurar el correcto funcionamiento del código, necesitas instalar los siguientes paquetes:

- Retina-Face: un paquete de detección de rostros que proporciona resultados precisos.
   ```shell
   pip install retina-face
IPykernel (Anaconda): solo si encuentras el error 'paquete ipykernel requerido':
conda install -c anaconda ipykernel
DeepFace: utilizado para tareas de reconocimiento facial basadas en aprendizaje profundo.
pip install deepface
Imutils: proporciona funciones utilitarias para trabajar con OpenCV.
pip install --upgrade imutils
CMake: requerido para compilar algunos paquetes, como dlib.
pip install cmake
Dlib (Conda Forge): una dependencia para algunas tareas relacionadas con rostros y requiere CMake para su instalación.
conda install -c conda-forge dlib
Dlib (PyPI): una biblioteca en C++ con bindings para Python utilizada para varias tareas de visión por computadora.
pip install dlib
MTCNN: un paquete de detección de rostros que se puede usar junto con otros métodos.
pip install MTCNN
TensorFlow es un framework de aprendizaje profundo que puede ser requerido por algunos modelos y tareas de reconocimiento facial.
pip install tensorflow
Asegúrate de instalar estos paquetes en tu entorno para asegurar el correcto funcionamiento del código proporcionado. También se proporcionan las razones para instalar cada paquete para mayor claridad.

Nota: Si los archivos .dat no funcionan, puedes descargarlos desde este enlace: http://dlib.net/files/

Tarea: Superposición de Características Faciales en Tiempo Real

Esta tarea implica crear un prototipo de código que utilice datos faciales sin restricciones temáticas. Detectores avanzados proporcionan información sobre componentes faciales, abriendo oportunidades para diversas aplicaciones, incluidos filtros creativos. La solución es un código que ofrece superposiciones de características faciales en tiempo real utilizando entrada de video en vivo. Este prototipo integra sin problemas las bibliotecas OpenCV, Tkinter y NumPy para lograr la tarea. Los usuarios pueden experimentar con superposiciones faciales de una manera creativa e interactiva, eligiendo entre varios modos para una experiencia atractiva. Documentación utilizada:

https://github.com/italojs/facial-landmarks-recognition/tree/master
https://python.hotexamples.com/examples/retinaface/RetinaFace/build_model/python-retinaface-build_model-method-examples.html 

Modos de Aumento de Accesorios

Modos disponibles para aumentar accesorios faciales en tiempo real:

Sombreros: Este modo permite a los usuarios probar diferentes sombreros, ajustando su posición y tamaño según el rostro detectado.
Gafas: Los usuarios pueden experimentar con varios estilos de gafas, asegurando un ajuste adecuado al rostro.
Labios: Experimenta con diferentes colores y formas de labios, mejorando la apariencia facial.
Bigotes: Agrega instantáneamente bigotes en varios estilos y tamaños para ver cómo complementan tu rostro.
Barbas: Explora diferentes estilos de barba, ajustando su posición y tamaño según sea necesario.
Descargo de Responsabilidad

Los archivos presentados aquí son una modificación de los archivos originales creados por otsedom.

Estas tareas se desarrollan exclusivamente con fines educativos como parte de un curso universitario.