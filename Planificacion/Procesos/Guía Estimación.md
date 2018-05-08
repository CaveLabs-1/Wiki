# Guía para estimar tamaño de un proyecto
Dentro de esta guía se va a detallar cómo estimar el tamaño de un proyecto con puntos de función.
## Índice

  * [RET DET & FTR](#ret-det-&-ftr)
  * [Entradas](#entradas)
  * [Salidas](#salidas)
  * [Inquiere](#inquiere)
  * [Archivos Lógicos](#arch)
  * [Interfaces](#interfaces)
  * [Influencia](#influencia)


## RET DET & FTR

Tipo de elemento de registro (RET): un RET es un subgrupo de elementos de datos reconocibles por el usuario dentro de un ILF ("Internal Logical Files") o un EIF ("External Interface File"). Lo mejor es observar las agrupaciones lógicas de datos para ayudar a identificarlas. (modelo)

Tipo de archivo referenciado (FTR): un FTR es un tipo de archivo al que hace referencia una transacción. Un FTR también debe ser un archivo lógico interno o un archivo de interfaz externo. (relaciones)

Tipo de elemento de datos (DET): un DET es un campo único reconocible por el usuario, no recursivo (no repetitivo). Un DET es información que es dinámica y no estática. Un campo dinámico se lee de un archivo o se crea a partir de DET contenidos en un FTR. Además, un DET puede invocar transacciones o puede ser información adicional con respecto a las transacciones. Si un DET es recursivo, solo la primera aparición del DET se considera no en todas las ocurrencias. (campos)



Un DET (Tipo de elemento de datos) no es solo un campo de entrada: es cualquier información reconocible por el usuario que cruza el límite de la aplicación. Generalmente, cada campo de entrada en la pantalla es de hecho un DET, pero no siempre.

Un ejemplo es contar 3 DET para los 3 campos de entrada (Nombre del proyecto, Tipo de proyecto y Descripción del proyecto), y también 1 DET para hacer clic en el botón Guardar. Hay que tener en cuenta que, incluso si hubiera varias formas de guardar el proyecto (haciendo clic en el botón Guardar, presionando Entrar, etc.), seguiría contando solo 1 DET.


## Entradas

![imagotype](https://i.imgur.com/GV71QGA.png)


## Salidas

 Los datos crean informes o archivos de salida enviados a otras aplicaciones.

![imagotype](https://i.imgur.com/LnEGZaz.png)


## Inquiere

Recuperación de datos de uno o más archivos lógicos internos y archivos de interfaz externos.

![imagotype](https://i.imgur.com/juE9lGH.png)

Ejemplo:
Una pantalla llena de información de la dirección del cliente sería un ejemplo de EQ.

## <h2 id_="arch">Archivos lógicos</h2>

![imagotype](https://i.imgur.com/ojuuEkw.png)

## Interfaces

![imagotype](https://i.imgur.com/g0tadlp.png)

## Influencia

Se usa para calcular el factor para el ajuste de los puntos de función. (Ejemplos y más detalles en https://www.softwaremetrics.com/Function%20Point%20Training%20Booklet%20New.pdf)

  * 0 No presente, o sin influencia
  * 1 Influencia incidental
  * 2 influencia moderada
  * 3 Influencia promedio
  * 4 Influencia significativa
  * 5 Fuerte influencia en todo

La pregunta que debemos hacernos es: <br>

  * ¿Tenemos datos históricos de proyectos similares? Es decir, ¿sabemos cuántas horas tardamos en hacer ciertas actividades de proyectos anteriores que se parecen a este?<br>

  * Si la respuesta es no, tendremos que hacer nuestra mejor aproximación basándonos en nuestro criterio.<br>

  * Si la respuesta es sí, entonces se procede a hacer la estimación utilizando regresión lineal.

## Referencias:

* https://www.softwaremetrics.com/Function%20Point%20Training%20Booklet%20New.pdf

* https://stackoverflow.com/questions/28136141/data-element-typedet-in-function-point-analysis



Última edición: @davidsrn mayo 7, 2018
