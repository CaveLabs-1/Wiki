
# Proceso para levantamiento inicial de requerimientos
Versión 2.0.1


[]() | []()
---|---
Objetivo | Gestionar los requisitos y componentes de producto del proyecto, asegurando la alineación entre esos requisitos, planes y productos del proyecto.
Métricas utilizadas | Número de requerimientos modificados, agregados o eliminados a comparación de los requerimientos iniciales.
Criterios de entrada | <ul><li>Problemática (obtenida de junta con StakeHolders)</li> <li>Plantilla Matriz de trazabilidad</li></ul>
Definir políticas y estándares | <ul><li>La información derivada de los S.H. (Stake Holders) será obtenida por el Product Owner.</li> <li>Se deberá seguir la guia de juntas con clientes para obtener la información necesaria con la mayor eficiencia.</li> <li>Usar guía para Process Flow Diagram.</li> <li>Una vez definido el alcance inicial del proyecto, se obtiene compromiso de todos los involucrados (pt. 4 Jimmy) por medio de una firma.</li> <li>Tódo módulo de software, acceptance criteria o vista debe tener trazabilidad desde el código, es decir, el código debe estar documentado para encontrar fácilmente en la matriz de trazabilidad.</li> <li>Los documentos y formatos relacionados con este proceso se deben subir a la carpeta de 'Requerimientos/' de cada proyecto. </li> </ul>
Salidas del proceso | <ul><li>[Process flow diagram](https://www.lucidchart.com/pages/process-flow-diagrams)</li> <li>[Problematic context definition document (Timmy)](https://github.com/CaveLabs-1/Wiki/blob/master/Requerimientos/Formatos/Timmy%20(Contexto%20de%20la%20problem%C3%A1tica).docx)</li> <li>[Project definition document (Jimmy)](https://github.com/CaveLabs-1/Wiki/blob/master/Requerimientos/Formatos/Jimmy%20(Definici%C3%B3n%20de%20Proyecto).docx)</li>  <li>[Requirement traceability matrix](https://github.com/CaveLabs-1/Wiki/blob/master/Requerimientos/Formatos/Matriz%20de%20Trazabilidad.xlsx)</li></ul>
Criterios de salida | <ol><li>Tener una lista de requerimientos analizados y ordenados por prioridad y dependencia con criterios de aceptación.</li> <li>Entendimiento del alcance del proyecto y compromiso al mismo por parte de los involucrados reflejado por medio de el documento de definición de proyecto(Jimmy) y una firma de cada involucrado del proyeto.</li> </ul>

## Definición de Fases
No. de Fase | Fase | Actividades | Área de CMMI
------------|------|-------------|-----------
1 | Recopilación |<ul> <li>Definir internamente roles para la entrevista inicial con el cliente</li> <li>Llevar registro de la entrevista ya se por medio de una grabación o una minuta.</li> <li>Solicitar documentos útiles al S.H. (formas, plantillas, estándares de diseño, etc.)</li> <li>Identificar S.H. y registrar, con rol, en documento de definición del proyecto (pt. 2)</li>  </ul> | RD RM
2 | Análisis |<ul><li>Identificar y documentar mediante un Process Flow Diagram el proceso de la empresa sobre el que tendrá impacto el proyecto</li> <li>Identificar panorama de la problemática y documentarlo en el documento de contexto de la problemática(Llenar Timmy)</li></ul>| RM RD
3 | Definición |<ul><li>Documentar,  en documento de definición de proyecto(pt 4), una propuesta de solución general acorde a la problemática(definida en el documento de contexto de problemática).</li></ul>| RM
4 | Identificación |<ul><li>A partir de la propuesta de solución, identificar los requerimientos funcionales del proyecto.</li> <li>Documentar requerimientos en matriz de trazabilidad(Sólo nombre)</li></ul>| RM RD
5 | Limitación | <ul><li>Se estima un tamaño estimado del proyecto según estipulado en el proceso de planning</li> <li>Se obtiene un tiempo estimado de desarrollo del proyecto y se documenta según el proceso de planeación.</li> <li>Acorde a la estimación de tamaño y tiempo obtenida del proceso de planeación, se realiza una acotación según el tiempo en horas/hombre disponibles de la empresa y la fecha de entrega estipulada.</li> <li>Actualizar matriz de trazabilidad(sólo nombres)</li></ul>| PP RM
6 | Clasificación |<ul><li>Identificar las características de cada requerimiento(Dependencias, módulos de software, estatus y versión ) y documentar en matriz de trazabilidad.</li> </ul>| RM
7 | Validación |<ul><li>Se valida Jimmy y lista de requerimientos con el cliente, firma de acuerdo de stakeholder principal y product owner</li></ul>| PPQA

## Plan de implementación
<li>Subir la documentación al portal oficial de información.</li>
<li>Asegurarse de seguir el proceso y políticas de entrevista a stakeholders.</li>

## Bitácora
No. de Versión | Cambio | Autor | Aprobado | Fecha de cambio
---------------|--------|-------|----------|----------------
1.0 | Creación de proceso | Alejandro Salmon | Mauricio Hernández| 29/ene/2018
1.1 |Plan de Implementación Complemento de la fase de análisis | Mauricio Hernández | Valter Nuñez | 1/feb/2018
2.0 | Implementación par acumplir con CMMI 2 y agregado de fase de recopilación y limitación | Alejandro Salmón | Mauricio Hernández | 19/mar/018
2.0.1 | Errores en links | Ian Romero |  | 2/abril/2018
