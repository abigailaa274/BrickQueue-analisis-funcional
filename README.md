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
    - **Como usuario resolutor:** toma tickets, se comunica con el usuario solicitante, resuelve y/o reabre tickets (cambia estado).
*Nota: las funciones de solicitante y resolutor corresponden a dos tareas que puede hacer un mismo usuario respecto a diferentes tickets, no a dos usuarios diferentes. Ademas un mismo Developer puede crear un ticket y despues ser asignado para resolverlo, es decir, ser solicitante y resolutor del mismo ticket*
- **Administrador/PM:** asigna y reasigna tickets, ve reportes y métricas, reabre tickets (cambia estado).
- **Sistema (actor no humano):** dispara notificaciones automáticas y alertas de vencimiento de tickets.

## Estructura del repositorio: 
ver después.

## Tecnologías/metodología usada:
queda para después

## Índice o links a cada documento 
queda para después.


**Autora: Abigail Arias — Analista de sistemas. LinkedIn: www.linkedin.com/in/arias-abigail-aylen**

