# Casos de Prueba

## CP-01 (HU-01 / RF-01 / RG-12) — Crear ticket exitosamente
**Precondición:** Estoy autenticado como Developer solicitante.
**Pasos:**
1. Accedo a la opción "Crear ticket".
2. Completo título ("Error en login") y tipo ("bug").
3. Dejo descripción y prioridad vacíos.
4. Confirmo la creación.
**Resultado esperado:** El ticket se crea en estado "Nuevo" y queda visible en el listado general.

## CP-02 (HU-01 / RF-01) — Intentar crear ticket sin título
**Precondición:** Estoy autenticado como Developer solicitante.
**Pasos:**
1. Accedo a "Crear ticket".
2. Dejo el título vacío, completo el tipo ("bug").
3. Confirmo la creación.
**Resultado esperado:** El sistema no guarda el ticket y muestra un error indicando que el título es obligatorio.

## CP-03 (HU-01 / RF-01) — Intentar crear ticket sin tipo
**Precondición:** Estoy autenticado como Developer solicitante.
**Pasos:**
1. Accedo a "Crear ticket".
2. Completo el título, dejo el tipo vacío.
3. Confirmo la creación.
**Resultado esperado:** El sistema no guarda el ticket y muestra un error indicando que el tipo es obligatorio.

## CP-04 (HU-01 / RG-09) — Intentar crear ticket con un tipo inválido
**Precondición:** Estoy autenticado como Developer solicitante.
**Pasos:**
1. Accedo a "Crear ticket".
2. Completo título y tipo con un valor distinto de "bug" o "mejora" (ej: "consulta").
3. Confirmo la creación.
**Resultado esperado:** El sistema no guarda el ticket y muestra un error indicando que el tipo no es válido.

## CP-05 (HU-01, Escenario 3 / RG-12) — Intentar crear ticket con título duplicado
**Precondición:** Ya existe un ticket con título "Error en login".
**Pasos:**
1. Accedo a "Crear ticket".
2. Completo el título con "Error en login" (idéntico a uno ya existente) y un tipo válido.
3. Confirmo la creación.
**Resultado esperado:** El sistema no guarda el ticket y muestra un error indicando que el título ya está en uso.

## CP-06 (HU-01) — Ticket queda en estado "Nuevo" al crearse (RG-10)
**Precondición:** Estoy autenticado como Developer solicitante.
**Pasos:**
1. Creo un ticket válido.
2. Reviso el estado del ticket recién creado.
**Resultado esperado:** El estado es "Nuevo", sin posibilidad de elegir otro estado inicial.

## CP-07 (HU-02 / RF-02 / RG-07) — Modificar ticket propio exitosamente
**Precondición:** Soy el Developer solicitante que creó el ticket X.
**Pasos:**
1. Accedo al ticket X.
2. Modifico la descripción y el tipo.
3. Confirmo los cambios.
**Resultado esperado:** Los cambios se guardan y se reflejan al visualizar el ticket.

## CP-08 (HU-02, Escenario 2 / RG-07) — Intentar editar un ticket ajeno
**Precondición:** Existe un ticket creado por otro Developer solicitante.
**Pasos:**
1. Intento acceder a la edición de ese ticket.
**Resultado esperado:** El sistema no permite la edición.

## CP-09 (HU-02, Escenario 3 / RG-12) — Intentar modificar el título a uno ya existente
**Precondición:** Soy el Developer solicitante que creó el ticket X. Existe otro ticket con título "Error en login".
**Pasos:**
1. Edito el ticket X.
2. Cambio su título a "Error en login".
3. Confirmo los cambios.
**Resultado esperado:** El sistema no permite la edición y muestra un error de título duplicado.

## CP-10 (HU-03 / RF-03) — Ver listado de tickets
**Precondición:** Estoy autenticado como Developer o PM.
**Pasos:**
1. Accedo al listado de tickets.
**Resultado esperado:** Se muestran todos los tickets existentes, con título, estado, tipo y prioridad.

