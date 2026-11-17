# Arquitectura inicial

## Objetivo

Proponer límites entre componentes antes de elegir una implementación. No se presupone un framework, proveedor de modelos ni método de despliegue.

## Componentes

| Componente | Responsabilidad inicial | Estado |
|---|---|---|
| Interfaz de trabajo | Recibir la tarea, mostrar fuentes, pedir confirmación para acciones con efecto y presentar resultados | Pendiente de decisión de canal |
| Orquestador | Descomponer la tarea, aplicar políticas, invocar herramientas permitidas y conservar referencias | Diseño |
| Contexto y búsqueda | Recuperar requisitos Jira, páginas Confluence y referencias técnicas autorizadas | Depende de accesos y APIs |
| Adaptador Jira | Lectura inicial de issues, comentarios y enlaces; escritura solo en acciones expresamente autorizadas | Bloqueado por acceso y alcance de escritura |
| Adaptador Confluence | Lectura de documentación autorizada; creación/actualización documental solo con flujo aprobado | Bloqueado por acceso y decisión |
| Adaptador SAP | Consultas de metadatos y objetos según rol; operaciones de desarrollo o ejecución segregadas por entorno | Bloqueado por conexión, API y permisos |
| Gestión de conocimiento | Mantener prompts, plantillas, decisiones y referencias con versión y propietario | Puede empezar con documentación del repositorio |
| Política y autorización | Aplicar acceso mínimo, separación DEV/QA/PRD y confirmación de cambios externos | Diseño; requiere validación de seguridad |
| Auditoría y evaluación | Registrar actor, tarea, fuentes, herramientas, resultado, errores y evaluación sin secretos | Requisitos definidos; implementación pendiente |

## Flujo previsto

1. La tarea se asocia a un identificador Jira o se marca como análisis exploratorio.
2. El orquestador carga criterios y documentación autorizada, registrando sus enlaces y versiones.
3. La respuesta o propuesta cita requisitos, páginas y objetos SAP consultados.
4. Toda modificación se prepara como propuesta revisable y se registra en Git/Jira/Confluence según permisos.
5. Las acciones sobre sistemas SAP respetan el entorno y el rol; producción permanece de solo lectura.

## Carpetas futuras cuando exista decisión de implementación

No crear módulos vacíos hasta seleccionar lenguaje y runtime. Como destino de referencia:

```text
src/
  api/                 # interfaz de entrada
  orchestration/       # flujo, políticas y manejo de contexto
  adapters/
    jira/
    confluence/
    sap/
  security/            # autorización y gestión de secretos vía proveedor externo
  observability/       # auditoría y métricas
tests/
  unit/
  contract/
  evals/
```

Los nombres son una propuesta, no una estructura impuesta. Los contratos de adaptador deben probarse con dobles o entornos de prueba antes de conectarse a sistemas reales.
