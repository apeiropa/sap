# Accesos y seguridad

## Modelo inicial propuesto

| Entorno / servicio | Acceso propuesto | Uso |
|---|---|---|
| SAP Desarrollo | Lectura y escritura solo para actividades autorizadas y con trazabilidad | Análisis y desarrollo supervisado |
| SAP Calidad | Ejecución de pruebas y consulta | Validación documentada |
| SAP Producción | Solo lectura | Diagnóstico y documentación |
| Jira | Lectura; escritura de comentarios o campos autorizados únicamente por instrucción explícita | Requisitos y seguimiento |
| Confluence | Lectura; escritura en páginas aprobadas cuando se solicite | Documentación funcional/técnica |
| Git | Ramas y PR; cambios revisables | Versionado y revisión |

Este cuadro describe el objetivo de diseño. No confirma que existan conexiones, credenciales ni permisos operativos.

## Controles necesarios antes de conectar sistemas

- Identidad técnica diferenciada por entorno y permisos mínimos.
- Autenticación mediante el gestor de secretos aprobado; nunca incluir tokens en YAML, código, issues o commits.
- Registro de identidad, acción, sistema, entorno, timestamp, resultado y referencias consultadas.
- Separación de lectura y escritura; escrituras desactivadas por defecto.
- Confirmación explícita antes de cambios en Jira, Confluence o SAP.
- Prohibición de ejecución o escritura en producción.
- Redacción de secretos y datos personales en logs; retención definida por seguridad.
- Revisión de permisos, auditoría y recuperación antes de piloto.

## Acciones no habilitadas en esta base

No se ha implementado autenticación, integración ni operación en Jira, Confluence o SAP. No se conceden permisos ni se crean credenciales desde este repositorio. Los permisos concretos, usuarios técnicos y controles deben validarse con los responsables de cada plataforma y seguridad.