## CP-11 (HU-04 / RF-04) — Asignar un resolutor a un ticket sin asignar
**Precondición:** Soy PM. Existe un ticket en estado "Nuevo", sin resolutor asignado.
**Pasos:**
1. Accedo al ticket.
2. Selecciono un Developer resolutor.
3. Confirmo la asignación.
**Resultado esperado:** El ticket queda asignado a ese Developer y su estado cambia a "Asignado".

## CP-12 (HU-04 / RG-05) — Asignar más de un resolutor a un ticket
**Precondición:** Soy PM. Existe un ticket sin resolutor asignado.
**Pasos:**
1. Accedo al ticket.
2. Selecciono dos Developers resolutores.
3. Confirmo la asignación.
**Resultado esperado:** El ticket queda asignado a ambos Developers simultáneamente.

## CP-13 (HU-05, Escenario 1 / RF-05) — Agregar un resolutor adicional a un ticket ya asignado
**Precondición:** Soy PM. El ticket X ya tiene un Developer resolutor asignado.
**Pasos:**
1. Accedo al ticket X.
2. Agrego un segundo Developer resolutor.
**Resultado esperado:** El ticket queda con ambos resolutores asignados.

## CP-14 (HU-05, Escenario 2 / RF-05) — Quitar asignación de un ticket
**Precondición:** Soy PM. El ticket X tiene al menos un resolutor asignado.
**Pasos:**
1. Accedo al ticket X.
2. Quito la asignación del/los resolutor(es).
**Resultado esperado:** El ticket queda sin resolutor, disponible para ser asignado nuevamente.

## CP-15 (HU-06 / RF-06 / RNF-06) — Notificación automática al asignar un ticket
**Precondición:** Soy PM. Existe un ticket sin asignar.
**Pasos:**
1. Asigno un Developer resolutor al ticket.
2. Espero hasta 1 minuto.
**Resultado esperado:** El Developer resolutor asignado recibe una notificación dentro del minuto posterior a la asignación.

## CP-16 (HU-07 / RF-07 / RG-01) — Avanzar estado de Asignado a En progreso
**Precondición:** Soy el Developer resolutor asignado a un ticket en estado "Asignado".
**Pasos:**
1. Accedo al ticket.
2. Cambio su estado a "En progreso".
**Resultado esperado:** El sistema guarda el nuevo estado y lo refleja en el listado.

## CP-17 (HU-07 / RF-07) — Avanzar estado de En progreso a Cerrado
**Precondición:** Soy el Developer resolutor asignado a un ticket en estado "En progreso".
**Pasos:**
1. Accedo al ticket.
2. Cambio su estado a "Cerrado".
**Resultado esperado:** El sistema guarda el nuevo estado como "Cerrado".

## CP-18 (RG-01) — Intentar avanzar estado de un ticket sin resolutor asignado
**Precondición:** Existe un ticket en estado "Nuevo", sin resolutor asignado.
**Pasos:**
1. Intento cambiar su estado a "En progreso" o "Cerrado" directamente.
**Resultado esperado:** El sistema no permite el cambio de estado.

## CP-19 (RG-03) — Intentar cambiar estado de un ticket asignado a otro resolutor
**Precondición:** Soy Developer resolutor. Existe un ticket asignado únicamente a otro Developer resolutor.
**Pasos:**
1. Intento cambiar el estado de ese ticket.
**Resultado esperado:** El sistema no permite el cambio de estado.

## CP-20 (RG-03) — Cambiar estado de un ticket con múltiples resolutores asignados
**Precondición:** Soy uno de los dos Developers resolutores asignados a un ticket.
**Pasos:**
1. Cambio el estado del ticket.
**Resultado esperado:** El sistema permite el cambio, ya que soy uno de los resolutores asignados (sin importar que haya otro).

## CP-21 (HU-08 / RF-08) — Asignar fecha de vencimiento a un ticket
**Precondición:** Soy PM, Developer solicitante o Developer resolutor con acceso al ticket.
**Pasos:**
1. Accedo al ticket.
2. Defino una fecha de vencimiento.
3. Confirmo.
**Resultado esperado:** El sistema guarda la fecha y la muestra en la información del ticket.

