# Análisis de texto con Python

En este módulo del [Diplomado en Ciencia de Datos UC](https://datascience.uc.cl/) nos aproximaremos al análisis de textos usando Python. Abordaremos algunas técnicas que se enmarcan en lo que usualmente se denomina _Minería de texto_ y otras propias del _Procesamiento del Lenguaje Natural_. Existe una sección paralela en la que abordamos los mismo contenidos, [pero usando R](https://github.com/rivaquiroga/analisis-de-textos-r-2023).

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

También es necesario instalar Poppler:

```
!apt-get install poppler-utils
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

Hacia el final de la clase, discutiremos algunas nociones vinculadas al preprocesamiento de textos. Para esa parte de la sesión será necesario tener instalado lo siguiente:

```
!pip install nltk
```

### Tercera sesión

Para las actividades de la tercera sesión necesitarás tener instalada la librería spaCy y descargado el modelo para español. También utilizaremos algunas funciones de scikit-learn.

```
!pip install -U pip setuptools wheel
!pip install -U spacy
!python -m spacy download es_core_news_sm
!pip install -U scikit-learn
```

## Actividades 

Durante las tres sesiones del módulo realizaremos una serie de actividades para poner en práctica lo aprendido. Iremos escribiendo el **código "en vivo"** en la clase, por lo que el contenido de los archivos con código se irá actualizando a medida que escribamos en ellos. Si bien las actividades de la sección presencial y online son las mismas, es posible que avancemos a un ritmo distinto o que el código difiera un poco producto de cómo se da la discusión en clases. 

🖥️ [materiales sección en línea](https://github.com/rivaquiroga/analisis-de-texto-python-2023/blob/main/actividades-en-linea.md)

:office: [materiales sección presencial](https://github.com/rivaquiroga/analisis-de-texto-python-2023/blob/main/actividades-presencial.md)



## Recursos adicionales

### Documentación librerías utilizadas

- [re](https://docs.python.org/es/3/library/re.html): la documentación está parcialmente traducida al español.
- [nltk](https://www.nltk.org/book/)
- [spacy](https://spacy.io/)
- [scikit-learn](https://scikit-learn.org/stable/index.html)
- [pdf2image](https://pdf2image.readthedocs.io/en/latest/index.html)
  
### Sobre expresiones regulares

- [regex101](https://regex101.com/): un sitio web para probar nuestras expresiones regulares
- [Hoja de referencia de la sintaxis de expresiones regulares](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_expressions/Cheatsheet)

### Instalar tesseract en tu máquina personal

Si trabajas en tu computador, puedes revisar la forma de instalación que corresponda a tu sistema operativo [en la documentación de tesseract](https://tesseract-ocr.github.io/tessdoc/Installation.html). 

**Personas que usan Windows**: pueden revisar [estas indicaciones en español para instalar tesseract](https://ucd-dnp.github.io/ConTexto/versiones/master/instalacion/instalacion_popple_teseract_windows.html). 

### Instalar Poppler
Las librerías para trabajar con archivos PDF requieren tener instalada una herramienta llamada Poppler. Si al tratar de usar pdf2image o tesseract te aparece un error relativo a Poppler, significa que tienes que instalarlo. Puedes encontrar indicaciones sonre cómo hacerlo [en la documentación de pdf2image](https://pdf2image.readthedocs.io/en/latest/installation.html#installing-poppler). 
Ojo que Poppler requiere tener permisos de administración del dispositivo para su instalación, por lo que si estás trabajando en el computador de tu institución puede que no sea posible instalarlo directamente. 

### Sobre Topic Modelling

- [Un artículo](http://www.cs.columbia.edu/~blei/papers/Blei2012.pdf) que sirve para entender los algoritmos que hacen modelación de tópicos.
- Otra librería que vale la pena explorar: [Gensim](https://radimrehurek.com/gensim/).

