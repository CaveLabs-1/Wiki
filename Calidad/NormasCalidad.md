# Normas de Calidad
Versión 2.1

**Estándares**

**Python**

- El  máximo de caracteres por línea deberá ser 80.

      foo\_bar(self, width, height, color=&#39;black&#39;, design=None, x=&#39;foo&#39;,
                         emphasis=None, highlight=0)

      if (width == 0 and height == 0 and
              color == &#39;red&#39; and emphasis == &#39;strong&#39;):

- Indentar código a 4 espacios.

-
  - No combinar tabs y espacios.
  - En caso de hacer un salto de línea por llegar al máximo de caracteres, la indentación debe ir alineada al paréntesis que marca el inicio del grupo al que pertenece (igual al ejemplo anterior).

- Nombres
  - module_name, package_name, ClassName, method_name, ExceptionName, function_name, GLOBAL_CONSTANT_NAME, global_var_name, instance_var_name, function_parameter_name, local_var_name.

   

[https://google.github.io/styleguide/pyguide.html](https://google.github.io/styleguide/pyguide.html)

**Django**

- Seguir los mismos estándares expuestos en la sección de python.

- El primer parámetro de una view debe ser llamado &#39;request&#39;.

      def my\_view (request, foo):
        #...

- Las clases de los modelos y sus campos deberán ser nombrados siguiendo los estándares de python, a si mismo los campos deberán ir enseguida sin salto de línea y las funciones o clases que estén dentro de la primera con un salto de línea como separación.

          class Person(models.Model):
              first\_name = models.CharField(max\_length=20)
              last\_name = models.CharField(max\_length=40)

          class Meta:
                 verbose\_name\_plural = &#39;people&#39;

- Dentro de los templates de Django, el código se pone entre llaves dobles, separadas por un espacio entre.

Sí: {{ foo }}

No: {{foo}}

[https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/)

**HTML/CSS**

- Indentación a dos espacios, no combinar tabs con espacios.

- Todo el código tiene que estar escrito en minúsculas, esto aplica para

-
  - HTML: elementos, nombres, atributos y valores de estos.
  - CSS: selectores, propiedades y valores de estas.

[https://google.github.io/styleguide/htmlcssguide.html](https://google.github.io/styleguide/htmlcssguide.html)



**Requerimientos**

[http://www.utm.mx/~caff/doc/OpenUPWeb/openup/guidances/checklists/good\_requirements\_594ACCBD.html](http://www.utm.mx/~caff/doc/OpenUPWeb/openup/guidances/checklists/good_requirements_594ACCBD.html)

**Funcionalidad**

- El elemento cumple con la funcionalidad establecida en su análisis y diseño.

- El elemento pasa las pruebas establecidas durante su análisis.

- El elemento brinda retroalimentación continua al usuario respecto a lo que acontece en el sistema.

**Eficiencia**

- El elemento realiza su función de la mejor forma.

- En caso de que exista una mejor forma de realizar la misma tarea esta debe ser implementada.

**Comentarios de documentación.**

- Son escritos para aquellas personas (incluyendo al autor) que en un futuro vayan a mantener, refactorizar o extender tu código.

- Antes de documentar, asegura que tu código sea lo más sencillo y eficiente posible. &quot;Good code is self documenting.&quot;

- Evita comentarios innecesarios.

- Los comentarios explican por qué se hacen las cosas, el código explica cómo se hace.

- El comentario se escribe una línea sobre la sección a documentar.

- El comentario se escribe siguiendo los estándares de código dependiendo del lenguaje de programación del archivo.



## Calendarizar tareas
1.  Al realizar la planeación de la iteración será necesario asignar prioridad a cada historia de usuario y dentro de esta misma, a las diferentes tareas.
    1. En base a esta prioridad, se planearán fechas para completar cada una de estas tareas dentro del tiempo delimitado de dicha iteración (respetando la prioridad previamente definida). Esto con fin de asegurar el seguimiento de tanto los tiempos y prioridad planeadas inicialmente.
 
 
 1.  Al encontrar un defecto, este se calendarizará tomando en cuenta lo siguiente:
        1. Si se estima un tiempo menor a una hora para realizar el defecto encontrado se corregirá en el momento por la misma persona que lo ha encontrado. Se registrará dentro de la bitácora de defectos.
         1. Si se estima un tiempo mayor a una hora para realizar el defecto encontrado se generará una nueva tarea que corresponde a este mismo. Será necesario darle una prioridad en comparación con el resto de las tareas faltantes y colocarlo con estas añadiendo una fecha para su corrección según su importancia. De ser necesario, se volverá a planear para las tareas que lo requieran.


## Bitácora


No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
---------------|--------|-------|----------|----------------
1.4 | Agregar calendarización para tareas | Rodolfo Martínez | Valter Núñez | 4/02/2018
2.0 | Nuevas Normas de Calidad | Victor Hugo Torres | Valter Núñez | 20/04/2018
2.1 | Agregar Bullet points | Victor Hugo Torres | Valter Núñez | 07/05/2018
