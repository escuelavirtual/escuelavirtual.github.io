# escuelavirtual.github.io

## Documentacion del proyecto

## Requerimientos

### Casos de uso.

Tareas a desarrollar, con sus test (preferentemente), y sus endpoint.

---

**Casos de uso:** Estudiante solicita registro **Código:** CU1

**Actor:** Estudiante

**Pre-condición:** Ninguna

**Final esperado:** El Estudiante queda registrado en el sistema

**Final fallido:** El estudiante ya existe en la base de datos

**Responsable:** @Rafael Moreno @Erick

**Propósito:** Registrar un nuevo estudiante en el sistema.

**Resumen**: El estudiante al completar un formulario de registro, se procede a la verificación de los datos y al registro del estudiante en el sistema.

***

**Casos de uso:** Usuario inicia sesión **Codigo:** CU2

**Actor:** Estudiante, Profesor, Moderador, Administrador

**Pre-condición:** Ninguna

**Final esperado:** El Usuario inicia sesión con las credenciales correspondientes / El sistema genera un token.

**Final fallido:** Las credenciales no son validos o el usuario no existe

**Responsable:** @arishkage @jlrcontactos

**Propósito:** Autentificación del usuario

**Resumen:** El usuario al completar un formulario de identificación, se procede a la verificación de los datos y a la autentifacacion del mismo en el sistema.

***

**Casos de uso:** Profesor solicita creación de un curso ** Código:** CU3

**Actor:** Profesor

**Pre-condición:** El profesor debe estar autentificado

**Final esperado:** El profesor completa exitosamente su solicitud para un nuevo curso

**Final fallido:** A revisar...

**Responsable:** @Lalo @SergioDC

**Propósito:** Creación de un nuevo curso

**Resumen:** Un profesor, al completar un formulario con los datos básicos del curso, el sistema le permitirá ingresar al panel de administración de su curso.

***

**Casos de uso:** Estudiante solicita ingreso a un curso ** Código:** CU4

**Actor:** Estudiante

**Pre-condición:** El estudiante debe estar autentificado y el curso debe existir

**Final esperado:** A revisar...

**Final fallido:** A revisar...

**Responsable:** ...

**Propósito:** Solicitud de un estudiante a un curso.

**Resumen:** Un estudiante, al registrarse a un curso, el sistema debe registrar su solicitud para su posterior aprobación del profesor.
