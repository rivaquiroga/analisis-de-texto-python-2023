## Materiales actividades sección en línea

### Ejercicio 1: el mágico mundo de las expresiones regulares

:page_facing_up: [Código escrito en clases](https://www.dropbox.com/scl/fi/78qvwfz42zrn58v3r1ych/01_regex.py?rlkey=8omszxararfnuoqjgcsuop11v&dl=0)

:card_file_box: [Datos registro nombres](https://www.dropbox.com/scl/fi/umg8lnwj89zsncgv0sdos/nombres.csv?rlkey=f8e5oy4o54hk4f5v3y1lkzncn&dl=0)


#### Desafío para practicar lo visto en la sesión 1

A continuación encontrarás dos archivos CSV (separados por `;`) en que la forma en que se escribieron los nombres de las personas no coinciden: "Nombre Apellido" en uno; "Apellido, Nombre" en el otro. 

:card_file_box: [Datos matemáticas](https://www.dropbox.com/scl/fi/0r0m3ttp5cagybvk5quhu/matematicas.csv?rlkey=5xddjevkgl0zd2dc7pzxpbweo&dl=0)

:card_file_box: [Datos lenguaje](https://www.dropbox.com/scl/fi/zoh7n0mfhh51539rtmpl6/lenguaje.csv?rlkey=ah9tekr76iwiymm11vo5kdknm&dl=0)

Si utilizamos `pd.merge()` para unir ambos dataframes, pandas no podrá hacer que coincidan las filas (es decir, que cada persona esté en una sola fila y tenga una columna para el puntaje de matemáticas y otra para el puntaje de lenguaje) porque, tal como están los datos, no tiene cómo saber que las dos formas de escribir el nombre corresponden a la misma persona. Para resolver el problema es necesario utilizar una expresión regular que te permita capturar grupos dentro de una cadena de caracteres.

Hay dos aproximaciones para resolver el problema:
 - Separar apellido y nombre en columnas distintas en ambos dataframes y luego hacer el merge con esas dos columnas como elemento común.
 - Modificar la columna "estudiante" en uno de los dataframes para que el formato coincida con la forma en que se escribieron los nombres en el otro.

:sparkles: [Solución]() (¡pronto!)


