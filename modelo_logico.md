Modelo relacional - EduGest

DEPARTAMENTO (id_departamento, jefe_departamento)
PK: id_departamento
FK: jefe_departamento -> PROFESOR

PROFESOR (dni_profesor, nombre, apellidos, correo, fecha_alta, especialidad, id_departamento)
PK: dni
FK: id_departamento -> DEPARTAMENTO

CICLO (codigo_ciclo, nombre, grado, duracion)
PK: codigo_ciclo

GRUPO (id_grupo, turno)
PK: id_grupo

MODULO (codigo_modulo, curso, nombre, horas)
PK: codigo_modulo

ALUMNO (dni_alumno, nia, nombre, apellidos, fecha_nacimiento, correo, telefono, localidad, id_grupo)
PK: nia
FK: id_grupo -> GRUPO

MATRICULA (id_matricula, codigo_modulo, dni_alumno, fecha_matricula, convocatoria, nota_final)
PK: id_matricula
FK: dni_alumno -> ALUMNO
FK: codigo_modulo -> MODULO

FALTA_ASISTENCIA (id_faltas, dia, numero_horas, justificada)
PK: id_falta


IMPARTE (N:M:M) (dni_profesor, codigo_modulo, id_grupo, curso_academico, horas_semanales )
PK / FK: dni_profesor -> PROFESOR
PK / FK: codigo_modulo -> MODULO
PK / FK: id_grupo -> GRUPO
