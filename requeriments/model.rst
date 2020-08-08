
***************
Modelo de datos
***************

.. contents:: Table of Contents

Control de Versiones
==============

Si vas a hacer una modificación al diagrama ER, llena el formato de
control de versiones y modifica los templates correspondientes del
diccionario de datos y descripción de tablas que se encuentran abajo,
agrega una captura de pantalla del diagrama modificado. **No olvides
cambiar al final del nombre de este documento la versión** *e.g
Documentacion Base de datos relacional (vx.x.x)*.

+------------------+-----------------+-----------------+-----------------+
| Usuario de       | Aporte          | Descripción     | Versión         |
| Github           |                 |                 |                 |
+==================+=================+=================+=================+
| `@Sergio-DC`_,   | Diseño del      | Se discutió     | **              |
| `@lalo1234321`_, | diagrama ER     | acerca del      | v1.0.0-040820** |
| `@VidalAlvarez`_ |                 | diseño de la    |                 |
|                  |                 | base de datos   |                 |
|                  |                 | relacional      |                 |
+------------------+-----------------+-----------------+-----------------+
| `@lalo1234321`_  | Se eliminó la   | La relación     | **              |
|                  | tabla de        | entre el        | v1.1.0-060820** |
|                  | couse_history   | profesor y el   |                 |
|                  |                 | curso se puede  |                 |
|                  |                 | interpretar de  |                 |
|                  |                 | dos formas      |                 |
|                  |                 | respecto a las  |                 |
|                  |                 | reglas de       |                 |
|                  |                 | negocio: 1) El  |                 |
|                  |                 | profesor puede  |                 |
|                  |                 | crear uno o     |                 |
|                  |                 | varios cursos.  |                 |
|                  |                 | 2) El profesor  |                 |
|                  |                 | ha impartido    |                 |
|                  |                 | uno o varios    |                 |
|                  |                 | cursos          |                 |
|                  |                 | (implicitamente |                 |
|                  |                 | se entiende que |                 |
|                  |                 | el profesor ya  |                 |
|                  |                 | tiene un        |                 |
|                  |                 | historial de    |                 |
|                  |                 | curso, por lo   |                 |
|                  |                 | tanto, se       |                 |
|                  |                 | elimina la      |                 |
|                  |                 | entidad         |                 |
|                  |                 | intermediaria). |                 |
+------------------+-----------------+-----------------+-----------------+
| `@Sergio-DC`_ ,  | Modificaciones  | La primera      | **              |
| `@lalo1234321`_  | importantes de  | modificación    | v1.2.0-060820** |
|                  | la base de      | que se realizó  |                 |
|                  | datos           | fue el cambio   |                 |
|                  |                 | de nombre de la |                 |
|                  |                 | tabla           |                 |
|                  |                 | FINAL_GRADE a   |                 |
|                  |                 | GRADE_REPORT,   |                 |
|                  |                 | se analizó la   |                 |
|                  |                 | relación entre  |                 |
|                  |                 | GRADE_REPORT y  |                 |
|                  |                 | EXAMINATION y   |                 |
|                  |                 | se llegó a la   |                 |
|                  |                 | conclusón de    |                 |
|                  |                 | que la relación |                 |
|                  |                 | estabaa de más, |                 |
|                  |                 | de ésta forma   |                 |
|                  |                 | sólo exisitiría |                 |
|                  |                 | la relación de  |                 |
|                  |                 | FINAL_GRADE y   |                 |
|                  |                 | STUDENT para    |                 |
|                  |                 | poder acceder a |                 |
|                  |                 | todas la        |                 |
|                  |                 | evaluaciones    |                 |
|                  |                 | que realice y   |                 |
|                  |                 | así obtener su  |                 |
|                  |                 | boleta.         |                 |
+------------------+-----------------+-----------------+-----------------+
| `@Sergio-DC`_ ,  | Se agregaron    | Se eliminó una  | v1.3.0-070820   |
| `@lalo1234321`_  | entidades al    | de las dos      |                 |
|                  | modelo y        | relaciones que  |                 |
|                  | cambios         | había entre     |                 |
|                  | importantes en  | PROFESOR Y      |                 |
|                  | la base de      | COURSE, se      |                 |
|                  | datos           | agregaron 4     |                 |
|                  |                 | tablas:         |                 |
|                  |                 | ANSWER,         |                 |
|                  |                 | QUESTION,MODULE |                 |
|                  |                 | y               |                 |
|                  |                 | GROUP_ACTIVITY  |                 |
+------------------+-----------------+-----------------+-----------------+
| `@VidalAlvarez`_ | Se agregó la    | Entidades       | v1.4.0-080820   |
|                  | propiedades     | Modificadas     |                 |
|                  | +codigo         | COURSE, GROUP,  |                 |
|                  |                 | y STUDENT.      |                 |
|                  |                 | Permitirá       |                 |
|                  |                 | relacionar las  |                 |
|                  |                 | entidades al    |                 |
|                  |                 | ingresar al     |                 |
|                  |                 | portal          |                 |
+------------------+-----------------+-----------------+-----------------+

