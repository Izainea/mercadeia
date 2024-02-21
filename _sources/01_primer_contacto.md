# Análisis de datos con pandas

Usaremos el dataset de kaggle "Marketing Data"
## **Objetivo**

En esta clase aprenderemos a programar un análisis de datos de una tabla. El análisis de datos nos permitirá explorar, visualizar y obtener información sobre el comportamiento de los clientes de una empresa de productos gourmet y sus respuestas a las campañas de marketing.
## **Dataset**
El dataset que usaremos se llama "Marketing Data" y se puede descargar de kaggle en el siguiente enlace: [kagle](https://www.kaggle.com/jackdaoud/marketing-data). El dataset contiene 2240 filas y 28 columnas, cada una de las cuales representa una característica de los clientes o una variable relacionada con el marketing. Las columnas son las siguientes:

|***Característica***|***Descripción***|
| - | - |
|AcceptedCmp1|1 si el cliente aceptó la oferta en la 1ª campaña, 0 de lo contrario|
|AcceptedCmp2|1 si el cliente aceptó la oferta en la 2ª campaña, 0 de lo contrario|
|AcceptedCmp3|1 si el cliente aceptó la oferta en la 3ª campaña, 0 de lo contrario|
|AcceptedCmp4|1 si el cliente aceptó la oferta en la 4ª campaña, 0 de lo contrario|
|AcceptedCmp5|1 si el cliente aceptó la oferta en la 5ª campaña, 0 de lo contrario|
|Response (objetivo)|1 si el cliente aceptó la oferta en la última campaña, 0 de lo contrario|
|Complain|1 si el cliente se quejó en los últimos 2 años|
|DtCustomer|fecha de inscripción del cliente en la empresa|
|Education|nivel de educación del cliente|
|Marital|estado civil del cliente|
|Kidhome|número de niños pequeños en el hogar del cliente|
|Teenhome|número de adolescentes en el hogar del cliente|
|Income|ingreso anual del hogar del cliente|
|MntFishProducts|cantidad gastada en productos de pescado en los últimos 2 años|
|MntMeatProducts|cantidad gastada en productos cárnicos en los últimos 2 años|
|MntFruits|cantidad gastada en frutas en los últimos 2 años|
|MntSweetProducts|cantidad gastada en productos dulces en los últimos 2 años|
|MntWines|cantidad gastada en vinos en los últimos 2 años|
|MntGoldProds|cantidad gastada en productos de oro en los últimos 2 años|
|NumDealsPurchases|número de compras realizadas con descuento|
|NumCatalogPurchases|número de compras realizadas mediante catálogo|
|NumStorePurchases|número de compras realizadas directamente en tiendas|
|NumWebPurchases|número de compras realizadas a través del sitio web de la empresa|
|NumWebVisitsMonth|número de visitas al sitio web de la empresa en el último mes|
|Recency|número de días desde la última compra|

## **Google Colab**

Google Colab es una herramienta online que nos permite ejecutar código de Python en la nube, sin necesidad de instalar nada en nuestro ordenador. Además, podemos acceder a recursos de computación avanzados, como GPUs o TPUs, para procesar grandes cantidades de datos o entrenar modelos de aprendizaje automático. Google Colab también nos permite compartir nuestros notebooks con otros usuarios y colaborar en tiempo real.

Para usar Google Colab, solo necesitamos una cuenta de Google y un navegador web. Podemos acceder a la página principal de Google Colab en <https://colab.research.google.com/> y seguir estos pasos para crear o abrir un notebook:

- Para crear un nuevo notebook, hacemos clic en el botón "Nuevo notebook" en la esquina superior izquierda, o seleccionamos "Archivo" y luego "Nuevo notebook" en el menú superior.
- Para abrir un notebook existente desde Google Drive o Github, usamos las opciones que aparecen en la página principal.

Un notebook es un documento que combina celdas de texto y de código, que se pueden ejecutar de forma interactiva. Las celdas de texto nos permiten explicar lo que hacemos con el código, usando el formato Markdown. Las celdas de código nos permiten escribir y ejecutar instrucciones de Python, usando el entorno de ejecución de Google Colab, que tiene instaladas muchas librerías útiles para el análisis de datos y el aprendizaje automático. Para ejecutar una celda de código, podemos usar el botón de play que aparece al lado de la celda, o presionar las teclas Ctrl+Enter. El resultado de la ejecución se mostrará debajo de la celda.

Las **celdas de texto** son espacios donde podemos escribir texto enriquecido, usando el formato Markdown. El formato Markdown nos permite usar diferentes estilos de letra, como negrita o cursiva, insertar enlaces, imágenes, ecuaciones matemáticas o listas. Para editar una celda de texto, hacemos doble clic sobre ella y usamos la barra de herramientas que aparece encima. Para ver el resultado final, presionamos Shift+Enter o hacemos clic fuera de la celda.

**Un tutorial elemental de cómo funciona Markdown**

Para complementar el texto con formato Markdown, podemos usar celdas de texto en nuestro notebook. El formato Markdown es un lenguaje de marcado ligero que nos permite crear documentos con un aspecto profesional, usando una sintaxis sencilla y fácil de aprender. Algunas de las ventajas de usar Markdown son:

\- Es compatible con HTML, por lo que podemos insertar etiquetas HTML en nuestro texto si queremos usar alguna función que no esté disponible en Markdown.

\- Se puede convertir a otros formatos, como PDF, Word o LaTeX, usando herramientas externas.

\- Es ampliamente usado en plataformas de desarrollo y colaboración, como Github, Stack Overflow o Medium.

A continuación, vamos a ver algunos ejemplos de cómo usar Markdown para dar formato a nuestro texto.

**Encabezados**

Para crear encabezados de diferentes niveles, usamos el símbolo # al principio de la línea, seguido de un espacio y el texto del encabezado. El número de # indica el nivel del encabezado, desde 1 (el más grande) hasta 6 (el más pequeño). Por ejemplo:

\# Este es un encabezado de nivel 1

\## Este es un encabezado de nivel 2

\### Este es un encabezado de nivel 3

\#### Este es un encabezado de nivel 4

\##### Este es un encabezado de nivel 5

\###### Este es un encabezado de nivel 6

**Estilos de letra**

Para aplicar estilos de letra como negrita, cursiva o tachado, usamos los símbolos \*, \*\* o ~~ alrededor del texto que queremos modificar. Por ejemplo:

\- Para escribir en \*\*negrita\*\* usamos dos asteriscos: `\*\*negrita\*\*`.

\- Para escribir en \*cursiva\* usamos un asterisco: `\*cursiva\*`.

\- Para escribir con ~~tachado~~ usamos dos virgulillas: `~~tachado~~`.

\- Podemos combinar estos estilos usando más de un símbolo: `\*\*\*negrita y cursiva\*\*\*`, `\*\*~negrita y tachado~\*\*` o `\*~cursiva y tachado~\*`.

**Listas e imágenes**

Para escribir una lista con viñetas, usamos el signo menos al comienzo de cada línea: `- elemento 1`, `- elemento 2`, etc. Por ejemplo:

- Esta es una lista
- Con tres elementos
- Muy sencillos

Para escribir una lista numerada, usamos un número seguido de un punto al comienzo de cada línea: `1. elemento 1`, `2. elemento 2`, etc. Por ejemplo:

1. Este es el primer elemento
1. Este es el segundo elemento
1. Este es el tercer elemento

Usamos la etiqueta <img> con el atributo `src` para insertar una imagen, indicando la dirección web donde se encuentra la imagen. También podemos modificar el tamaño de la imagen con los atributos `width` y `height`. Por ejemplo:

![logo](https://izainea.github.io/mercadeia/_static/logo.png)

Las **celdas de código** son espacios donde podemos escribir y ejecutar instrucciones de Python. Estas instrucciones pueden definir variables, funciones, clases, importar librerías, manipular datos, crear gráficos o aplicar algoritmos de aprendizaje automático. Para editar una celda de código, hacemos clic sobre ella y escribimos el código que queremos. Para ejecutarlo, usamos el botón de play o las teclas Ctrl+Enter. El resultado de la ejecución se mostrará debajo de la celda, junto con cualquier mensaje de error o advertencia que se produzca. Podemos usar la opción "Reiniciar entorno de ejecución" del menú "Entorno de ejecución" para borrar todas las variables y reiniciar el notebook.

Python es un lenguaje de programación de alto nivel, que se caracteriza por su simplicidad y flexibilidad. Python tiene una sintaxis clara y consistente, que facilita la lectura y escritura del código. Además, Python es un lenguaje interpretado, lo que significa que no necesita ser compilado antes de ejecutarse, sino que el código se traduce a lenguaje máquina en tiempo real.

Para escribir código en Python, debemos seguir algunas reglas básicas, como:

- Usar indentación para delimitar los bloques de código. La indentación consiste en agregar espacios o tabulaciones al inicio de cada línea de un bloque. Todos los bloques que pertenecen al mismo nivel deben tener la misma indentación.

- Usar dos puntos (:) para indicar el inicio de un bloque. Por ejemplo, después de una declaración if, for o def, se debe colocar dos puntos y luego indentar el bloque correspondiente.

- Usar comillas simples (' ') o dobles (" ") para crear cadenas de texto. Por ejemplo: 'Hola', "Python".

- Usar el símbolo # para crear comentarios. Los comentarios son líneas de texto que no se ejecutan y sirven para explicar el código o dejar notas. Por ejemplo: # Esto es un comentario

- Usar mayúsculas y minúsculas de forma consistente. Python distingue entre mayúsculas y minúsculas, lo que significa que las variables, funciones o clases con nombres diferentes según el uso de mayúsculas y minúsculas son tratadas como entidades distintas. Por ejemplo: nombre, Nombre y NOMBRE son tres variables diferentes.

Estas son algunas de las reglas elementales de programación en Python. Para aprender más sobre este lenguaje, podemos consultar la documentación oficial o algún tutorial en línea. Google Colab nos ofrece un entorno interactivo para practicar y experimentar con Python sin necesidad de instalar nada en nuestro ordenador.

Un ejemplo de cómo usar Google Colab para revisar nuestro dataset es el siguiente:

```python
# Importar las librerías necesarias para el análisis de datos
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

El anterior código importa las librerías necesarias para el análisis de datos. La librería pandas nos permite trabajar con tablas de datos, la librería numpy nos permite realizar operaciones matemáticas y la librería matplotlib nos permite crear gráficos. Estas librerías son muy útiles para el análisis de datos y la visualización de resultados.


Para cargar el dataset desde el archivo csv tenemos dos alternaticas, la primera es si el archivo se encuentra en el directorio raíz, en ese caso lo subimos en Google Colab y lo cargamos de la siguiente forma:

- Acceder al panel de archivos en Google Colab haciendo clic en el ícono de carpeta en la barra lateral izquierda.

- Hacer clic en el ícono de subir archivo en la parte superior derecha del panel y seleccionar el archivo ifood\_df.csv desde la ubicación donde se guardó en el ordenador.

- Esperar a que el archivo se suba y se muestre en el panel de archivos con su nombre y tamaño.

- El siguiente código carga el archivo ifood\_df.csv en un DataFrame de pandas y muestra las primeras filas del DataFrame, la información sobre las columnas y el resumen estadístico de las variables.

```python

# Cargar el dataset desde el archivo csv si se encuentra en el directorio raíz
df = pd.read_csv("ifood_df.csv")

# Explorar el dataset y realizar un análisis exploratorio de datos (EDA)
print(df.head())
print(df.info())
print(df.describe())

```

Otra alternativa es si el archivo se encuentra en Google Drive, en ese caso montamos el Google Drive con el siguiente código:

```python
# Montar el Google Drive
from google.colab import drive
drive.mount('/content/drive')
```

Luego navegamos por las carpetas hasta encontrar el archivo deseado y lo cargamos de la siguiente forma:

```python
# Cargar el dataset desde el archivo csv si se encuentra en Google Drive
df = pd.read_csv("/content/drive/MyDrive/datos.csv")

# Explorar el dataset y realizar un análisis exploratorio de datos (EDA)
print(df.head())
print(df.info())
print(df.describe())
```


 Para extraer la ruta relativa de un archivo, podemos usar el click derecho sobre el archivo y seguir los siguientes pasos:

    - Seleccionar el archivo cuya ruta relativa queremos obtener.
    - Hacer click derecho sobre el archivo y elegir la opción "Copiar ruta".
    - Pegar la ruta copiada en un editor de texto o en la consola de Python.
    - Eliminar la parte de la ruta que corresponde al directorio base desde el que queremos obtener la ruta relativa. Por ejemplo, si el directorio base es "/content", podemos eliminar "/content/" de la ruta copiada.
    - La ruta resultante es la ruta relativa del archivo. Por ejemplo, si la ruta copiada es "/content/drive/MyDrive/datos.csv", la ruta relativa es "drive/MyDrive/datos.csv".

## **Copilotos LLM**
Los copilotos LLM son asistentes de escritura inteligentes que nos ayudan a programar en diferentes lenguajes usando el lenguaje natural. En esta clase usaremos el copiloto LLM para Python, que nos permite escribir código en Python usando frases en español. Para usar el copiloto LLM para Python, debemos seguir las siguientes instrucciones:

- Escribir la frase en español que describe lo que queremos hacer con el código, precedida por el símbolo #.
- Presionar la tecla Tab para que el copiloto LLM genere el código en Python correspondiente a la frase.
- Revisar el código generado y modificarlo si es necesario.
- Repetir el proceso hasta completar el análisis de datos.
## **Análisis de datos**
Para realizar el análisis de datos de la tabla, seguiremos los siguientes pasos:

1. Importar las librerías necesarias para el análisis de datos.
1. Cargar el dataset desde el archivo csv.
1. Explorar el dataset y realizar un análisis exploratorio de datos (EDA).
1. Visualizar el dataset y crear gráficos que muestren la distribución de las variables y las relaciones entre ellas.
1. Obtener información sobre el perfil de los clientes, sus preferencias de compra y su respuesta a las campañas de marketing.

El cuaderno compartido nos ayudará a realizar la clase:

<https://colab.research.google.com/drive/1KbhZ6HIprtePhDj10mtxpBrStOTetpQK?usp=sharing>
