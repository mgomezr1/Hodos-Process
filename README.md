# Hodós

**Visualizador de procesos en notación BPMN 2.0 con identificación de puntos de control**

Hodós (del griego ὁδός, «camino», raíz de la palabra «método») es una aplicación web para el análisis de eficiencia operativa. Permite construir un proceso a partir de formularios o de una plantilla de Excel, lo representa automáticamente como diagrama BPMN 2.0 y señala dónde deben ejecutarse controles duales y operativos para garantizar su ejecución efectiva.

## Acceso

La aplicación funciona directamente en el navegador, sin instalación ni servidor:

**https://mgomezr1.github.io/hodos/**

## Funcionalidades

* **Ingesta de datos por dos caminos.** Descarga de una plantilla de Excel para diligenciar y cargar, o construcción directa en formularios por pestañas. Los datos pueden exportarse de nuevo al formato de la plantilla.
* **Diagrama BPMN 2.0 en vivo.** Pool con carriles por rol o área, eventos de inicio, intermedio y fin, tareas con subtipo (usuario, manual, servicio), gateways exclusivo, paralelo e inclusivo, condiciones en los flujos y ciclos de reproceso.
* **Registro de controles.** Controles duales y operativos asociados a cada elemento, clasificados por naturaleza (preventivo, detectivo, correctivo) y forma de ejecución (manual, automática, semiautomática), con frecuencia, responsable y evidencia.
* **Validación de la notación.** Revisión de eventos de inicio y fin, elementos aislados o inalcanzables, gateways sin condiciones y referencias inconsistentes entre tablas.
* **Puntos de control sugeridos.** Reglas estructurales sobre actividades críticas, segregación de funciones, traspasos entre carriles y ciclos de reproceso.
* **Exportación.** Diagrama en SVG y PNG, y archivo BPMN 2.0 en XML con geometría, compatible con Camunda Modeler y bpmn.io.
* **Datos de prueba.** Un proceso ficticio de pago a proveedores, identificado claramente como tal, para explorar la herramienta.

## Estructura de la plantilla

| Hoja | Contenido |
|---|---|
| Instrucciones | Guía de uso y valores permitidos |
| Proceso | Nombre, dueño, versión y objetivo |
| Carriles | Roles o áreas que participan |
| Elementos | ID, tipo, nombre, carril, subtipo de tarea y criticidad |
| Flujos | Origen, destino y condición |
| Controles | ID, elemento, tipo, naturaleza, ejecución, frecuencia, responsable, descripción y evidencia |

## Reglas de sugerencia de controles

| Situación en el modelo | Control sugerido |
|---|---|
| Tarea crítica sin control dual | Dual preventivo |
| Dos tareas críticas consecutivas en el mismo carril | Dual preventivo (segregación de funciones) |
| Traspaso entre carriles hacia una tarea sin controles | Operativo preventivo (control de recepción) |
| Flujo que regresa a un paso anterior | Operativo detectivo (seguimiento del reproceso) |

## Tecnología

Un único archivo `index.html` con HTML5, CSS3 y JavaScript. Usa SheetJS desde CDN para leer y escribir Excel. No requiere servidor, base de datos ni instalación, y los datos no salen del navegador del usuario.

## Referencias

* Object Management Group. (2014). *Business Process Model and Notation (BPMN), versión 2.0.2*. OMG.
* Committee of Sponsoring Organizations of the Treadway Commission. (2013). *Marco Integrado de Control Interno*. COSO.

## Cómo citar

Si utilizas Hodós en trabajos académicos, cítalo así:

> Gómez Rueda, M. S., Mazo Duque, J.F (2026). *Hodós: visualizador de procesos en notación BPMN 2.0 con identificación de puntos de control* (Versión 1.0.0) [Software]. https://github.com/mgomezr1/hodos

GitHub también ofrece la cita en formato APA y BibTeX desde el botón **Cite this repository**, a partir del archivo `CITATION.cff`.

## Licencia

Uso académico. Cualquier otro uso se rige por las normas de propiedad intelectual. Consulta el archivo [LICENSE](LICENSE).

## Autor

**Mario Sergio Gómez-Rueda & Juan Felipe Mazo-Duque**
Sugerencias o inquietudes: mgomezr1@gmail.com
