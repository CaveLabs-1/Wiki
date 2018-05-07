# Guía para estimar tamaño de un proyecto
Dentro de esta guía se va a detallar cómo estimar el tamaño de un proyecto con puntos de función. 


RET DET & FTR

Tipo de elemento de registro (RET): un RET es un subgrupo de elementos de datos reconocibles por el usuario dentro de un ILF o un EIF. Lo mejor es observar las agrupaciones lógicas de datos para ayudar a identificarlas. El concepto de RET se discutirá en detalle en los capítulos que tratan sobre el archivo lógico interno y los archivos de la interfaz externa. (modelo)

Tipo de archivo referenciado (FTR): un FTR es un tipo de archivo al que hace referencia una transacción. Un FTR también debe ser un archivo lógico interno o un archivo de interfaz externo. (relaciones)

Tipo de elemento de datos (DET): un DET es un campo único reconocible por el usuario, no recursivo (no repetitivo). Un DET es información que es dinámica y no estática. Un campo dinámico se lee de un archivo o se crea a partir de DET contenidos en un FTR. Además, un DET puede invocar transacciones o puede ser información adicional con respecto a las transacciones. Si un DET es recursivo, solo la primera aparición del DET se considera no en todas las ocurrencias. (campos)

Más sobre DET (explicación de stackoverflow)


Un DET (Tipo de elemento de datos) no es solo un campo de entrada: es cualquier información reconocible por el usuario que cruza el límite de la aplicación. Generalmente, cada campo de entrada en la pantalla es de hecho un DET, pero no siempre. No voy a entrar en eso ahora, sin embargo, dado que en este caso particular todos los campos de entrada son de hecho DET. Vamos a hablar de esos 2 DET que parecen desaparecidos.

Debe contar 3 DET para los 3 campos de entrada (Nombre del proyecto, Tipo de proyecto y Descripción del proyecto), y también 1 DET para hacer clic en el botón Guardar. Tenga en cuenta que, incluso si hubiera varias formas de guardar el proyecto (haciendo clic en el botón Guardar, presionando Entrar, etc.), seguiría contando solo 1 DET.

En cuanto al quinto DET, supongo que el autor está contando 1 DET para cualquier mensaje que la aplicación pueda mostrar en el proceso de creación de un nuevo proyecto (mensaje de confirmación, mensajes de error, advertencias, etc.). De nuevo, solo debe contar 1 DET sin importar cuántos mensajes posibles haya. Y dije que asumo porque, si bien es correcto contar 1 DET para la capacidad de mostrar mensajes (es, después de todo, información reconocible por el usuario que cruza el límite de la aplicación), debería haber mencionado explícitamente al menos un mensaje, especialmente porque es un ejemplo de enseñanza.

Entradas

![imagotype](https://i.imgur.com/GV71QGA.png)

Salidas

 Los datos crean informes o archivos de salida enviados a otras aplicaciones.

![imagotype](https://i.imgur.com/LnEGZaz.png)

Vocabulario típico: Explorar Mostrar Obtener resultados en línea Imprimir consulta Informes Solicitud Recuperar búsqueda Seleccionar vista

Inquiere

 Recuperación de datos de uno o más archivos lógicos internos y archivos de interfaz externos.
![imagotype](https://i.imgur.com/juE9lGH.png)

Ejemplo:
Una pantalla llena de información de la dirección del cliente sería un ejemplo de EQ.

Vocabulario típico:
Tenga en cuenta que las palabras son muy similares a las relacionadas con los resultados externos.
Examinar Mostrar Extraer Buscar Buscar Recopilar Obtener listas desplegables Buscar en las líneas En lista de salida de salida Consulta de impresión Búsqueda de escaneo Seleccionar Mostrar informes de visualización

Archivos lógicos

![imagotype](https://i.imgur.com/ojuuEkw.png)

Interfaces

![imagotype](https://i.imgur.com/g0tadlp.png)

Influencia

Se usa para calcular el factor para el ajuste de los puntos de función. (Ejemplos y más detalles en https://www.softwaremetrics.com/Function%20Point%20Training%20Booklet%20New.pdf)

0 No presente, o sin influencia
1 Influencia incidental
2 influencia moderada
3 Influencia promedio
4 Influencia significativa
5 Fuerte influencia en todo


Referencias:
https://www.softwaremetrics.com/Function%20Point%20Training%20Booklet%20New.pdf
https://stackoverflow.com/questions/28136141/data-element-typedet-in-function-point-analysis

La pregunta que debemos hacernos es: <br>
¿Tenemos datos históricos de proyectos similares? Es decir, ¿sabemos cuántas horas tardamos en hacer ciertas actividades de proyectos anteriores que se parecen a este?<br>
Si la respuesta es no, tendremos que hacer nuestra mejor aproximación basándonos en nuestro criterio.<br>
Si la respuesta es sí, entonces se procede a hacer la estimación utilizando regresión lineal.


Última edición: @MelannieTorres @DavidSrn abril 27, 2018