.. _@Sergio-DC: https://github.com/Sergio-DC

.. _@VidalAlvarez: https://github.com/ReynaldoAlvarez 

.. _@lalo1234321: https://github.com/lalo1234321

Diagrama Entidad Relación
==============

`Link para editar el diagrama`_ |Tabla_versiones|

.. _Link para editar el diagrama: https://app.lucidchart.com/invitations/accept/4e829d59-8b8f-448f-a828-7677a8c0870e

.. |Tabla_versiones| image:: https://res.cloudinary.com/vidalalvarez/image/upload/v1596902314/bd/Diagrama-ER_v1.3.0_-_Diagrama_E-R_g6ejzd.png

   
Descripción de tablas
=====================

+-----------------------+-----------------------+-----------------------+
| NOMBRE DE TABLA       | CLAVE PRIMARIA        | DESCRIPCIÓN           |
+=======================+=======================+=======================+
| USER                  | id_user               | Almacena el código    |
|                       |                       | (llave primaria),     |
|                       |                       | nombre, apellidos,    |
|                       |                       | email y password del  |
|                       |                       | usuario.              |
+-----------------------+-----------------------+-----------------------+
| PROFESOR              | id_profesor           | La tabla se encarga   |
|                       |                       | de guardar la         |
|                       |                       | información del id de |
|                       |                       | un profesor y la      |
|                       |                       | valoración que tiene  |
|                       |                       | éste(Si es un buen o  |
|                       |                       | mal profesor) como    |
|                       |                       | referencias.          |
+-----------------------+-----------------------+-----------------------+
| STUDENT               | id_student            | Esta tabla sólo se    |
|                       |                       | encargará de          |
|                       |                       | almacenar los         |
|                       |                       | identificadores de    |
|                       |                       | los estudiantes.      |
+-----------------------+-----------------------+-----------------------+
| COURSE                | id_course             | Se retiene            |
|                       |                       | información a cerca   |
|                       |                       | de la llave primaria  |
|                       |                       | del curso, llave      |
|                       |                       | foránea del profesor, |
|                       |                       | título o nombre de la |
|                       |                       | asignatura, una breve |
|                       |                       | descripción del       |
|                       |                       | curso, el temario,    |
|                       |                       | fecha de inicio,      |
|                       |                       | fecha de              |
|                       |                       | finalización,         |
|                       |                       | requerimientos y si   |
|                       |                       | es privado o público  |
|                       |                       | el curso.             |
+-----------------------+-----------------------+-----------------------+
| TOPIC                 | id_topic              | Nos ayuda a preservar |
|                       |                       | información de la     |
|                       |                       | llave primaria de     |
|                       |                       | éste, la llave        |
|                       |                       | foránea del curso a   |
|                       |                       | la cual pertenece, y  |
|                       |                       | el nombre del tema o  |
|                       |                       | sección.              |
+-----------------------+-----------------------+-----------------------+
| GROUP                 | id_group              | Esta tabla mantendrá  |
|                       |                       | datos del grupo; el   |
|                       |                       | id primario, la llave |
|                       |                       | foránea del           |
|                       |                       | estudiante y la llave |
|                       |                       | foránea del course al |
|                       |                       | que pertenece.        |
+-----------------------+-----------------------+-----------------------+
| EXAMINATION           | id_examination        | Nos ayuda a guardar   |
|                       |                       | toda la información   |
|                       |                       | referente a las       |
|                       |                       | pruebas aplicadas por |
|                       |                       | un profesor; el id de |
|                       |                       | la evaluación, la     |
|                       |                       | llave foránea del     |
|                       |                       | estudiante, la llave  |
|                       |                       | foránea del tema, el  |
|                       |                       | tipo de examen que se |
|                       |                       | aplicará, nombre del  |
|                       |                       | examen, calificación  |
|                       |                       | y la llave foránea de |
|                       |                       | la calificación final |
+-----------------------+-----------------------+-----------------------+
| FINAL_GRADE           | id_final_grade        | Esta tabla se encarga |
|                       |                       | de la información de  |
|                       |                       | la calificación final |
|                       |                       | de un estudiante,     |
|                       |                       | facilita a que        |
|                       |                       | persistan los         |
|                       |                       | siguientes datos;     |
|                       |                       | llave primaria de la  |
|                       |                       | calificación final,   |
|                       |                       | la llave foránea de   |
|                       |                       | la prueba, la llave   |
|                       |                       | foránea del           |
|                       |                       | estudiante, la        |
|                       |                       | calificación final y  |
|                       |                       | un campo para         |
|                       |                       | determinar si aprobó  |
|                       |                       | la materia.           |
+-----------------------+-----------------------+-----------------------+
| QUESTION              | id_question           | Esta tabla hace que   |
|                       |                       | persista la           |
|                       |                       | información de una    |
|                       |                       | pregunta que forma    |
|                       |                       | ṕarte de un examen,   |
|                       |                       | los campos que tiene  |
|                       |                       | son su llave          |
|                       |                       | primaria, la llave    |
|                       |                       | foránea de la         |
|                       |                       | realción entre        |
|                       |                       | EXAMINATION y la      |
|                       |                       | tabla actual, el      |
|                       |                       | campo content es el   |
|                       |                       | apartado que guarda   |
|                       |                       | el contenido de la    |
|                       |                       | pregunta y el campo   |
|                       |                       | open_answer es donde  |
|                       |                       | se quedará guardada   |
|                       |                       | la respuesta correcta |
|                       |                       | de la pregunta        |
+-----------------------+-----------------------+-----------------------+
| ANSWER                | NA                    | La tabla tiene tres   |
|                       |                       | campos, la llave      |
|                       |                       | foránea generada por  |
|                       |                       | la relación entre     |
|                       |                       | QUESTION y ANSWER     |
+-----------------------+-----------------------+-----------------------+
| MODULE                | id_module             | Esta tabla la función |
|                       |                       | de guardar los        |
|                       |                       | modulos o secciones   |
|                       |                       | en las cuales se      |
|                       |                       | dividirá un           |
|                       |                       | curso,tiene su llave  |
|                       |                       | primaria, una llave   |
|                       |                       | foránea de la tabla   |
|                       |                       | COURSE y la           |
|                       |                       | descripción de qué se |
|                       |                       | va a tratar la unidad |
|                       |                       | o modulo              |
+-----------------------+-----------------------+-----------------------+
| GROUP_ACTIVITY        | id_group_activity     | La tabla almacena la  |
|                       |                       | informcaión de las    |
|                       |                       | actividades que       |
|                       |                       | creará un profesor en |
|                       |                       | un curso, tiene su    |
|                       |                       | llave primaria, una   |
|                       |                       | llave foránea de la   |
|                       |                       | tabla MODULE, campos  |
|                       |                       | para el nombre de la  |
|                       |                       | actividad, las        |
|                       |                       | intrucciones para     |
|                       |                       | guiar a los alumnos,  |
|                       |                       | la calificación que   |
|                       |                       | obtendrá y una        |
|                       |                       | sección para las      |
|                       |                       | observaciones         |
+-----------------------+-----------------------+-----------------------+


