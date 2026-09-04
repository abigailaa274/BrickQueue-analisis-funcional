# Historias de Usuario (HU):

## HU-01 (RF-01)
> **Como** Developer solicitante, **quiero** crear un ticket especificando título, tipo, descripción y prioridad, **para** reportar un bug o mejora de forma clara y que el equipo pueda priorizarlo correctamente.

**Escenario 1: Creación exitosa**
- **Given** que soy un Developer solicitante autenticado
- **When** completo título y tipo (obligatorios), y opcionalmente descripción y prioridad, y confirmo la creación
- **Then** el ticket se guarda en estado "Nuevo" y queda visible para el resto del equipo.

**Escenario 2: Falta un campo obligatorio**
- **Given** que soy un Developer solicitante creando un ticket
- **When** intento guardar sin completar el título o el tipo
- **Then** el sistema no guarda el ticket y muestra un mensaje de error indicando el campo faltante.

**Escenario 3: El nombre elegido ya está en uso**
- **Given** que soy un Developer solicitante creando un ticket
- **When** intento guardar un ticket con un nombre con que ya se guardó otro previamente
- **Then** el sistema no guarda el ticket y muestra un mensaje de error indicando el campo repetido.
---

## HU-02 (RF-02)
> **Como** Developer solicitante, **quiero** modificar los datos de los tickets que yo creé, **para** corregir o completar información luego de crearlos.

**Escenario 1: Edición exitosa**
- **Given** que soy el Developer solicitante que creó un ticket
- **When** modifico título, descripción, tipo o prioridad y confirmo los cambios
- **Then** el sistema guarda los cambios y refleja la información actualizada.

**Escenario 2: Intento de editar un ticket ajeno**
- **Given** que soy un Developer solicitante
- **When** intento modificar un ticket creado por otro solicitante
- **Then** el sistema no permite la edición.

**Escenario 3: Intento de editar el nombre de un ticket por otro ya en uso**
- **Given** ue soy el Developer solicitante que creó un ticket
- **When** intento modificar el nombre del ticket dejando como nuevo nombre uno que ya corresponde a otro ticket
- **Then** el sistema no permite la edición.

---

## HU-03 (RF-03)
> **Como** miembro del equipo (Developer o PM), **quiero** ver el listado de tickets existentes, **para** tener visibilidad del estado general del trabajo y evitar duplicar reportes.

**Escenario 1: Visualización del listado**
- **Given** que soy un usuario del sistema (Developer o PM)
- **When** accedo al listado de tickets
- **Then** puedo ver todos los tickets existentes con su título, estado, tipo y prioridad

---

## HU-04 (RF-04)
> **Como** PM, **quiero** asignar uno o más Developers resolutores a un ticket, **para** definir quién es responsable de resolverlo.

**Escenario 1: Asignación exitosa**
- **Given** que soy PM y existe un ticket sin resolutor asignado
- **When** selecciono un Developer resolutor para ese ticket
- **Then** el ticket queda asignado a ese Developer y cambia su estado a "Asignado".

---

## HU-05 (RF-05)
> **Como** PM, **quiero** cambiar la asignación de un ticket a otro u otros Developers o dejarlo sin asignar, **para** reorganizar la carga de trabajo del equipo.

**Escenario 1: Reasignación**
- **Given** que soy PM y un ticket ya tiene un Developer resolutor asignado
- **When** selecciono otro Developer resolutor para ese ticket
- **Then** el ticket queda reasignado al nuevo Developer.

**Escenario 2: Quitar asignación**
- **Given** que soy PM y un ticket tiene un resolutor asignado
- **When** quito la asignación
- **Then** el ticket queda sin resolutor, disponible para ser asignado nuevamente.

---

## HU-06 (RF-06)
> **Como** Developer resolutor, **quiero** recibir una notificación cuando se me asigna un nuevo ticket, **para** enterarme y comenzar a trabajar en él sin demoras.

