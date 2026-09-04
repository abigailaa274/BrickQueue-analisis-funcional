# BrickQueue: Seguimiento de Tickets

## Descripción:
Este proyecto presenta el análisis funcional de un sistema de gestión de bugs y oportunidades de mejora para reporte y seguimiento, destinado a equipos de producción de Software (y/o cualquier otro producto con un ciclo de vida similar, para el que se considere útil).

**Nota importante:** El proyecto busca ser una práctica de análisis funcional y no contiene un producto implementado.

## Alcances:
**Incluye:**
- Carga y seguimiento de tickets de bugs y oportunidades de mejora con prioridad, estado y descripción.
- Redacción de casos de prueba asociados a un ticket.
- Asignación y reasignación manual de tickets.
- Notificaciones automáticas por cambios de estado y vencimientos.
- Panel de reportes básico (tickets por estado, por responsable).

**No incluye:**
- Integración con repositorios de código (GitHub, GitLab) para vincular commits/PRs.
- Gestión de sprints o backlog.
- Autenticación/gestión de usuarios.

## Actores: 
- **Developer:**
    - **Como usuario solicitante:** crea tickets, asigna prioridad, redacta casos de prueba, hace seguimiento, responde consultas sobre el ticket, reabre tickets (cambia estado).
    - **Como usuario resolutor:** toma tickets, se comunica con el usuario solicitante, resuelve tickets (cambia estado), cierra el ticket.
    *Nota: las funciones de solicitante y resolutor corresponden a dos tareas que puede hacer un mismo usuario respecto a diferentes tickets, no a dos usuarios diferentes.*
- **Administrador/PM:** asigna y reasigna tickets, ve reportes y métricas.
- **Sistema (actor no humano):** dispara notificaciones automáticas y alertas de vencimiento de tickets.

## Estructura del repositorio:
- `/documentacion`
  - `requerimientos.md` — Requerimientos funcionales, no funcionales, de performance e infraestructura
  - `historias-de-usuario.md` — Historias de usuario con criterios de aceptación (Given/When/Then)
  - `reglas-de-negocio.md` — Reglas de negocio del sistema
  - `glosario-de-terminos.md` — Glosario de términos técnicos y del dominio
  - `listado-de-estados-ticket.md` — Estados y transiciones del ciclo de vida del ticket
- `/diagramas` — Diagramas UML y BPMN (en desarrollo)
- `/casos-de-prueba` — Casos de prueba (en desarrollo)

## Tecnologías/metodología usada:
- Documentación en Markdown
- Historias de usuario con criterios de aceptación en formato Given/When/Then (estilo BDD)
- Diagramas UML (casos de uso, estados) y BPMN
- Trazabilidad entre requerimientos de negocio, partes interesadas, funcionales e historias de usuario

## Índice
- [Requerimientos](./documentacion/requerimientos.md)
- [Historias de Usuario](./documentacion/historias-de-usuario.md)
- [Reglas de Negocio](./documentacion/reglas-de-negocio.md)
- [Glosario de Términos](./documentacion/glosario-de-terminos.md)
- [Estados y Transiciones del Ticket](./documentacion/listado-de-estados-ticket.md)

**Autora: Abigail Arias — Analista de sistemas. LinkedIn: www.linkedin.com/in/arias-abigail-aylen**

