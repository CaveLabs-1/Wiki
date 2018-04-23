# Proceso de Pruebas SWAT
Versión 1.0

[]() | []()
--|--
Objetivo | Probar un sistema de software.
Métricas utilizadas | <ul><li>Tiempo de Respuesta</li><li>Throughput</li><li>Número de Conexiones</li><li>Disponibilidad</li></ul>
Repositorio de Métricas | [Metricas SWAT](https://github.com/CaveLabs-1/Wiki/SWAT/MetricaSWAT.md "Metricas SWAT")
Criterios de entrada | Un sistema no probado.
Definir políticas y estándares | Plantilla del Reporte de Pruebas.
Salidas del proceso | Un sistema de software probado.
Criterios de salida | Un sistema que haya pasado exitosamente todas las pruebas según  los criterios de aceptación. 

## Definición de Fases
No. de Fase | Fase | Actividades | Encargado
------------|------|-------------|-----------
1 | Delimitación | Establecer los criterios de aceptación para un sistema adecuado<ul><li>Tiempo de Respuesta</li><li>Throughput</li><li>Número de Conexiones</li><li>Disponibilidad</li></ul>[Metricas SWAT](https://github.com/CaveLabs-1/Wiki/SWAT/MetricaSWAT.md "Metricas SWAT") | Product Owner & Architecture Owner
2 | Preparación | <ol><li>Registrar los criterios de aceptación por cada elemento a evaluar en la plantilla de [Reporte de Pruebas](https://github.com/CaveLabs-1/Wiki/SWAT/ReporteSWAT.md "Reporte de Pruebas")</li><li>Preparar el ambiente de pruebas</li></ol>| Architecture Owner
3 | Ejecutar las pruebas | Realizar las pruebas siguiendo el [Reporte de Pruebas](https://github.com/CaveLabs-1/Wiki/SWAT/ReporteSWAT.md "Reporte de Pruebas") | Team  Member
4 | Análisis | Analizar y ver qué información se obtuvo al realizar las pruebas, ¿Cuales no pasaron, definir si fue por cuestiones de configuración, de diseño, criterios no adecuados o es error de hardware? | Team Member & Architecture Owner
5 | Correcciones | Hacer las correcciones pertinentes al sistema en caso de que alguna no haya pasado exitosamente y volver a ejecutar el proceso | Team Member & Architecture Owner

## Plan de implementación

<ol><li>Presentar el proceso al grupo</li><li>Subirlo a los medios adecuados Slack y wikis</li></ol>

## Bitácora
No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
------------|------|-------------|-----------|-----------
1.0 |Creación del proceso | Iancarlo Romero | Manuel Flores | 23 de Abril


Última Modificación: @ian (23 de Abril)

