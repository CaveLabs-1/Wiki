# Proceso para Cambiar elementos de configuración
Versión 2.0


[]() | []()  
--|--
Objetivo| Actualizar la versión de un elemento de la línea base
Métricas utilizadas | Número de Errores / Número de días desde la última auditoría
Repositorio de Métricas | Carpeta Auditorías encontrada en el root de la wiki
Entrada del Proceso | Artefacto que se quiera subir a la wiki
Criterios de entrada | Elemento de configuración
Definir políticas y estándares | Dependiendo el artefacto cumplir con las [políticas de guías](https://github.com/CaveLabs-1/Wiki/blob/master/Calidad/Politicas%20Generales/Politicas%20Guias.md), [políticas de formatos](https://github.com/CaveLabs-1/Wiki/blob/master/Calidad/Politicas%20Generales/Politicas%20Formatos.md), [guía de proyectos](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Guias/Guia%20Proyecto.md), [guía de herramientas](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Guias/Guia%20Herramientas.md), [guía de procesos](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Guias/Guia%20Procesos.md), o [guía de roles](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Guias/Guia%20Roles.md)
Salidas del proceso | Línea base
Criterios de salida | Línea base aprobada por el manager de configuración y que se encuentren en la Wiki tomando en cuenta el [checklist](https://docs.google.com/spreadsheets/d/18sip07IcwXP1hOEYeHXHiEgInX6_O9oWMhLfAf98j-c/edit?usp=sharing)


## Definición de Fases
No. de Fase | Fase | Actividades | Encargado | Áreas
------------|------|-------------|-----------|-------
1 | Identificación | Identificar elemento de la línea base encontrada en la [guía de elemento de configuración](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Guias/Guia%20Configuration%20Item.md) | Team member | CM
2 | Validación | Validar los cambios y subirlos a la wiki | CM | PPQA, CM
3 | Análisis de Métricas | Cada 3 días se harán auditorias, sin embargo, si el número de errores sea menor o igual a 5 las auditorías se harán cada semana, y si los errores son iguales o menores a 2 entonces se hará cada 2 semanas. [Formato de Auditorias](https://github.com/CaveLabs-1/Wiki/blob/master/Configuracion/Auditor%C3%ADa%20Configuraci%C3%B3n.xlsx) Los resultados de las auditrias se guardarán en la carpeta auditorias que se encuentra en el root del proyecto y se pondrá un link hacia él en el archivo "Auditorias.md". El nombre del link debe de ser la fecha en la cual fue realizada la auditoría. | CM de cada Equipo | MA



## Plan de implementación
1. Subir un mensaje a Slack donde se exprese que un elemento de configuración fue versionado.

## Bitácora
No. de versión | Cambio | Autor | Aprobado | Fecha de Cambio
---------------|--------|-------|----------|-----------------
1 | Creación | Mariana | Mauricio Hernandez | 7 Feb 2018
1.1 | Modificación | Mariana | Valter Núñez |13 Mar 2018
1.2 | Agregar fase análisis | Mariana | Valter Núñez | 18 Abr 2018
1.3 | Modificar redacción de métricas | Mariana  | Valter Núñez | 20 Abr 2018
2.0 | Agregar áreas y checklists | Mariana | Valter Núñez| 2 May 2018