Diccionario de Datos
==============

USER
~~~~

+-------+---------+------------------+---------+--------------------+
| Clave | Campo   | Tipo de Atributo | Es Nulo | Descripción        |
+=======+=========+==================+=========+====================+
| P     | id_user | Integer          | NULL    | Almacena el código |
|       |         |                  |         | que identifica a   |
|       |         |                  |         | cada usuario       |
+-------+---------+------------------+---------+--------------------+

STUDENT
~~~~~~~

+-------+------------+------------------+---------+------------------+
| Clave | Campo      | Tipo de Atributo | Es Nulo | Descripción      |
+=======+============+==================+=========+==================+
| PFK   | id_student | Integer          | NULL    | Almacena el      |
|       |            |                  |         | código que       |
|       |            |                  |         | identifica a     |
|       |            |                  |         | cada estudiante  |
+-------+------------+------------------+---------+------------------+

PROFESSOR
~~~~~~~~~

+-------+--------------+--------------+--------------+--------------+
| Clave | Campo        | Tipo de      | Es Nulo      | Descripción  |
|       |              | Atributo     |              |              |
+=======+==============+==============+==============+==============+
| PFK   | id_professor | Integer      | NULL         | Almacena el  |
|       |              |              |              | código que   |
|       |              |              |              | identifica a |
|       |              |              |              | cada         |
|       |              |              |              | profesor     |
+-------+--------------+--------------+--------------+--------------+
|       | valuation    | Integer      | Almacena la  |              |
|       |              |              | valoración   |              |
|       |              |              | que tiene un |              |
|       |              |              | profesor     |              |
+-------+--------------+--------------+--------------+--------------+

