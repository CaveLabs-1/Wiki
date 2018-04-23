#Guia para la generación de criterios de aceptación
Versión 1.0

Esta guía pretende ayudar a definir cuales son los valores  permitidos por tu sistema

## Criterios
<ol>
<li>Tiempo de Respuesta</li><li>Throughput</li><li>Número de Conexiones </li> <li>Disponibilidad </li>
</ol>


###Tiempo de Respuesta
La velocidad de carga de una página web puede marcar el límite entre el éxito y el fracaso de una organización, es por ende que el tiempo va en proporción a las metas de nuestro cliente, para ello es necesario considerar estos datos:

1. Tiempo cuando la paguina empieza a renderizar, este tiempo entre menor es mejor, pues da al usuario una sensación de logro y retroalimentación de que lo que solicita se está procesando.  Altamente recomendado no mayor a tres segundos.
2. Tiempo total del renderizado de la página, este tiempo entre menor sea mejor será. 

Los benchmark actuales en la industria son:
- Páginas que tardan más de 5 segundos en ser renderizadas completamente, el 74% de sus usuarios las abandonan
- El 60% de los usuarios esperan que la página esté completamente renderizada en 3 segundos o menos.
- El tiempo promedio de carga de las 50 mejores tiendas online  es de 4.8 segundos.

Referencia: smartbear.com

Por lo que cualquier sistema que en condiciones normales cargue completamente por debajo de 5 segundos se podría considerar aceptable, pero recuerda que hay sistemas donde el tiempo de respuesta es de mayor importancia por lo que optar por un tiempo menor a 3 segundos sería altamente recomendado.

###Throughput
Indica el número de transacciones que puede manejar el sistema por segundo. Este valor depende directamente de las especificaciones técnicas del hosting (hardware), el overhead del procesamiento del sistema, el paralelismo del sistema, y el tipo de transacciones. Este número entre mas alto es mejor.

Este valor va en proporción al uso si es un sistema que lo van a utilizar millones de personas, un throughput alto es lo que se estaría buscando. Pero si es un sistema que solo una persona lo estará utilizando un throughput de 10 operaciones por segundo es suficiente.

Este valor idealmente debe ser constante sin importar el número de usuario que le lleguen al sistema, es decir si tengo un throughput de 15/s si tengo cien usuarios seguirá siendo el mismo que si tengo 100 mil usuarios.

El throughput promedio calculado de páginas web estáticas es de 50/seg.

### Número de Conexiones
Este valor es un poco más difícil de definir pues debes considerar el mayor número de conexiones simultáneas que tu sistema pudiese tener, es decir si soy hbo y voy a tener el estreno del capítulo final de GoT mi numero de conexiones deberá ser mayor al numero actuales de usuarios que tengo registrados pues puede ser que tenga nuevos usuarios que se registren solo para ver el capítulo. 

Así que si el sistema actualmente lo usaran 10 personas es recomendable considerar el crecimiento que puede tener el cliente al usar el sistema y estimar el número, para hacer una prueba donde aguante un 12 que es un crecimiento del 20%.

###Disponibilidad

Los sistemas no pueden estar siempre activos, por eso se establece el valor mínimo del porcentaje que el sistema debe de estar funcionado.  La media actual de sistemas es de 99%. 


Bitacora
No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
------------|------|-------------|-----------|-----------
1.0 |Creación de la guia | Iancarlo Romero |  | 23 de Abril