## CP-22 (HU-09 / RF-09) — Enviar un mensaje asociado a un ticket
**Precondición:** Soy Developer (solicitante o resolutor) con acceso a un ticket.
**Pasos:**
1. Accedo al ticket.
2. Escribo un mensaje y lo envío.
**Resultado esperado:** El mensaje queda guardado y visible para el resto del equipo dentro del ticket.

## CP-23 (RF-09) — Intentar que el PM envíe un mensaje
**Precondición:** Soy PM.
**Pasos:**
1. Busco la opción de enviar mensaje en un ticket.
**Resultado esperado:** La opción no está disponible para el rol PM.

## CP-24 (HU-10 / RF-10) — Notificación al solicitante cuando su ticket se cierra
**Precondición:** Soy Developer solicitante y creé el ticket X, actualmente en estado "En progreso".
**Pasos:**
1. El Developer resolutor cambia el estado del ticket X a "Cerrado".
2. Espero hasta 1 minuto.
**Resultado esperado:** Recibo una notificación de que mi ticket fue cerrado.

## CP-25 (HU-11, Escenario 1 / RF-11) — Notificación de vencimiento con fecha definida
**Precondición:** El ticket X tiene fecha de vencimiento definida para hoy y no está cerrado.
**Pasos:**
1. Se alcanza la fecha de vencimiento sin cambios en el ticket.
**Resultado esperado:** El PM y el/los Developer(s) resolutor(es) asignados reciben una notificación de vencimiento.

## CP-26 (HU-11, Escenario 2 / RG-06) — Sin notificación si no hay fecha de vencimiento
**Precondición:** El ticket X no tiene fecha de vencimiento definida.
**Pasos:**
1. Pasa el tiempo (ej: una semana) sin cambios en el ticket.
**Resultado esperado:** El sistema no genera ninguna notificación de vencimiento para ese ticket.

## CP-27 (HU-12 / RF-12) — Ver panel de reportes
**Precondición:** Soy PM.
**Pasos:**
1. Accedo al panel de reportes.
**Resultado esperado:** Veo la cantidad de tickets agrupados por estado y por Developer resolutor.

## CP-28 (RF-12) — Intentar acceder al panel de reportes sin ser PM
**Precondición:** Soy Developer (solicitante o resolutor).
**Pasos:**
1. Intento acceder al panel de reportes.
**Resultado esperado:** El sistema no permite el acceso.

## CP-29 (HU-13 / RF-13 / RG-04) — Reabrir un ticket cerrado (por cualquiera de los 3 roles)
**Precondición:** El ticket X está en estado "Cerrado".
**Pasos:**
1. Como Developer solicitante, resolutor o PM, cambio el estado del ticket a "Reabierto".
**Resultado esperado:** El ticket pasa a estado "Reabierto" y vuelve a ser visible para seguimiento.

## CP-30 (RG-13) — Reabierto pasa a Asignado cuando el PM reasigna
**Precondición:** El ticket X está en estado "Reabierto".
**Pasos:**
1. El PM asigna o reasigna un Developer resolutor al ticket X.
**Resultado esperado:** El ticket pasa a estado "Asignado".

## CP-31 (RG-04) — Intentar reabrir un ticket que no está cerrado
**Precondición:** El ticket X está en estado "En progreso".
**Pasos:**
1. Intento cambiar su estado a "Reabierto".
**Resultado esperado:** El sistema no permite la acción, ya que solo los tickets "Cerrados" pueden reabrirse.

## CP-32 (HU-14 / RF-14 / RG-08) — Modificar prioridad de un ticket ajeno (PM o resolutor)
**Precondición:** Soy PM o Developer resolutor. Existe un ticket que no creé.
**Pasos:**
1. Accedo al ticket.
2. Modifico su prioridad.
3. Confirmo.
**Resultado esperado:** El sistema guarda el cambio de prioridad.

## CP-33 (HU-14 / RF-14 / RG-08) — Intentar que un Developer solicitante ajeno modifique la prioridad
**Precondición:** Existe un ticket creado por otro Developer solicitante.
**Pasos:**
1. Intento modificar la prioridad de ese ticket.
**Resultado esperado:** El sistema no permite la acción (solo puede el creador, el PM o el resolutor).