COURSE
~~~~~~

+-------------+-------------+-------------+-------------+-------------+
| Clave       | Campo       | Tipo de     | Es Nulo     | Descripción |
|             |             | Atributo    |             |             |
+=============+=============+=============+=============+=============+
| PFK         | id_course   | Varchar(50) | NOT NULL    | Almacena el |
|             |             |             |             | código que  |
|             |             |             |             | identifica  |
|             |             |             |             | un curso    |
+-------------+-------------+-------------+-------------+-------------+
| FK          | i           | Integer     | NOT NULL    | Es el       |
|             | d_professor |             |             | profesor    |
|             |             |             |             | que imparte |
|             |             |             |             | el curso    |
+-------------+-------------+-------------+-------------+-------------+
|             | title       | Varchar(50) | NOT NULL    | Nombre que  |
|             |             |             |             | describa el |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
|             | description | Varchar(50) | NOT NULL    | Almacena    |
|             |             |             |             | una         |
|             |             |             |             | descripción |
|             |             |             |             | más         |
|             |             |             |             | detallada   |
|             |             |             |             | del curso   |
+-------------+-------------+-------------+-------------+-------------+
|             | syllabus    | V           | NOT NULL    | Almacena el |
|             |             | archar(500) |             | temario del |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
|             | start_date  | Date        | NULL        | Almacena la |
|             |             |             |             | fecha       |
|             |             |             |             | inicial del |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
|             | end_date    | Date        | NULL        | Almacena la |
|             |             |             |             | fecha final |
|             |             |             |             | del curso   |
+-------------+-------------+-------------+-------------+-------------+
|             | r           | Varvhar(50) | NOT NULL    | **Este      |
|             | equirements |             |             | campo está  |
|             |             |             |             | en proceso  |
|             |             |             |             | de          |
|             |             |             |             | discusión** |
+-------------+-------------+-------------+-------------+-------------+
|             | isPrivate   | Bool        | NOT NULL    | Bandera de  |
|             |             |             |             | estado que  |
|             |             |             |             | determina   |
|             |             |             |             | si el curso |
|             |             |             |             | es privado  |
|             |             |             |             | o público   |
|             |             |             |             | **Este      |
|             |             |             |             | campo está  |
|             |             |             |             | en proceso  |
|             |             |             |             | de          |
|             |             |             |             | discusión** |
+-------------+-------------+-------------+-------------+-------------+

COURSE_HISTORY
~~~~~~~~~~~~~~

+-------------+-------------+-------------+-------------+-------------+
| Clave       | Campo       | Tipo de     | Es Nulo     | Descripción |
|             |             | Atributo    |             |             |
+=============+=============+=============+=============+=============+
| P           | id_cou      | Integer     | NOT NULL    | **Este      |
|             | rse_history |             |             | campo debe  |
|             |             |             |             | ser         |
|             |             |             |             | discutido** |
+-------------+-------------+-------------+-------------+-------------+
| FK          | i           | Integer     | NOT NULL    | Profesor    |
|             | d_professor |             |             | que         |
|             |             |             |             | impartió el |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
|             | id_course   | VARCHAR(50) | NOT NULL    | Almacena el |
|             |             |             |             | código que  |
|             |             |             |             | identifica  |
|             |             |             |             | a cada      |
|             |             |             |             | curso       |
|             |             |             |             | impartido   |
|             |             |             |             | por un      |
|             |             |             |             | profesor    |
+-------------+-------------+-------------+-------------+-------------+

