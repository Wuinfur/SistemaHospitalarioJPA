# Historias de Usuario – Sistema de Gestión Hospitalaria

## 1. Registro de nuevo paciente
**Como** recepcionista del hospital,  
**quiero** registrar un nuevo paciente con sus datos personales,  
**para** poder asignarle citas médicas y mantener su historial clínico.

**Criterios de aceptación:**
- Se deben registrar nombre, apellido, DNI y fecha de nacimiento.
- El sistema debe asignar automáticamente un identificador único al paciente.
- No se deben permitir duplicados de DNI.

---

## 2. Edición de datos de paciente
**Como** recepcionista,  
**quiero** actualizar los datos de un paciente,  
**para** mantener la información personal siempre vigente.

**Criterios de aceptación:**
- Solo se pueden modificar los campos de contacto y dirección.
- Los cambios deben persistirse automáticamente en la base de datos.

---

## 3. Eliminación de paciente inactivo
**Como** administrador,  
**quiero** eliminar pacientes que no registren actividad en más de cinco años,  
**para** mantener la base de datos optimizada.

**Criterios de aceptación:**
- Solo el administrador puede eliminar registros.
- Se debe registrar la fecha y motivo de la eliminación.

---

## 4. Registro de médico
**Como** jefe de recursos humanos,  
**quiero** registrar un médico con su especialidad y matrícula profesional,  
**para** habilitarlo a atender pacientes.

**Criterios de aceptación:**
- Deben completarse nombre, especialidad y número de matrícula.
- La matrícula debe ser única y válida según el formato “M-XXXX”.

---

## 5. Actualización de especialidad médica
**Como** administrador del sistema,  
**quiero** modificar la especialidad de un médico,  
**para** reflejar su nueva área de desempeño.

**Criterios de aceptación:**
- Solo usuarios con rol administrativo pueden realizar la modificación.
- El cambio debe registrarse en el log de auditoría.

---

## 6. Asignación de médico a departamento
**Como** jefe de hospital,  
**quiero** asignar un médico a un departamento,  
**para** organizar la estructura funcional del hospital.

**Criterios de aceptación:**
- El médico debe existir previamente en el sistema.
- El departamento debe tener capacidad disponible.

---

## 7. Registro de hospital
**Como** administrador general,  
**quiero** registrar un hospital con su nombre, dirección y departamentos,  
**para** gestionar múltiples sedes institucionales.

**Criterios de aceptación:**
- Cada hospital debe tener un nombre único.
- El sistema debe permitir agregar departamentos al hospital recién creado.

---

## 8. Creación de departamento
**Como** director médico,  
**quiero** crear un nuevo departamento dentro del hospital,  
**para** organizar áreas de especialización médica.

**Criterios de aceptación:**
- Cada departamento pertenece a un hospital existente.
- El sistema debe verificar que no existan nombres duplicados en el mismo hospital.

---

## 9. Creación de sala
**Como** jefe de departamento,  
**quiero** crear una sala asociada a mi departamento,  
**para** organizar la asignación de camas y pacientes.

**Criterios de aceptación:**
- Cada sala debe tener capacidad máxima definida.
- La sala no puede crearse sin un departamento asociado.

---

## 10. Asignación de paciente a sala
**Como** enfermero,  
**quiero** asignar un paciente a una sala disponible,  
**para** garantizar su ubicación física dentro del hospital.

**Criterios de aceptación:**
- No se puede superar la capacidad máxima de la sala.
- El paciente no puede estar asignado simultáneamente a dos salas.

---

## 11. Creación de cita médica
**Como** recepcionista,  
**quiero** programar una cita entre un médico y un paciente,  
**para** gestionar el calendario de consultas.

**Criterios de aceptación:**
- El médico y el paciente deben estar registrados.
- La fecha y hora deben estar disponibles para ambos.
- El estado inicial debe ser “PENDIENTE”.

---

## 12. Modificación de cita
**Como** recepcionista,  
**quiero** modificar la fecha o el médico de una cita,  
**para** reprogramarla según disponibilidad.

**Criterios de aceptación:**
- Solo se permite modificar citas en estado “PENDIENTE”.
- El nuevo horario no debe superponerse con otras citas del mismo médico.

---

## 13. Cancelación de cita
**Como** paciente,  
**quiero** cancelar una cita con anticipación,  
**para** liberar el horario del médico.

**Criterios de aceptación:**
- La cancelación solo es válida con más de 24 horas de antelación.
- El estado debe actualizarse a “CANCELADA”.

---

## 14. Completar cita médica
**Como** médico,  
**quiero** marcar una cita como completada,  
**para** registrar la atención realizada.

**Criterios de aceptación:**
- Solo el médico asignado puede completar la cita.
- Debe indicarse un diagnóstico o nota médica.

---

## 15. Consulta de médicos por especialidad
**Como** recepcionista,  
**quiero** obtener un listado de médicos según su especialidad,  
**para** asignar pacientes al profesional adecuado.

**Criterios de aceptación:**
- Debe filtrarse por campo `especialidad`.
- La lista se devuelve ordenada alfabéticamente por nombre.

---

## 16. Conteo de citas completadas
**Como** administrador,  
**quiero** conocer la cantidad de citas completadas en el sistema,  
**para** elaborar reportes de productividad médica.

**Criterios de aceptación:**
- Se deben contar solo las citas con estado `COMPLETADA`.
- El resultado debe presentarse como un número entero.

