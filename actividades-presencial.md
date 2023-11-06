## Materiales actividades sección presencial

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
