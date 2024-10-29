# Práctica 3

El presente repositorio contiene ejercicios prácticos y código relacionado con la asignatura 40982 - Visión por Computador. Cada una de las tareas está acompañada de una descripción de la implementación del código y documentación relevante al respecto.


# 📖 Tabla de Contenidos
  - [Paquetes utilizados](#paquetes-utilizados)
  - [Tarea 1: Detección de monedas y coincidencia de radios en imágenes](#task-1)
  - [Tarea 2: Clasificación y análisis basado en contornos](#task-2)
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
- Scikit-learn
- Seaborn

Asegúrate de disponer instalado los paquetes anteriormente listados, para ello, ejecuta el siguiente comando:

```bash
pip install opencv-python numpy matplotlib scikit-learn seaborn
```

# Tarea 1: Detección de monedas y coincidencia de radios en imágenes <a name="task-1"></a>

Esta tarea consiste en capturar una o más imágenes que contengan monedas tanto superpuestas como no, así como, algunos objetos que no sean monedas estrictamente. El objetivo principal es procesar e identificar las imágenes para detectar y dibujar círculos con radios reales que correspondan a las monedas. El proceso de identificación se inicia haciendo clic en una de las monedas de la imagen, tras lo cual el sistema se encarga de calcular el valor de dicha moneda en función de su radio. Asimismo, el código proporciona información sobre el conteo total de monedas presentes en la imagen y obtiene el valor monetario combinado de todas las monedas presentes en la misma. 

## Implementación:

En esta tarea, se ha desarrollado un contador de monedas de euro a partir de una imagen de monedas dispersas inicalmente provista, utilizando una moneda de 1 euro como referencia comparativa. La selección de esta moneda se realiza mediante un clic izquierdo sobre la misma.

A partir de la imagen original, se detectan los contornos principales utilizando el detector de bordes Canny, para lo cual se proporciona una imagen en escala de grises con un desenfoque Gaussiano como entrada.

![Coins Image With Canny Filter](./Assets/Canny%20Filter.png)

Posteriormente, se aplica el umbral de Otsu, del cual se resta la imagen obtenida con Canny para destacar de manera marcada y diferenciada cada uno de los bordes.

![OTSU Image minus Canny Edges](./Assets/Coins%20Difference.png)

Finalmente, se procesa dicha imagen para identificar los bordes circulares externos de las monedas.

![Coin Circle Detection Image](./Assets/Coins%20Contours.png)

Una vez detectados los posibles contornos existentes, se procede al conteo del dinero. Al hacer clic sobre la moneda de 1 euro, se calcula un factor de escala dividiendo su diámetro real entre su diámetro en la imagen; este factor se usará en los sucesivos pasos.

Previamente, se han generado dos diccionarios: uno para los diámetros reales de cada tipo de moneda y otro para el total de dinero contado.

Se continua detectando los contornos activos y verificando si corresponden a una moneda con la función `isCoin()`, la cual comprueba si los píxeles correspondientes en la imagen procesada son blancos. En caso afirmativo, se multiplica el diámetro de dicha moneda en la imagen por el factor de escala para obtener su diámetro real equivalente. Seguidamente, se agrupa dentro del intervalo correspondiente, de acuerdo con el umbral de tolerancia de diámetros de las monedas. Esto permite añadir una unidad de esa moneda al contador total.

El proceso de conteo continúa hasta que no queden más contornos, y se calcula el valor total sumando la cantidad de cada tipo de moneda multiplicada por su valor, mostrando finalmente los resultados.

<ins>Documentación utilizada:</ins>

- https://docs.opencv.org/4.x/dd/d49/tutorial_py_contour_features.html

- https://docs.opencv.org/4.x/d1/d32/tutorial_py_contour_properties.html

- https://stackoverflow.com/questions/268272/getting-key-with-maximum-value-in-dictionary 

- https://docs.opencv.org/4.x/da/d53/tutorial_py_houghcircles.html

- https://acodigo.blogspot.com/2017/09/deteccion-de-lineas-y-circulos-usando.html

- https://dev.to/tinazhouhui/coin-amount-calculation-discovering-opencv-with-python-52gn

## Problemas detectados

El conteo de monedas no es completamente preciso. El error radica principalmente en la confusión entre las monedas de 50 céntimos y las de 2 euros, así como con las de 1 euro.

![Coin Detection Result](./Assets/Coins%20Result.png)

# Tarea 2: Clasificación y análisis basado en contornos <a name="task-2"></a>

Esta tarea consiste en determinar patrones geométricos para tres clases distintas de imágenes de microplásticos y evaluar la precisión de su clasificación utilizando para ello matrices de confusión. El objetivo radica en analizar las características geométricas de las imágenes disponibles en cada clase y evaluar qué tan bien se pueden distinguir entre sí. Las métricas se utilizan para medir la eficacia de un clasificador.

*¿Qué es una matriz de confusión?*

Una matriz de confusión es una herramienta que permite la visualización del desempeño de un algoritmo que se emplea en múltiples escenarios como los modelos de inteligencia artificial o el aprendizaje supervisado. En esta práctica se emplea para visualizar el desempeño de un clasificador de las distintas clases consideradas. Específicamente, relaciona las etiquetas reales de las muestras anotadas con las predicciones realizadas por el clasificador. El resultado ideal aspira a obtener una matriz lo más diagonal posible.

## Extracción de características

La extracción de las características se realiza de la siguiente manera:

- Para cada imagen de referencia se extraen los contornos externos de los elementos.

- Para cada uno de los contornos se calcula:
    * Relación del cuadrado del perímetro con el área.
    * Relación del área con el contenedor.
    * Relación del ancho y alto del contenedor.
    * Relación entre los ejes de la elipse ajustada.
    * Relación de aspecto del contenedor.
    * Extensión como la relación entre el área del contorno y el área del rectángulo delimitador.
    * Solidez como la relación entre el área del contorno y el "casco" (hull)
    * Relación entre el perímetro y área para determinar lo circular que es un contorno (medida de "circularidad")
    * Color o intensidad promedio de la zona del contorno.

- Para simplificar, para cada una de las clase de microplásticos se computa un vector de características cuyos valores será la media de los calculados para cada uno de los contornos de referencia.

## Problemas detectados

- <ins>Detección incompleta de formas:</ins> El código no es capaz de detectar todas las formas de manera completamente precisa. La detección de contornos puede verse afectada por múltiples factores, como la calidad de la imagen, la iluminación y las características específicas de cada uno de los objetos presentes en la imagen.

- <ins>Ambigüedad en la clasificación:</ins> Aunque el código intenta clasificar los contornos como fragmentos, bolitas o alquitrán en función de determinados criterios, dichos criterios pueden no ser suficientes como para proporcionar una clasificación definitiva, exacta y precisa. De esta manera, los objetos con tamaños o formas similares son clasificados incorrectamente.

## Conclusiones

Los resultados obtenidos presentan una clasificación que dista de ser perfecta. Este hecho no es sorprendente, dado que la clasificación de un tipo de objeto se ha realizado reduciendo una medida geométrica a un valor promedio, lo cual genera inconvenientes, particularmente en el caso de fragmentos, los cuales presentan una amplia variedad de formas y colores.

Es importante destacar que el código ha sido desarrollado con un enfoque altamente abstracto y con el menor grado de intervención manual posible, dadas las características del problema. Es por ello, que considerando el tipo de implementación llevado a cabo los resultados obtenidos son satisfactorios.

Una forma de mejorar los resultados, al menos desde un enfoque empírico, ha sido la incorporación de características adicionales. Un avance significativo se obtuvo al añadir el análisis del color, lo que, aunque incrementa notablemente el tiempo de ejecución del programa, mejoró considerablemente las matrices de confusión en la clasificación del alquitrán y los fragmentos. Otra opción existente sería ajustar los pesos de las características, por ejemplo, asignando una mayor importancia al color, duplicando su peso relativo.

<ins>Documentación utilizada:</ins>

- https://stackoverflow.com/questions/72118665/particle-detection-with-python-opencv

- https://learnopencv.com/blob-detection-using-opencv-python-c/

![Fragments Contour Highlighting Result](./Assets/Fragments%20result%20of%20detection.jpg)

![Fragments Confusion Matrix Result](./Assets/Fragments%20confusion%20matrix.png)

![Pellets Contour Highlighting Result](./Assets/Pellets%20result%20of%20detection.jpg)

![Fragments Confusion Matrix Result](./Assets/Pellets%20confusion%20matrix.png)

![Tar Contour Highlighting Result](./Assets/Tar%20result%20of%20detection.jpg)

![Fragments Confusion Matrix Result](./Assets/Tar%20confusion%20matrix.png)

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

# 👨🏻‍💻 Colaboradores <a name="colaboradores"></a>

- [Brian Suárez Santiago](https://github.com/BrianSuarezSantiago)

# ⚠️ Disclaimer <a name="disclaimer"></a>

Los archivos recopilados en este repositorio son una modificación de los archivos originales creados por [otsedom.](https://github.com/otsedom/otsedom.github.io/tree/main/VC)

Este repositorio se desarrolla exclusivamente con fines educativos como parte de un curso universitario.

<hr>
<p align="center">
Made with ♥️ in Spain
</p>