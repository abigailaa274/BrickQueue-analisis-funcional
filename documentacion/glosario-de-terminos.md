# Glosario de Términos

**Ticket:** unidad básica de trabajo del sistema. Representa un bug o una oportunidad de mejora reportada, con datos como título, descripción, tipo, prioridad, estado y fecha de vencimiento (opcional).

**Bug:** tipo de ticket que reporta un error o comportamiento no esperado en el producto.

**Mejora (oportunidad de mejora):** tipo de ticket que propone un cambio o incorporación que no corrige un error, sino que optimiza o amplía una funcionalidad existente.

**Developer:** rol genérico que puede actuar como solicitante o como resolutor, según el ticket. No son dos usuarios distintos, sino dos funciones que puede cumplir la misma persona.

**Developer solicitante:** rol que cumple un Developer al crear un ticket y hacer seguimiento del mismo hasta su resolución.

**Developer resolutor:** rol que cumple un Developer al ser asignado a un ticket y trabajar en su resolución.

**PM (Product Manager / Administrador):** rol responsable de asignar y reasignar tickets a Developers resolutores, visualizar métricas y hacer seguimiento general del trabajo del equipo.

**Sistema:** actor no humano que ejecuta acciones automáticas, como el envío de notificaciones ante eventos definidos (asignación, cierre, vencimiento).

**Estado del ticket:** valor que indica en qué punto del ciclo de vida se encuentra un ticket. Ver estados definidos abajo.

**Nuevo:** estado inicial de un ticket, asignado automáticamente al momento de su creación, antes de tener un Developer resolutor asignado.

**Asignado:** estado de un ticket una vez que el PM le asignó un Developer resolutor.

**En progreso:** estado de un ticket cuando el Developer resolutor asignado comenzó a trabajar activamente en su resolución.

**Cerrado:** estado final de un ticket cuando el Developer resolutor considera que fue resuelto.

**Reabierto:** estado de un ticket previamente cerrado, cuando se determina que el problema persiste o la solución no fue suficiente. Puede reabrirlo cualquiera de los tres roles (Developer solicitante, Developer resolutor o PM).

**Prioridad:** nivel de urgencia asignado a un ticket, utilizado para definir el orden en que debería atenderse.

**Fecha de vencimiento:** fecha límite opcional asignada a un ticket, utilizada para definir un plazo esperado de resolución. Si se alcanza sin que el ticket esté cerrado, dispara una notificación automática.

**Notificación:** aviso automático enviado por el Sistema ante determinados eventos (asignación de ticket, cierre de ticket, vencimiento de fecha límite).

**Panel de reportes:** vista destinada al PM que muestra métricas agregadas, como cantidad de tickets por estado y por Developer resolutor.

**Mensaje/comentario:** texto asociado a un ticket, publicado por un Developer (solicitante o resolutor), utilizado para comunicación centralizada del equipo respecto a ese ticket.

**RF (Requerimiento Funcional):** especificación de una acción o comportamiento concreto que el sistema debe cumplir.

**RNF (Requerimiento No Funcional):** especificación de una condición o cualidad que el sistema debe cumplir (rendimiento, seguridad, disponibilidad, etc.), sin describir una funcionalidad puntual.

**RN (Requerimiento de Negocio):** necesidad expresada a nivel organización/proyecto que justifica la existencia del sistema.

**RPI (Requerimiento de Partes Interesadas):** necesidad general de un actor específico, más concreta que un RN pero sin bajar al detalle de una funcionalidad del sistema.

**HU (Historia de Usuario):** descripción de una funcionalidad desde la perspectiva de un actor, en formato "Como... quiero... para...", con criterios de aceptación asociados.

**Título (de un ticket):** nombre identificador de un ticket, obligatorio y único dentro del sistema. No puede haber dos tickets con el mismo título.