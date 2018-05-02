# Proceso de Pruebas SWAT
Versión 1.1

[]() | []()
--|--
Objetivo | Probar un sistema de software.
Métricas utilizadas | <ul><li>Tiempo de Respuesta</li><li>Throughput</li><li>Número de Conexiones</li><li>Disponibilidad</li></ul>[Guía de Metricas SWAT](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/Guias/GuiaMetricaSWAT.md)
Repositorio de Métricas | [Formato Swat](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/Formatos/FormatoPruebasSWAT.docx), en la wiki de cada equipo.
Entrada del Proceso | Un nuevo sistema no probado en ambiente final.
Criterios de entrada | Un sistema que tenga el 100% de la funcionalidad hecha.
Definir políticas y estándares | Formato de Reporte de Pruebas completa.
Salidas del proceso | Un sistema de software probado.
Criterios de salida | Que el checklist esté completado exitosamente

## Definición de Fases
No. de Fase | Fase | Actividades | Encargado | Áreas
------------|------|-------------|-----------|-------
1 | Delimitación | Establecer los criterios de aceptación para un sistema adecuado<ul><li>Tiempo de Respuesta</li><li>Throughput</li><li>Número de Conexiones</li><li>Disponibilidad</li></ul>[Guía de Metricas SWAT](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/Guias/GuiaMetricaSWAT.md) | Product Owner & Architecture Owner | PPQA RM
2 | Preparación | <ol><li>Registrar los criterios de aceptación por cada elemento a evaluar en la plantilla de [Formato Swat](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/Formatos/FormatoPruebasSWAT.docx)</li><li>Preparar el ambiente de pruebas</li></ol>| Architecture Owner | MA
3 | Ejecutar las pruebas | Realizar las pruebas siguiendo el [Formato Swat](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/Formatos/FormatoPruebasSWAT.docx) | Team  Member | MA PPQA
4 | Análisis | Analizar y ver qué información se obtuvo al realizar las pruebas, ¿Cuáles no pasaron, definir si fue por cuestiones de configuración, de diseño, criterios no adecuados o es error de hardware? Por ejemplo: <ul><li>Tiempo de Respuesta es muy alto, reduce el tamaño de las imágenes o simplifica los archivos de estilos</li><li>Throughput bajo, simplifica la complejidad asintótica o mejorar el hardware del sistema</li><li>Número de Conexiones insuficientes, mas memoria RAM es una posible solución</li><li>Disponibilidad no adecuada, cambia de proveedor de Hosting</li></ul> | Team Member & Architecture Owner | RM MA PPQA
5 | Correcciones | Hacer las correcciones pertinentes al sistema en caso de que alguna no haya pasado exitosamente y volver a ejecutar el proceso | Team Member & Architecture Owner | PPQA
6 | Verificación | Que el Formato de Reporte de Procesos esté completado y llenar el [Checklist](https://docs.google.com/spreadsheets/d/1FaHFsycVU1FwIVxs4_sD7ceZwTrKYKYXfQ2f0IrQ-bs/edit#gid=0)  | Team Member | VAL VER PPQA

## Plan de implementación

<ol><li>Presentar el proceso al grupo</li><li>Subirlo a los medios adecuados Slack y wikis</li></ol>

## Bitácora
No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
------------|------|-------------|-----------|-----------
1.0 |Creación del proceso | Iancarlo Romero | Manuel Flores | 23 de Abril
1.1 |Actualizar Proceso | Ian y Luis Rodriguez | Valter Nuñez | 1 de Mayo


