# Requerimientos

## Requerimientos de negocio (RN):

| Código | Descripción | Objetivo/Justificación |
|-----------|-----------|-----------------------|
| RN-01 | La empresa requiere un sistema para centralizar la administración de tickets | Reducir dispersión de comunicación y acelerar el proceso de resolución |
| RN-02 | Los PMs requieren un medio para asignar y dar seguimiento a los tickets | Mejora en administración del tiempo y recursos humanos |
| RN-03 | Los developers como resolutores requieren un sistema centralizado donde encontrar los tickets asignados | Reducir la dispersión y pérdida de información sobre tickets y agilizar la comunicación con developers solicitantes |
| RN-04 | Los developers como solicitantes requieren un sistema donde comunicarse con los developers como resolutores de forma centralizada respecto a los tickets | Mejorar la comunicación entre roles y reducir malentendidos que retrasan la resolución de tickets |

## Requerimientos de partes interesadas (RPI):

| Código | Actor | Necesidad |
|--------|-------|-----------|
| RPI-01 | Developer como solicitante | Requiere visibilidad sobre los tickets ya creados para evitar crear duplicados |
| RPI-02 | Developer como resolutor | Requiere notificaciones para enterarse cuando se le asigna un nuevo ticket |
| RPI-03 | PM | Requiere visibilidad de las fechas de vencimiento de tickets para asignarles resolutores |
| RPI-04 | PM | Requiere visibilidad de métricas para toma de decisiones |

## Requerimientos funcionales (RF):

| Código | Descripción | Actor(es) | Requerimiento(s) de negocio relacionado(s) |
|---|---|---|---|
| RF-01 | El sistema debe permitir al developer solicitante crear tickets con título (obligatorio y único dentro del sistema), descripción (optativo), tipo (bug/mejora obligatorio) y prioridad (optativo) | Developer solicitante | RN-01, RN-04 |
| RF-02 | El sistema debe permitir al developer solicitante modificar los datos de los tickets que creó (título, descripción, tipo (bug/mejora) y prioridad), validando que el nuevo título, si se modifica, no coincida con el de otro ticket existente | Developer solicitante | RN-01, RN-04 |
| RF-03 | El sistema debe permitir a todos los usuarios ver los tickets ya existentes | Developer, PM | RN-01, RN-03, RN-04 |
| RF-04 | El sistema debe permitir al PM asignar uno o más Developers (resolutores) a un ticket | PM | RN-02 |
| RF-05 | El sistema debe permitir al PM cambiar la asignación de un ticket quitando o añadiendo Developers asignados, o dejar un ticket sin asignación | PM | RN-02 |
| RF-06 | El sistema debe enviar notificaciones al Developer resolutor cuando se le asigne un nuevo ticket | Sistema, Developer como resolutor | RN-02, RN-03 |
| RF-07 | El sistema debe permitir al Developer resolutor cambiar el estado de un ticket a lo largo de las ultimas etapas de su ciclo de vida normal (En progreso → Cerrado. Las anteriores, Nuevo y Asignado, corresponden a otras funciones) | Developer resolutor | RN-02, RN-03 |
| RF-08 | El sistema debe permitir a cualquier miembro del equipo asignar fechas de vencimiento a los tickets | PM, Developer (como solicitante o como resolutor) | RN-02 |
| RF-09 | El sistema debe permitir guardar mensajes/preguntas de los developers como solicitantes o como resolutores para el resto del equipo | Sistema, Developer (como solicitante o como resolutor) | RN-03, RN-04 |
| RF-10 | El sistema debe enviar notificaciones al developer solicitante cuando un ticket creado por él pase a estado cerrado | Developer solicitante, Sistema | RN-01, RN-04 |
| RF-11 | El sistema debe enviar notificación al PM y al developer resolutor asignado a un ticket cuando el ticket llegue a su fecha de vencimiento (solo si tiene fecha de vencimiento) | PM, Developer como resolutor, Sistema | RN-02 |
| RF-12 | El sistema debe mostrar un panel de reportes con la cantidad de tickets por estado y por responsable (Developer resolutor) | PM | RN-02 |
| RF-13 | El sistema debe permitir a cualquier miembro del equipo (Developer solicitante, Developer resolutor o PM) reabrir un ticket que se encuentre en estado "Cerrado" | Developer solicitante, Developer resolutor, PM | RN-01, RN-02, RN-03, RN-04 |

## Requerimientos no funcionales (RNF):

| Código | Descripción | Categoría |
|---|---|---|
| RNF-01 | El sistema debe mostrar el listado de tickets en menos de 3 segundos, con hasta 1000 tickets cargados. | Rendimiento |
| RNF-02 | El sistema debe restringir las acciones de asignación y reasignación de tickets exclusivamente al rol PM. | Seguridad |
| RNF-03 | El sistema debe estar disponible al menos el 99% del tiempo en horario laboral, permitiendo ventanas de mantenimiento programado fuera de ese horario. | Disponibilidad |
| RNF-04 | La creación de un ticket no debe requerir más de 2 campos obligatorios (titulo y tipo), para minimizar la fricción al reportar un bug o mejora. | Usabilidad |
| RNF-05 | El sistema debe soportar al menos 50 usuarios concurrentes sin degradación perceptible del rendimiento. | Escalabilidad |
| RNF-06 | Las notificaciones automáticas (asignación, cambio de estado, vencimiento) deben enviarse dentro de un plazo máximo de 1 minuto desde el evento que las origina. | Rendimiento |
| RNF-07 | El sistema debe registrar un historial de cambios de estado de cada ticket, para trazabilidad y auditoría. | Seguridad |