TOPIC
~~~~~

+-------------+-------------+-------------+-------------+-------------+
| Clave       | Campo       | Tipo de     | Es Nulo     | Descripción |
|             |             | Atributo    |             |             |
+=============+=============+=============+=============+=============+
| PK          | id_topic    | Integer     | NOT NULL    | Almacena el |
|             |             |             |             | código que  |
|             |             |             |             | identifica  |
|             |             |             |             | un tema o   |
|             |             |             |             | módulo del  |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
| FK          | id_course   | VARCHAR(50) | NOT NULL    | id          |
|             |             |             |             | entificador |
|             |             |             |             | del curso   |
|             |             |             |             | que         |
|             |             |             |             | determina   |
+-------------+-------------+-------------+-------------+-------------+

EXAMINATION
~~~~~~~~~~~

===== ============== ================ ======== =================
Clave Campo          Tipo de Atributo Es Nulo  Descripción
===== ============== ================ ======== =================
PK    id_examination Integer          NOT NULL falta descripción
FK    id_student     Integer          NOT NULL falta descripción
FK    id_topic       Integer          NOT NULL falta descripción
\     tipo           Varchar(50)      NOT NULL falta descripción
\     name           Varchar(50)      NOT NULL falta descripción
\     grade          Double           NOT NULL falta descripción
FK    id_grade       Integer          NOT NULL falta descripción
===== ============== ================ ======== =================

Tabla GROUP
~~~~~~~~~~~

+-------+------------+------------------+----------+------------------+
| Clave | Campo      | Tipo de Atributo | Es Nulo  | Descripción      |
+=======+============+==================+==========+==================+
| PK    | id_group   | Integer          | NOT NULL | Almacena el      |
|       |            |                  |          | código que       |
|       |            |                  |          | identifica a un  |
|       |            |                  |          | grupo            |
+-------+------------+------------------+----------+------------------+
| FK    | id_student | Integer          | NOT NULL | Estudiante que   |
|       |            |                  |          | esta en el grupo |
+-------+------------+------------------+----------+------------------+
| FK    | id_course  | Varchar(50)      | NOT NULL | Curso que se     |
|       |            |                  |          | imparte en el    |
|       |            |                  |          | grupo            |
+-------+------------+------------------+----------+------------------+

FINAL_GRADE
~~~~~~~~~~~

+-------------+-------------+-------------+-------------+-------------+
| Clave       | Campo       | Tipo de     | Es Nulo     | Descripción |
|             |             | Atributo    |             |             |
+=============+=============+=============+=============+=============+
| PK          | id_grade    | Integer     | NOT NULL    | Almacena el |
|             |             |             |             | código que  |
|             |             |             |             | identifica  |
|             |             |             |             | a una       |
|             |             |             |             | boleta      |
+-------------+-------------+-------------+-------------+-------------+
| FK          | id_         | Integer     | NOT NULL    | t           |
|             | examination |             |             | est/pruebas |
|             |             |             |             | presentadas |
|             |             |             |             | por el      |
|             |             |             |             | alumno para |
|             |             |             |             | poder       |
|             |             |             |             | realizar el |
|             |             |             |             | calculo del |
|             |             |             |             | promedio    |
|             |             |             |             | final       |
+-------------+-------------+-------------+-------------+-------------+
| FK          | id_student  | Integer     | NOT NULL    | Almacena al |
|             |             |             |             | estudiante  |
|             |             |             |             | que es      |
|             |             |             |             | dueño de la |
|             |             |             |             | boleta      |
+-------------+-------------+-------------+-------------+-------------+
|             | final_grade | Double      | NOT NULL    | Almacena el |
|             |             |             |             | promedio    |
|             |             |             |             | final de un |
|             |             |             |             | curso       |
+-------------+-------------+-------------+-------------+-------------+
|             | isApproved  | Bool        | NOT NULL    | Bandera que |
|             |             |             |             | determina   |
|             |             |             |             | si el       |
|             |             |             |             | alumno      |
|             |             |             |             | aprobó o no |
|             |             |             |             | un curso    |
+-------------+-------------+-------------+-------------+-------------+
