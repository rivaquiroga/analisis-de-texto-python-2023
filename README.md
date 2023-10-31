# Análisis de texto con Python (sección presencial)

En este módulo del [Diplomado en Ciencia de Datos UC](https://datascience.uc.cl/) nos aproximaremos al análisis de textos usando Python. Abordaremos algunas técnicas que se enmarcan en lo que usualmente se denomina _Minería de texto_ y otras propias del _Procesamiento del Lenguaje Natural_. 

## Preparación

### Primera sesión

Para realizar las actividades planificadas para la primera sesión necesitarás las siguientes librerías: 

```
pip install pandas
```

Si prefieres trabajar en Google Colab, no olvides agregar un signo de exclamación al inicio de cada línea para su instalación, es decir:

```
!pip install pandas
```
Esto le indica a Google Colab que ese no es código de Python, sino código que tiene que ejecutarse en la terminal.

Si trabajas en Visual Studio Code (u otro IDE), es necesario que crees un entorno virtual. Durante la primera sesión mostraremos cómo hacerlo. También puedes revisar [las indicaciones en este documento](https://github.com/rivaquiroga/taller-web-scraping-python-2023/blob/main/crear-entorno-virtual.md).

### Segunda sesión

En la primera parte de la segunda sesión nos enfocaremos en la extracción de texto de archivos PDF y en la conversión de un audio a texto (lo que se conoce como "speech-to-text"). **La sugerencia es trabajar en Google Colab en esta parte de la clase**, ya que se requiere instalar más cosas que solo librerías de Python para hacer que el código funcione. De todos modos, en la sección [Recursos Adicionales](#recursos-adicionales) quedarán indicaciones sobre cómo instalar todo si es que trabajas en tu máquina personal.  

Para el trabajo con PDFs, primero instala tesseract en Google Colab:

```
!sudo apt install tesseract-ocr-spa
```

Esa línea de código instalará el modelo para español (y el para inglés, que queda instalado por defecto). Puedes chequear que está todo en orden ejecutando lo siguiente

```
!tesseract --list-langs
```

Las otras librerías que utilizaremos en esta parte de la sesión son las siguientes:

```
!pip install pytesseract
!pip install pdf2image
!pip install PyPDF2
```

Para convertir un audio a texto, necesitarás instalar lo siguiente:

```
!pip install setuptools-rust
!pip install -U openai-whisper
!sudo apt update && sudo apt install ffmpeg
```

Hacia el final de la clase, nos enfocaremos en el preprocesamiento de texto. Para esa parte de la sesión será necesario tener instalado lo siguiente:

```
!pip install nltk
```

### Tercera sesión

¡Pronto!

## Actividades

Durante las tres sesiones del módulo realizaremos una serie de actividades para poner en práctica lo aprendido. Iremos escribiendo el **código "en vivo"** en la clase, por lo que el contenido de los archivos con código se irá actualizando a medida que escribamos en ellos. 

### Ejercicio 1: el mágico mundo de las expresiones regulares

:page_facing_up: [Código escrito en clases](https://www.dropbox.com/scl/fi/gpyxmbkbm4lgmqyyqjmze/01_regex.py?rlkey=xn891w8808p3pztibi1dqz2ci&dl=0)

:card_file_box: [Datos registro nombres](https://www.dropbox.com/scl/fi/umg8lnwj89zsncgv0sdos/nombres.csv?rlkey=f8e5oy4o54hk4f5v3y1lkzncn&dl=0)

#### Desafío de práctica
A continuación encontrarás dos archivos CSV (separados por `;`) en que la forma en que se escribieron los nombres de las personas no coinciden: "Nombre Apellido" en uno; "Apellido, Nombre" en el otro. 

:card_file_box: [Datos matemáticas](https://www.dropbox.com/scl/fi/0r0m3ttp5cagybvk5quhu/matematicas.csv?rlkey=5xddjevkgl0zd2dc7pzxpbweo&dl=0)

:card_file_box: [Datos lenguaje](https://www.dropbox.com/scl/fi/zoh7n0mfhh51539rtmpl6/lenguaje.csv?rlkey=ah9tekr76iwiymm11vo5kdknm&dl=0)

Si utilizamos `pd.merge()` para unir ambos dataframes, pandas no podrá hacer que coincidan las filas (es decir, que cada persona esté en una sola fila y tenga una columna para el puntaje de matemáticas y otra para el puntaje de lenguaje) porque, tal como están los datos, no tiene cómo saber que las dos formas de escribir el nombre corresponden a la misma persona. Para resolver el problema es necesario utilizar una expresión regular que te permita capturar grupos dentro de una cadena de caracteres.

Hay dos aproximaciones para resolver el problema:
 - Separar apellido y nombre en columnas distintas en ambos dataframes y luego hacer el merge con esas dos columnas como elemento común.
 - Modificar la columna "estudiante" en uno de los dataframes para que el formato coincida con la forma en que se escribieron los nombres en el otro.

:sparkles: [Solución]() (¡pronto!)

### Ejercicio 2: extracción de texto de archivos en formato PDF

:page_facing_up: [Código escrito en clases](https://www.dropbox.com/scl/fi/bo3u2vnodz6kw8dzxvhon/02_extraccion-pdfs.py?rlkey=ticylxleqea09iuz9c8yunmdy&dl=0)

📖 [PDF escaneado](https://www.dropbox.com/scl/fi/yy9894lex6zf6sbyyj2yv/amanda_labarca.pdf?rlkey=03xplf67hh9gh5ffjfizs3h7m&dl=0)

✍️ [PDF nativo](https://www.dropbox.com/scl/fi/kiwtke3zbkel1etcee51h/historia_python.pdf?rlkey=16oiuxjx7eliyn9165u1by9sj&dl=0)


### Ejercicio 3: "speech-to-text"

:page_facing_up: [Código escrito en clases](https://www.dropbox.com/scl/fi/h3un6986hzyxhhk69asfv/03_speech-to-text.py?rlkey=s12h4ysfakpgo8rierc7g8w6d&dl=0)

🎤 [Audio de prueba](https://www.dropbox.com/scl/fi/7so2upmvlyt6vp0xurhp5/audio-de-prueba.m4a?rlkey=3eznie2kjr7tf0xncp6ty900n&dl=0)

### Ejercicio 4: Preprocesamiento de texto
 
:page_facing_up: [Código escrito en clases](https://www.dropbox.com/scl/fi/h71zwf0a67ozkn05buxef/04_preprocesamiento.py?rlkey=dv7ohlzatixyirh1dj23m4bkg&dl=0)

🗣️ [Primer ejemplo](https://www.dropbox.com/scl/fi/1qxof69pzi2pkj5vez030/cuenta-publica-2023.txt?rlkey=9wxuka5pl8lbhqpzw3ksd115i&dl=0)
🔡 [Una lista de stopwords](https://raw.githubusercontent.com/7PartidasDigital/AnaText/master/datos/diccionarios/vacias.txt)

## Recursos adicionales

### Documentación librerías utilizadas

- [re](https://docs.python.org/es/3/library/re.html): la documentación está parcialmente traducida al español.

### Sobre expresiones regulares

- [regex101](https://regex101.com/): un sitio web para probar nuestras expresiones regulares
- [Hoja de referencia de la sintaxis de expresiones regulares](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_expressions/Cheatsheet)

### Instalar tesseract en tu máquina personal

Si trabajas en tu computador, puedes revisar la forma de instalación que corresponda a tu sistema operativo [en la documentación de tesseract](https://tesseract-ocr.github.io/tessdoc/Installation.html). 

**Personas que usan Windows**: pueden revisar [estas indicaciones en español para instalar tanto tesseract como Poppler](https://ucd-dnp.github.io/ConTexto/versiones/master/instalacion/instalacion_popple_teseract_windows.html), una herramienta para renderear PDF que es necesario tener instalada también. Ojo que Poppler requiere tener permisos de administración del dispositivo para su instalación, por lo que si estás trabajando en el computador de tu institución puede que no sea posible instalarlo directamente. 

