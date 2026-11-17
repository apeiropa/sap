# agentic-sap

Base documental y técnica para construir un asistente de ingeniería SAP con trazabilidad entre requisitos Jira, documentación Confluence y cambios en SAP/Git.

## Estado

El repositorio parte de una base vacía. Este primer cambio define la estructura y las reglas de trabajo; todavía no implementa conectores ni ejecuta acciones contra Jira, Confluence o SAP.

## Principios

- Jira conserva el requisito y los criterios de aceptación.
- Confluence conserva la documentación funcional y técnica aprobada.
- Git conserva prompts, configuración no sensible, código auxiliar y cambios revisables.
- SAP conserva los objetos y transportes; cada cambio debe referenciar sus identificadores.
- Acceso mínimo por entorno: desarrollo con permisos expresos, calidad para pruebas y producción en solo lectura.
- No guardar secretos, datos personales ni volcados de negocio en el repositorio.

## Estructura propuesta

```text
.
├── config/
│   └── integrations.example.yaml
├── docs/
│   ├── access-model.md
│   ├── architecture.md
│   ├── backlog.md
│   ├── traceability.md
│   └── decisions/
│       └── README.md
└── .github/
    └── pull_request_template.md
```

La estructura separa documentación y configuración de ejemplo. Los conectores, servicios y pruebas se añadirán cuando se decidan tecnología, despliegue y accesos.

## Primeros pasos

1. Revisar y aprobar el alcance y el modelo de acceso de [docs/access-model.md](docs/access-model.md).
2. Resolver las decisiones P0 de [docs/backlog.md](docs/backlog.md).
3. Registrar cada decisión técnica en [docs/decisions/README.md](docs/decisions/README.md).
4. Implementar primero lectura y trazabilidad, con datos de prueba y sin escrituras en sistemas.
5. Incorporar conectores únicamente tras validar permisos, autenticación, auditoría y tratamiento de datos.

## Documentación

- [Arquitectura y componentes](docs/architecture.md)
- [Trazabilidad Jira–Confluence–SAP–Git](docs/traceability.md)
- [Accesos y seguridad](docs/access-model.md)
- [Backlog técnico priorizado](docs/backlog.md)
- [Registro de decisiones (ADR)](docs/decisions/README.md)
- [Ejemplo de configuración](config/integrations.example.yaml)
