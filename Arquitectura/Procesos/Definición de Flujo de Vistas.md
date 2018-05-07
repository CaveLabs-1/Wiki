# Definición de Flujo de Vistas
Versión 2.0


[]() | []()
--|--
Objetivo| Validar el flujo de la app y definir un diagrama de despliegue óptimo.
Métricas utilizadas | Número de vistas creadas por historia de usuario
Repositorio de Métricas | Una gráfica de barras mostrando las vistas por historia de usuario que se guardará en el documento Ernie
Entrada del Proceso | Necesidad de crear un flujo de vistas para definir una arquitectura
Criterios de entrada | Criterios para crear la arquitectura, componentes del sistema y requerimientos.
Definir políticas y estándares | UML
Salidas del proceso | Diagrama de flujo validado por el cliente, diagrama de despliegue óptimo, [Flujo de Vistas](https://github.com/CaveLabs-1/Wiki/tree/master/Arquitectura/Formatos/Formato%20Ernie%20(Flujo%20de%20Vistas%20y%20Arquitectura%20Inicial).docx), Cumplir con el [Checklist](https://docs.google.com/spreadsheets/d/1HmgptaVZD09DKs0Po2TJ3fVDQKbMR3NBtB9x4wKJ6nQ/edit?usp=sharing)
Criterios de salida | Los Modelos deben de seguir el estándar de UML y el diagrama debe de ser validado por el cliente


## Definición de Fases
No. de Fase | Fase | Actividades | Encargado | Áreas
------------|------|-------------|----------- | ---
1 | Definición |<ul><li>Definir número de vistas requeridas</li><li>Definir tipo de diagrama a usar (alto vs bajo nivel)</li></ul>| Encargado de Arquitectura | TS
2 | Diseño |<ul><li>Diseñar vistas ([Ejemplo de Vistas](http://tecnologiasweb.jsenso.es/wp-content/uploads/2015/06/full20.jpg))</li><li>Diseñar relaciones entre las vistas</li><li>Ejecutar el [Proceso de Arquitectura](https://github.com/CaveLabs-1/Wiki/blob/master/Arquitectura/Procesos/Proceso%20para%20definir%20arquitectura%20general.md) para definir el patrón de diseño a usarse y documentar el diagrama de despliegue</li></ul>| Encargado de Arquitectura  | TS
3 | Validación |<ul><li>Validar los diagramas y el flujo con el stakeholder</li></ul> | Product Owner  | TS
4 | Documetanción |<ul><li>Llenar [Flujo de Vistas](https://github.com/CaveLabs-1/Wiki/tree/master/Arquitectura/Formatos/Formato%20Ernie%20(Flujo%20de%20Vistas%20y%20Arquitectura%20Inicial).docx) y mantener los diagramas con el estándar UML</li><li>Documentar en Ernie las decisiones claves (es decir, efecto significativo sobre coste, calendario o rendimiento técnico) tomadas o definidas,incluyendo su análisis razonado.</li></ul>| Team Member  | TS
5 | Análisis de Métricas | Validar el tamaño definido de cada user stories según las vistas asignadas a él | Arch Owner | MA

## Plan de implementación

1. Publicar los documentos en su respectiva sección de la wiki y avisar a los miembros del equipo que está publicado por Slack
2. Presentar a los encargados de Arquitectura en flujo de los procesos correspondientes a esta área

## Bitácora

No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
---------------|--------|-------|----------|----------------
1.0 | Creación y Llenado de Documento | David Ramírez y Marco Luna | Mauricio Hernández | 2/2/2018
2.0 | Actualización según el nuevo proceso de proceso | David Ramírez | Ian Rosas | 5/3/2018
