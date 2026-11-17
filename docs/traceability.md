# Trazabilidad Jira–Confluence–SAP–Git

## Identificadores que debe conservar cada cambio

| Sistema | Referencia mínima |
|---|---|
| Jira | Clave del issue, versión/revisión consultada y criterios de aceptación aplicables |
| Confluence | URL de la página funcional/técnica, versión o fecha de revisión y propietario |
| Git | Rama, commit y pull request que contienen la propuesta |
| SAP | Sistema/entorno, tipo y nombre del objeto, paquete cuando aplique, transporte y estado |
| Pruebas | Entorno, fecha, caso, resultado y evidencia autorizada |

## Regla de enlace

Un cambio implementable debe poder recorrerse en ambos sentidos:

`Jira issue → Confluence funcional/técnica → PR/commit → objeto SAP/transporte → evidencia de prueba`

Si un eslabón todavía no existe, anotarlo como pendiente; no inventar identificadores ni declarar el cambio completado.

## Flujo de trabajo

1. Leer el issue y confirmar alcance y criterios de aceptación.
2. Localizar la documentación Confluence relacionada. Si no existe o está desactualizada, registrarlo como dependencia.
3. Documentar análisis, objetos SAP afectados, riesgos y plan de pruebas en el issue o en una página enlazada.
4. Proponer cambios en una rama y abrir un PR referenciando la clave Jira.
5. Tras revisión y pruebas, registrar los objetos y números de transporte por entorno.
6. Adjuntar o enlazar evidencia sin incluir datos sensibles.
7. Actualizar Jira/Confluence con el resultado final, links a Git y estado de SAP conforme a los permisos aprobados.

## Convención para Git

- Rama: `feature/<JIRA-KEY>-<slug>`, `fix/<JIRA-KEY>-<slug>` o `docs/<slug>`.
- Commit: incluir `<JIRA-KEY>` cuando exista un issue asociado.
- PR: título con la clave Jira y resumen; plantilla con pruebas, objetos SAP y transportes.
- Una tarea exploratoria sin Jira debe indicarse como tal y solicitar issue antes de iniciar cambios funcionales.

## Condiciones de integridad

- Jira es la referencia de alcance y aceptación; Confluence, de documentación; SAP, del estado técnico desplegado.
- Un commit o PR no demuestra por sí solo que el transporte se haya importado.
- Un transporte creado no demuestra por sí solo que las pruebas se hayan superado.
- Las discrepancias entre issue, documentación, Git y SAP deben quedar como incidencia abierta.
- No copiar credenciales, datos personales, facturas ni contenido de negocio al historial de Git.
