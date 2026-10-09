# Matriz de Requisitos – Sistema de Gestión de Citas Médicas

## 1. Requisitos funcionales

| Código | Descripción | Tipo | Prioridad | Criterio de aceptación |
|--------|-------------|------|-----------|------------------------|
| RF-01 | El sistema debe permitir al paciente registrar sus datos personales y de contacto. | Funcional | Alta | El paciente completa un formulario y su perfil queda guardado en el sistema con un ID único. |
| RF-02 | El sistema debe permitir al paciente agendar una cita seleccionando doctor, fecha y hora disponible. | Funcional | Alta | Al seleccionar un horario disponible, la cita queda registrada y visible en la agenda del doctor correspondiente. |
| RF-03 | El sistema debe permitir al personal administrativo visualizar la agenda diaria de cada doctor de la clínica. | Funcional | Alta | El panel muestra todas las citas del día ordenadas por hora, sin horarios duplicados. |
| RF-04 | El sistema debe permitir al paciente cancelar o reprogramar una cita ya agendada. | Funcional | Media | Al cancelar o reprogramar una cita, el horario anterior queda liberado y disponible para otro paciente. |
| RF-05 | El sistema debe enviar una notificación de recordatorio al paciente antes de la fecha de su cita. | Funcional | Media | El paciente recibe una notificación (correo o mensaje de texto) al menos 24 horas antes de la fecha de su cita agendada. |

## 2. Requisitos no funcionales

| Código | Categoría | Descripción | Prioridad | Criterio de aceptación |
|--------|-----------|-------------|-----------|------------------------|
| RNF-01 | Seguridad | El sistema debe garantizar la confidencialidad de los datos personales y médicos de los pacientes. | Alta | Solo usuarios autenticados con rol autorizado pueden acceder a los datos del paciente. |
| RNF-02 | Usabilidad | El sistema debe ofrecer una interfaz sencilla y fácil de usar para pacientes sin experiencia técnica. | Alta | Un usuario nuevo logra agendar una cita en menos de 3 pasos, sin necesitar ayuda externa. |
| RNF-03 | Trazabilidad | El sistema debe registrar de forma inmutable cada cambio de estado de una cita (creada, modificada, cancelada). | Media | Cada cambio de estado queda registrado con fecha, hora y usuario responsable, sin poder eliminarse. |
| RNF-04 | Rendimiento | El sistema debe responder a las solicitudes de agendamiento en un tiempo máximo de 3 segundos. | Media | Al agendar una cita bajo condiciones normales de uso, el sistema confirma la acción en 3 segundos o menos. |
| RNF-05 | Mantenibilidad | El sistema debe estar estructurado en módulos independientes que permitan agregar nuevas funcionalidades sin afectar las existentes. | Baja | Se puede añadir un nuevo módulo sin modificar el código de los módulos ya existentes. |

## 3. Historias de usuario y trazabilidad

| Hallazgo | Historia de usuario | Requisito | Issue |
|----------|---------------------|-----------|-------|
| Los pacientes no tienen forma de confirmar si su solicitud de cita fue debidamente recibida. | **HU-01:** Como paciente, quiero registrar mis datos en el sistema para poder solicitar citas médicas sin repetir mi información cada vez. | RF-01 | #3 Registro de pacientes |
| El personal administrativo gestiona la agenda de forma manual, lo que provoca citas duplicadas. | **HU-02:** Como paciente, quiero agendar una cita seleccionando doctor, fecha y hora disponible, para asegurar mi atención sin necesidad de llamar por teléfono. | RF-02 | #4 Agendar cita médica |
| No existe visibilidad clara de la agenda diaria para organizar las citas de cada doctor. | **HU-03:** Como personal administrativo, quiero visualizar la agenda diaria de cada doctor, para organizar las citas sin que se dupliquen horarios. | RF-03 | #5 Panel de agenda del doctor |
| No existe un mecanismo claro para cancelar o reprogramar una cita ya solicitada. | **HU-04:** Como paciente, quiero cancelar o reprogramar una cita ya agendada, para ajustar mi solicitud sin tener que llamar a la clínica. | RF-04 | #6 Cancelación/Reprogramación de citas |
| Los pacientes olvidan sus citas por falta de recordatorios automáticos. | **HU-05:** Como paciente, quiero recibir una notificación de recordatorio antes de mi cita, para no olvidar la fecha y hora de mi consulta. | RF-05 | #7 Notificaciones de recordatorio |