**Escenario 1: Notificación por asignación**
- **Given** que un ticket es asignado a un Developer resolutor
- **When** se confirma la asignación
- **Then** el sistema envía una notificación automática a ese Developer dentro del minuto siguiente al evento.

---

## ## HU-07 (RF-07)
> **Como** Developer resolutor, **quiero** avanzar el estado de un ticket asignado a medida que trabajo en él, **para** reflejar el progreso real y comunicar cuándo quedó resuelto.

**Escenario 1: Avance normal de estado**
- **Given** que soy el Developer resolutor asignado a un ticket en estado "Asignado"
- **When** actualizo su estado (Asignado → En progreso → Cerrado)
- **Then** el sistema guarda el nuevo estado y lo refleja en el listado.
---

## HU-08 (RF-08)
> **Como** PM o Developer (solicitante o resolutor), **quiero** asignar una fecha de vencimiento a un ticket, **para** establecer un plazo de resolución esperado.

**Escenario 1: Asignación de fecha de vencimiento**
- **Given** que soy PM o Developer con acceso a un ticket
- **When** defino una fecha de vencimiento para ese ticket
- **Then** el sistema guarda la fecha y la muestra junto al resto de la información del ticket.

---

## HU-09 (RF-09)
> **Como** Developer (solicitante o resolutor), **quiero** dejar mensajes o preguntas asociadas a un ticket, **para** comunicarme con el resto del equipo de forma centralizada.

**Escenario 1: Publicar un mensaje**
- **Given** que soy un Developer con acceso a un ticket
- **When** escribo un mensaje o pregunta y lo envío
- **Then** el sistema lo guarda asociado al ticket y queda visible para el resto del equipo.

---

## HU-10 (RF-10)
> **Como** Developer solicitante, **quiero** recibir una notificación cuando un ticket que creé se cierra, **para** enterarme de que mi reporte fue resuelto.

**Escenario 1: Notificación por cierre**
- **Given** que un ticket creado por un Developer solicitante cambia a estado "Cerrado"
- **When** se confirma el cambio de estado
- **Then** el sistema notifica automáticamente al Developer solicitante dentro del minuto siguiente.

---

## HU-11 (RF-11)
> **Como** PM o Developer resolutor, **quiero** recibir una notificación cuando un ticket llega a su fecha de vencimiento, **para** tomar acción antes de que se acumule el atraso.

**Escenario 1: Vencimiento con fecha definida**
- **Given** que un ticket tiene una fecha de vencimiento definida
- **When** el sistema detecta que se alcanzó esa fecha sin que el ticket esté cerrado
- **Then** se notifica automáticamente al PM y al Developer resolutor asignado.

**Escenario 2: Ticket sin fecha de vencimiento**
- **Given** que un ticket no tiene fecha de vencimiento definida
- **When** pasa el tiempo
- **Then** el sistema no genera ninguna notificación de vencimiento para ese ticket.

---

## HU-12 (RF-12)
> **Como** PM, **quiero** ver un panel de reportes con la cantidad de tickets por estado y por responsable, **para** tomar decisiones informadas sobre la carga y prioridades del equipo.

**Escenario 1: Visualización del panel**
- **Given** que soy PM
- **When** accedo al panel de reportes
- **Then** puedo ver la cantidad de tickets agrupados por estado y por Developer resolutor.

---

## HU-13 (RF-13)
> **Como** Developer solicitante, Developer resolutor o PM, **quiero** reabrir un ticket que está en estado "Cerrado", **para** indicar que el problema persiste o la solución no fue suficiente.

**Escenario 1: Reapertura de un ticket cerrado**
- **Given** que un ticket está en estado "Cerrado" y soy Developer solicitante, Developer resolutor o PM
- **When** cambio su estado a "Reabierto"
- **Then** el ticket vuelve a estar activo y visible para su seguimiento.