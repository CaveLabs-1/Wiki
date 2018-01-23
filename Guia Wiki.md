# Guía para editar la Wiki
El propósito de esta guía es que cualquier miembro del equipo de CaveLabs sea capaz de agregar, descargar y editar contenido cumpliendo con las políticas del departamento. En ella se podrán encontrar los pasos que se deben seguir para manejar el contenido de la Wiki además de un breve manual donde se explicará la sintaxis que será utilizada por el departamento de CaveLabs.

## Index
* [¿Qué es lo que va en el README y cómo va ordenado?](#README)

* [¿Cómo creo un nuevo documento y dónde lo guardo?](#NuevoDocumento)

* [¿Cómo nombro a mi nuevo documento?](#Nombro)

* [Ya tengo mi documento ¿Ahora qué?](#DocumentoListo)

* [No se agregar imágenes, links, etc aiuda](#Imagenes)
 

<a id="README"></a> 
## ¿Qué es lo que va en el README y cómo va ordenado? 
El README es la página principal de la Wiki, donde solamente puede contener un index donde se encontraran los links a los documentos principales de cada fase y documentos cuyo propósito sea general, por ejemplo un link hacia la página de minutas.

El index empieza con el nombre de las fases en orden de ejecución, por ejemplo primero va la fase de incepción, seguida del link hacia el documento de la fase de construcción y finalmente el link hacia la fase de transición. Después de los links fases (Incepción, construcción y transición) seguirán los links a los documentos de propósito general. 

El nombre del link debe de ser el nombre del documento y debajo del nombre una pequeña descripción no mayor de un renglón de qué es lo que se encuentra en ese archivo.

<a id="NuevoDocumento"></a> 
## ¿Cómo creo un nuevo documento y dónde lo guardo?
Para cada guía y formato es necesario crear un documento nuevo que se encuentre en la carpeta de su fase correspondiente, por ejemplo la guía de requisitos de la fase de incepción se encontrará en la carpeta de “Incepción”; si es necesario se puede crear un documento nuevo para el script sin embargo es preferible que todos los scripts se encuentren en el documento de su respectiva fase, por ejemplo el script de requerimientos que es utilizado en la fase inicial deberia de estar en el documento de Inception Phase.md

Si la carpeta no está creada, se puede crear fácilmente de la siguiente manera
![carpetas](https://i.stack.imgur.com/9Ifmj.gif)

Donde se escribe el nombre de la carpeta en el espacio correspondiente al nombre del archivo y despues se escribe “/” para indicar que es una carpeta. 

Si sólo se requiere un documento para un documento de propósito general puede ser creado en el root del proyecto.

<a id="Nombro"></a> 
## ¿Cómo nombro a mi nuevo documento?
El documento debe de tener el nombre en español y debe de utilizar espacios para que sea más fácil leer el nombre. La longitud del nombre de preferencia debe de ser de máximo dos palabras. Es importante recordar poner la extensión “.md” al final del nombre para que Github lo reconozca como un documento de markdown.

<a id="DocumentoListo"></a> 
## Ya tengo mi documento ¿Ahora qué?
Es importante tener como título principal el nombre del documento para que la persona tenga continuidad al documento que está leyendo. Después del título se debe de poner una pequeña introducción por si alguién no recuerda que es eso en específico. Después de la introducción, si el documento contiene varios apartados es necesario tener un index que vaya a los documentos necesitados o a las secciones del documento. Es importante seguir el siguiente formato de inicio para mantener una estandarización en toda la documentación del equipo.

![sintaxis](https://image.prntscr.com/image/qWt7qq-ESa_Ky4r3YVCyhg.png)

<a id="Imagenes"></a> 
## No se agregar imágenes, links, etc aiuda 
Para agregar links que lleven a algún apartado dentro del mismo documento:

![anchors](https://image.prntscr.com/image/0aY45VJtQQaXv480psGp8g.png)

Eso esta muy chido pero sigo sin saber como agregar una imagen.
Aquí hay una [guía oficial de Github](https://guides.github.com/features/mastering-markdown/) y esta otra [guía creada por el usuario adam-p](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), que te ayudarán en tu viaje de aprendizaje de Markdown.

![thatsAll](https://i.ytimg.com/vi/0FHEeG_uq5Y/maxresdefault.jpg)
---

Last edition: @pirty6 enero 22, 2018.
