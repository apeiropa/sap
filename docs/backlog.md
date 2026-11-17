# Backlog técnico inicial

Prioridad: P0 bloquea decisiones fundacionales; P1 habilita el primer flujo verificable; P2 amplía capacidades. “Implementable ahora” significa que puede trabajarse en el repositorio sin conexión a sistemas corporativos.

| ID | Prioridad | Trabajo | Resultado / aceptación | Estado |
|---|---|---|---|---|
| ASAP-01 | P0 | Establecer estructura, alcance, modelo de acceso, configuración de ejemplo y trazabilidad | Documentación revisable; sin secretos ni llamadas externas | Implementable ahora |
| ASAP-02 | P0 | Decidir runtime, lenguaje, modelo/proveedor y modo de despliegue | ADR aprobado que incluya operación, residencia de datos y límites de red | Decisión pendiente |
| ASAP-03 | P0 | Confirmar arquitectura de identidad, secretos, logging y retención con Seguridad | Matriz aprobada por sistema/entorno y procedimiento de auditoría | Depende de Seguridad |
| ASAP-04 | P0 | Confirmar accesos y APIs disponibles para Jira, Confluence y SAP | Inventario de endpoints, scopes, cuentas técnicas y restricciones por entorno | Depende de propietarios/accesos |
| ASAP-05 | P1 | Definir contratos de adaptador y pruebas con dobles | Interfaces versionadas para lectura; pruebas sin servicios reales | Implementable tras ASAP-02 |
| ASAP-06 | P1 | Crear flujo de lectura Jira → Confluence con referencias y fecha de consulta | Resumen reproduce clave, criterios, URL y versión; sin escritura | Depende de ASAP-02/04 |
| ASAP-07 | P1 | Crear plantilla de documentación funcional/técnica y enlaces a objetos SAP | Plantilla incluye alcance, objetos, pruebas, transporte, riesgos y trazabilidad | Implementable ahora |
| ASAP-08 | P1 | Preparar pipeline de calidad de repositorio | Formateo/lint, detección de secretos y validaciones acordadas en PR | Depende de stack y políticas de CI |
| ASAP-09 | P1 | Definir evaluación de respuestas y casos de regresión SAP | Dataset anonimizado, rúbrica y umbrales aprobados; pruebas reproducibles | Depende de Seguridad y ejemplos aprobados |
| ASAP-10 | P2 | Adaptador SAP de solo lectura para metadatos/documentación | Consultas limitadas, auditadas y probadas en entorno autorizado | Depende de APIs, red y accesos SAP |
| ASAP-11 | P2 | Publicar comentarios/enlaces en Jira y páginas Confluence | Escritura opt-in, revisión previa, autorización por usuario y auditoría | Depende de scopes y decisión operativa |
| ASAP-12 | P2 | Asistencia de desarrollo SAP con cambios propuestos en DEV y promoción gobernada | Propuestas en PR, evidencia QA y referencias de transporte; sin escritura PRD | Depende de políticas, herramientas y accesos |

## Secuencia sugerida

1. Revisar ASAP-01 y completar ASAP-02–04.
2. En paralelo, preparar ASAP-07 y diseñar ASAP-05 sin comprometer stack.
3. Implementar lectura y pruebas aisladas para ASAP-06/08/09 cuando haya decisiones y accesos.
4. Incorporar SAP de solo lectura antes de cualquier escritura.
5. Considerar escrituras únicamente con política explícita, aprobación operativa y auditoría probada.

Los IDs son locales a esta propuesta y no son issues Jira/GitHub. Convertirlos en tickets cuando el proyecto acuerde su herramienta y responsables.
