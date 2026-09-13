# Reglas de Negocio

| Código | Regla |
|---|---|
| RG-01 | Un ticket no puede pasar a estado "En progreso" o "Cerrado" sin tener un Developer resolutor asignado. |
| RG-02 | Solo el PM puede asignar o reasignar el Developer resolutor de un ticket. |
| RG-03 | El Developer resolutor solo puede avanzar el estado de los tickets que tiene asignados a él mismo. En caso de haber más de un resolutor asignado, cualquiera de ellos puede avanzar el estado del ticket. |
| RG-04 | Un ticket en estado "Cerrado" puede ser reabierto por cualquiera de los tres roles: Developer solicitante, Developer resolutor o PM. |
| RG-05 | Un ticket puede tener más de un Developer resolutor asignado a la vez. |
| RG-06 | Un ticket puede no tener fecha de vencimiento asignada. Si no la tiene, el sistema no genera ninguna notificación de vencimiento para ese ticket. |
| RG-07 | Solo el Developer solicitante que creó un ticket puede modificar los siguientes datos: título, descripción, tipo. |
| RG-08 | Tanto el Developer solicitante que creó un ticket, el PM y el Developer resolutor pueden modificar los siguientes datos: prioridad, fecha de vencimiento. |
| RG-09 | El tipo de un ticket puede ser únicamente "bug" o "mejora". |
| RG-10 | Todo ticket se crea automáticamente en estado "Nuevo", sin posibilidad de que el solicitante elija otro estado inicial. |
| RG-11 | Las notificaciones automáticas del sistema deben enviarse dentro de un plazo máximo de 1 minuto desde el evento que las origina. |
| RG-12 | El título de un ticket debe ser único dentro del sistema; no puede haber dos tickets con el mismo título. |
| RG-13 | Un ticket en estado "Reabierto" pasa a estado "Asignado" cuando el PM le asigna (o reasigna) un Developer resolutor. |