---

## 17. Listado de pacientes con alergias
**Como** médico,  
**quiero** consultar los pacientes que presentan alergias,  
**para** prevenir riesgos en tratamientos.

**Criterios de aceptación:**
- Se debe obtener información desde la entidad `HistoriaClinica`.
- Solo se listan pacientes con al menos una alergia registrada.

---

## 18. Registro de historia clínica
**Como** médico,  
**quiero** crear una historia clínica para un paciente,  
**para** documentar diagnósticos y tratamientos.

**Criterios de aceptación:**
- Cada paciente puede tener una única historia clínica activa.
- La historia debe incluir fecha de creación y médico responsable.

---

## 19. Agregar diagnóstico a historia clínica
**Como** médico,  
**quiero** registrar un diagnóstico en la historia clínica de un paciente,  
**para** dejar constancia del tratamiento indicado.

**Criterios de aceptación:**
- La historia clínica debe existir previamente.
- Debe almacenarse la fecha y descripción del diagnóstico.

---

## 20. Registrar alergias en historia clínica
**Como** médico,  
**quiero** registrar alergias de un paciente,  
**para** evitar errores en prescripciones futuras.

**Criterios de aceptación:**
- Las alergias se guardan como lista de cadenas de texto.
- El sistema debe permitir agregar o eliminar alergias.

---

## 21. Consulta de historial de citas por paciente
**Como** médico,  
**quiero** ver todas las citas de un paciente,  
**para** conocer su evolución médica.

**Criterios de aceptación:**
- Las citas deben mostrarse en orden cronológico descendente.
- Debe incluirse fecha, médico y estado.

---

## 22. Generación de reporte por departamento
**Como** administrador,  
**quiero** generar un reporte con el número de médicos y pacientes por departamento,  
**para** analizar la distribución de recursos.

**Criterios de aceptación:**
- El reporte debe calcular totales por cada departamento.
- Se debe exportar en formato de texto o CSV.

---

## 23. Listado de médicos activos
**Como** director,  
**quiero** ver los médicos activos en cada hospital,  
**para** evaluar la disponibilidad del personal.

**Criterios de aceptación:**
- Solo se incluyen médicos con estado activo.
- Debe mostrarse su especialidad y matrícula.

---

## 24. Reasignación de médico entre hospitales
**Como** administrador general,  
**quiero** transferir un médico de un hospital a otro,  
**para** equilibrar la carga de trabajo.

**Criterios de aceptación:**
- Solo se permite si el nuevo hospital tiene departamento compatible.
- La operación debe registrarse en el historial del médico.

---

## 25. Consulta de disponibilidad de salas
**Como** jefe de departamento,  
**quiero** conocer qué salas tienen camas disponibles,  
**para** organizar las internaciones.

**Criterios de aceptación:**
- La consulta debe devolver número de sala y cantidad de camas libres.
- Solo deben listarse salas con disponibilidad > 0.

---

## 26. Auditoría de cambios
**Como** auditor interno,  
**quiero** acceder al registro de modificaciones en entidades críticas,  
**para** garantizar trazabilidad.

**Criterios de aceptación:**
- Debe registrar usuario, fecha y tipo de cambio.
- Se deben auditar entidades: `Paciente`, `Medico`, `Cita`.

---

## 27. Autenticación de usuarios
**Como** usuario del sistema,  
**quiero** iniciar sesión con credenciales,  
**para** acceder a las funciones correspondientes a mi rol.

**Criterios de aceptación:**
- Debe validarse usuario y contraseña en base segura.
- Cada rol (médico, recepcionista, administrador) tiene permisos distintos.

---

## 28. Registro de altas médicas
**Como** médico,  
**quiero** registrar la fecha de alta de un paciente internado,  
**para** actualizar su estado en el sistema.

**Criterios de aceptación:**
- Solo se puede registrar alta si el paciente tenía internación activa.
- El sistema debe registrar la fecha de alta automáticamente.

---

## 29. Eliminación de cita antigua
**Como** administrador,  
**quiero** eliminar citas con más de dos años de antigüedad,  
**para** optimizar el rendimiento de la base de datos.

**Criterios de aceptación:**
- Solo citas con estado “COMPLETADA” o “CANCELADA” pueden eliminarse.
- Debe registrarse un log con la cantidad eliminada.

---

## 30. Asignación automática de médico
**Como** sistema,  
**quiero** asignar automáticamente un médico disponible según especialidad,  
**para** agilizar la programación de citas.

**Criterios de aceptación:**
- Se debe buscar un médico sin citas programadas en el horario solicitado.
- Si no hay disponibilidad, se muestra un mensaje informativo.

---

## 31. Consulta de pacientes sin historia clínica
**Como** jefe médico,  
**quiero** conocer los pacientes que aún no tienen historia clínica,  
**para** priorizar su evaluación.

**Criterios de aceptación:**
- La consulta debe devolver nombre y fecha de registro del paciente.
- Solo se incluyen pacientes activos.

---

## 32. Respaldo de base de datos
**Como** administrador del sistema,  
**quiero** generar una copia de respaldo del archivo de base de datos H2,  
**para** prevenir pérdidas de información.

**Criterios de aceptación:**
- El respaldo debe incluir todos los registros actuales.
- El archivo de copia debe guardarse en la carpeta `/backup` con fecha en el nombre.

---

**Fin del documento.**
