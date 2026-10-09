# Sistema de Gestión de Citas Médicas

Plataforma web para una clínica pequeña que permite a los pacientes solicitar y gestionar sus citas médicas y al personal administrativo organizar la agenda de los doctores. Proyecto de Ingeniería de Software I (UAPA).

## Objetivo
Centralizar la solicitud, programación, cancelación y seguimiento de citas médicas, evitando duplicidades, confirmando cada solicitud y recordando la cita al paciente.

## Problema que resuelve
La clínica gestiona las citas por teléfono y en una libreta. Esto genera citas duplicadas en el mismo horario, pacientes sin confirmación de su solicitud, cancelaciones que no llegan a tiempo y falta de historial de consultas.

## Funcionalidades principales
- Registro de pacientes (RF-01)
- Agendar cita seleccionando doctor, fecha y hora disponible (RF-02)
- Panel de agenda diaria del doctor (RF-03)
- Cancelación y reprogramación de citas (RF-04)
- Notificaciones de recordatorio (RF-05)
- Historial básico de consultas

## Arquitectura seleccionada
Arquitectura en capas con separación cliente-servidor, con el backend organizado según el patrón MVC. Principio de diseño: separación de responsabilidades, con bajo acoplamiento y alta cohesión.

## Organización frontend / backend

### Frontend (cliente)
Responsabilidad: presentar la interfaz y capturar la interacción del usuario. No contiene reglas de negocio.
- Formulario de registro guiado paso a paso
- Pantalla de agendar cita (doctor, fecha y solo horarios disponibles)
- Panel de agenda diaria ordenada por hora
- Vistas distintas según el rol (paciente o personal)

### Backend (servidor)
Responsabilidad: aplicar las reglas del sistema, controlar el acceso y gestionar los datos.
- Servicios: exponen los endpoints de la API (agendar, cancelar, notificar)
- Autenticación: inicio de sesión y control de acceso por rol
- Lógica de negocio: valida disponibilidad, evita citas duplicadas y registra cada cambio de estado
- Acceso a datos: lee y escribe pacientes, doctores, citas y notificaciones

### Comunicación entre ambos
1. El frontend envía solicitudes HTTP a la API REST del backend, con datos en JSON sobre HTTPS.
2. Cada solicitud lleva el token de sesión del usuario; el backend lo valida y verifica el rol antes de ejecutar la acción.
3. El backend responde con JSON y un código de estado (éxito, horario no disponible, no autorizado), que el frontend traduce en un mensaje claro para el usuario.
4. El frontend nunca accede directamente a la base de datos.

## Herramientas utilizadas
- GitHub: repositorio, Issues y control de cambios
- GitHub Projects: tablero Kanban
- Visual Paradigm Online: diagramas UML y de arquitectura
- Scrum + Kanban: enfoque de gestión del proyecto

## Estado actual del proyecto
Versión v0.1.0 (base documental y de diseño). Requisitos, modelado y arquitectura definidos; desarrollo de código en etapa inicial.
