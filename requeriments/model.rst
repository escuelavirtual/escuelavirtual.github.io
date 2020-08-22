
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


.. list-table:: Control de Versiones
    :widths: 10 10 50 5
    :header-rows: 1

    * - Usuario de Github
      - Aporte
      - Descripcion
      - Versión
    * - `@Sergio-DC`_, `@lalo1234321`_, `@VidalAlvarez`_
      - Diseño del diagrama ER
      - Se discutió acerca del diseño de la base de datos relacional
      - **v1.0.0-040820**
    * - `@lalo1234321`_
      - Se eliminó la tabla de couse_history
      - La relación entre el profesor y el curso se puede interpretar de dos formas respecto a las reglas de negocio: 1) El profesor puede crear uno o varios cursos. 2) El profesor ha impartido uno o varios cursos (implicitamente se entiende que el profesor ya tiene un historial de curso, por lo tanto, se elimina la entidad intermediaria).
      - **v1.1.0-060820**
    * - `@Sergio-DC`_ , `@lalo1234321`_
      - Modificaciones importantes de la base de datos
      - La primera modificación que se realizó fue el cambio de nombre de la tabla FINAL_GRADE a GRADE_REPORT, se analizó la relación entre GRADE_REPORT y EXAMINATION y se llegó a la conclusón de que la relación estabaa de más, de ésta forma sólo exisitiría la relación de FINAL_GRADE y STUDENT para poder acceder a todas la evaluaciones que realice y así obtener su boleta.
      - **v1.2.0-060820**
    * - `@Sergio-DC`_ , `@lalo1234321`_
      - Se agregaron entidades al modelo y cambios importantes en la base de datos
      - Se eliminó una de las dos relaciones que había entre PROFESOR Y COURSE, se agregaron 4 tablas: ANSWER, QUESTION,MODULE y GROUP_ACTIVITY
      - **v1.3.0-070820**
    * - `@VidalAlvarez`_
      - Se agregó la propiedades +codigo
      - Entidades Modificadas COURSE, GROUP, y STUDENT. Permitirá relacionar las entidades al ingresar al portal
      - **v1.4.0-080820**
    * - `@lalo1234321`_
      - Se agregaron campos a la tabla de curso
      - Se agregó el campo rating con el fin de calificar un curso y el campo de category fue añadido en esta versión para que un usuario pueda buscar un curso según su categoría.
      - **v1.5.0-110820**
    * - `@lalo1234321`_ , `@fernando3600`_
      - Cambios en la tabla COURSE
      - Se renombró el campo de id_category por category, de la tabla COURSE, éste campo será la relación que se generará con COURSE Y CATEGORY
      - **v1.5.0-150820**
    * - `@lalo1234321`_
      - Cambios en la tabla STUDENT,modificaciones en todas las tablas y eliminación de tablas
      - Se renombró el campo id_student por id, además se cambió la propiedad primary foreign key por primary key, y se agregó un campo para el id_user que será la llave foránea de la relación entre user y student. Las modificaciones que se realizaron en todas la tablas fueron en su campo de llave primaria fueron renombradas de id_nombreDeLaTabla a id, se eliminó la tabla de GROUP y STUDENT pasó a tener un relación de muchos a muchos con COURSE, por lo que se creó una nueva entidad de fungiera como unión de ambas tablas, la tabla tiene por nombre ENROLLMENT
      - **v1.6.0-180820**


.. _@Sergio-DC: https://github.com/Sergio-DC

.. _@VidalAlvarez: https://github.com/ReynaldoAlvarez 

.. _@lalo1234321: https://github.com/lalo1234321

.. _@fernando3600: https://github.com/fernando3600

Diagrama Entidad Relación
==============

`Link para editar el diagrama`_ |Tabla_versiones|

.. _Link para editar el diagrama: https://app.lucidchart.com/invitations/accept/4e829d59-8b8f-448f-a828-7677a8c0870e

.. |Tabla_versiones| image:: https://user-images.githubusercontent.com/64877172/90570073-a17cfb80-e174-11ea-8bf8-407bd09e90ec.png

   
Descripción de tablas
=====================


.. list-table:: Descripción de tablas
    :widths: 10 80
    :header-rows: 1
    
    * - NOMBRE DE TABLA
      - DESCRIPCIÓN
    * - USER
      - Representa una coleecion de un usuarios. Los usuarios pueden tener diferentes roles, los estudiantes y profesores tendran el rol de usuario. Luego existe el rol de moderador y el rol de administrador.
    * - PROFESSOR
      - Representa una coleccion de profesores o instructores. Cada profesor esta asociado a un usuario.
    * - STUDENT
      - Representa una coleccion de estudiantes o alumnos. Cada estudiante esta asociado a un usuario.
    * - COURSE
      - Representa una coleccion de cursos. En esta coleccion, solo se almacena los metadatos del curso, como el titulo, la descripcion, la visibilidad, entre otros detalles. Cada curso esta asociado a un profesor.
    * - MODULE
      - Representa una coleccion de modulos o bloques de contenido en las cuales se pueden dividir un curso. Cada modulo esta asociado a un curso.
    * - TOPIC
      - Representa una coleccion de topicos o documentos. Esta tabla almancenara el contenido de un documento. Si el formato sera de texto plano, el contenido se guardara directamente en esta tabla, si el mismo sera de formato video, pdf u otro archivo embebido, se almacenara su url. Cada topico o documento esta asociado a un modulo.
    * - EXAMINATION
      - Representa una coleccion de examenes o evaluaciones. Cada evaluacion esta asociado a un modulo de un curso. 
    * - QUESTION
      - Representa una coleccion de preguntas y respuestas en caso de que las haya. Cada pregunta esta asociada a un examen.
    * - GROUP_ACTIVITY
      - Representa una coleccion de grupos de estudio dentro de un curso. Cada grupo esta asoaciado a un curso.
    * - GRADE_REPORT_PER_COURSE
      - Esta tabla almacenará la boleta del estudiante de un curso, los campos que tiene esta tabla son su llave primaria la llave foránea generada por la relación de esta tabla con STUDENT, el campo final_grade y isApproved, que determinará si el estudiante pasó el curso.
    * - ENROLLMENT
      - En esta tabla, se visualizan las relaciones de un estudiante con un curso. El listado de estudiantes de un curso o los cursos que un estudiante esta inscripto, se muestran en esta coleccion.
    * - CATEGORY
      - Representa una coleccion de categorias o ejes tematicos principales que tendra la plataforma.

Diccionario de Datos
==============

USER
~~~~

+-------+-----------+------------------+----------+------------------+
| Clave | Campo     | Tipo de Atributo | Es Nulo  | Descripción      |
+=======+===========+==================+==========+==================+
| P     | id        | Integer          | NULL     | Almacena el      |
|       |           |                  |          | código que       |
|       |           |                  |          | identifica a     |
|       |           |                  |          | cada usuario     |
+-------+-----------+------------------+----------+------------------+
|       | firstname | Varchar          | NOT NULL | Guarda el nombre |
|       |           |                  |          | de un usuario    |
+-------+-----------+------------------+----------+------------------+
|       | lastname  | Varchar          | NOT NULL | Conserva los     |
|       |           |                  |          | datos de los     |
|       |           |                  |          | apellidos        |
+-------+-----------+------------------+----------+------------------+
|       | email     | Varchar          | NOT NULL | Almacena datos   |
|       |           |                  |          | del correeo de   |
|       |           |                  |          | un usuario       |
+-------+-----------+------------------+----------+------------------+
|       | password  | Varchar          | NOT NULL | Guardar la       |
|       |           |                  |          | contraseña de un |
|       |           |                  |          | usuario          |
+-------+-----------+------------------+----------+------------------+

STUDENT
~~~~~~~

+-------+----------------+----------------+----------+----------------+
| Clave | Campo          | Tipo de        | Es Nulo  | Descripción    |
|       |                | Atributo       |          |                |
+=======+================+================+==========+================+
| P     | id             | Integer        | NULL     | Almacena el    |
|       |                |                |          | código que     |
|       |                |                |          | identifica a   |
|       |                |                |          | cada           |
|       |                |                |          | estudiante     |
+-------+----------------+----------------+----------+----------------+
| F     | id_            | Integer        | NOT NULL | Guarda la      |
|       | group_activity |                |          | relación con   |
|       |                |                |          | la tabla       |
|       |                |                |          | GROUP_ACTIVITY |
+-------+----------------+----------------+----------+----------------+
| F     | id_user        | Integer        | NOT NULL | Guarda la      |
|       |                |                |          | relación con   |
|       |                |                |          | la tabla USER  |
+-------+----------------+----------------+----------+----------------+
|       | code           | Varchar        | NOT NULL | Guarda el      |
|       |                |                |          | código de un   |
|       |                |                |          | estudiante     |
+-------+----------------+----------------+----------+----------------+

PROFESSOR
~~~~~~~~~

+-------+--------------+--------------+--------------+--------------+
| Clave | Campo        | Tipo de      | Es Nulo      | Descripción  |
|       |              | Atributo     |              |              |
+=======+==============+==============+==============+==============+
| P     | id_professor | Integer      | NULL         | Almacena el  |
|       |              |              |              | código que   |
|       |              |              |              | identifica a |
|       |              |              |              | cada         |
|       |              |              |              | profesor     |
+-------+--------------+--------------+--------------+--------------+
| F     | id_user      | Integer      | NOT NULL     | Guarda la    |
|       |              |              |              | relación de  |
|       |              |              |              | PROFESSOR    |
|       |              |              |              | con USER     |
+-------+--------------+--------------+--------------+--------------+
|       | valuation    | Integer      | Almacena la  |              |
|       |              |              | valoración   |              |
|       |              |              | que tiene un |              |
|       |              |              | profesor     |              |
+-------+--------------+--------------+--------------+--------------+

COURSE
~~~~~~

+-------+--------------+----------------+----------+----------------+
| Clave | Campo        | Tipo de        | Es Nulo  | Descripción    |
|       |              | Atributo       |          |                |
+=======+==============+================+==========+================+
| P     | id           | Varchar(50)    | NOT NULL | Almacena el    |
|       |              |                |          | código que     |
|       |              |                |          | identifica un  |
|       |              |                |          | curso          |
+-------+--------------+----------------+----------+----------------+
| F     | id_professor | Integer        | NOT NULL | Es el profesor |
|       |              |                |          | que imparte el |
|       |              |                |          | curso          |
+-------+--------------+----------------+----------+----------------+
| F     | category     | Integer        | NOT NULL | Es la          |
|       |              |                |          | categoría a la |
|       |              |                |          | que pertenece  |
|       |              |                |          | el curso       |
+-------+--------------+----------------+----------+----------------+
|       | title        | Varchar(50)    | NOT NULL | Nombre que     |
|       |              |                |          | describa el    |
|       |              |                |          | curso          |
+-------+--------------+----------------+----------+----------------+
|       | description  | Varchar(50)    | NOT NULL | Almacena una   |
|       |              |                |          | descripción    |
|       |              |                |          | más detallada  |
|       |              |                |          | del curso      |
+-------+--------------+----------------+----------+----------------+
|       | startedAt    | Date           | NULL     | Almacena la    |
|       |              |                |          | fecha inicial  |
|       |              |                |          | del curso      |
+-------+--------------+----------------+----------+----------------+
|       | finishedAt   | Date           | NULL     | Almacena la    |
|       |              |                |          | fecha final    |
|       |              |                |          | del curso      |
+-------+--------------+----------------+----------+----------------+
|       | requirements | Varvhar(50)    | NOT NULL | **Este campo   |
|       |              |                |          | está en        |
|       |              |                |          | proceso de     |
|       |              |                |          | discusión**    |
+-------+--------------+----------------+----------+----------------+
|       | isPrivate    | Bool           | NOT NULL | Bandera de     |
|       |              |                |          | estado que     |
|       |              |                |          | determina si   |
|       |              |                |          | el curso es    |
|       |              |                |          | privado o      |
|       |              |                |          | público **Este |
|       |              |                |          | campo está en  |
|       |              |                |          | proceso de     |
|       |              |                |          | discusión**    |
+-------+--------------+----------------+----------+----------------+
|       | code         | Varchar        | NOT NULL | Es el código   |
|       |              |                |          | que se le dará |
|       |              |                |          | al curso que   |
|       |              |                |          | es privado     |
+-------+--------------+----------------+----------+----------------+
|       | rating       | Double         | NOT NULL | En este        |
|       |              |                |          | apartado se le |
|       |              |                |          | asigna la      |
|       |              |                |          | valoración del |
|       |              |                |          | curso          |
+-------+--------------+----------------+----------+----------------+

CATEGORY
~~~~~~~~

+-------+-------+------------------+----------+--------------------+
| Clave | Campo | Tipo de Atributo | Es Nulo  | Descripción        |
+=======+=======+==================+==========+====================+
| P     | id    | Integer          | NOT NULL | La lllave primaria |
|       |       |                  |          | de la categoría    |
+-------+-------+------------------+----------+--------------------+
|       | name  | Varchar          | NOT NOLL | Nombre de la       |
|       |       |                  |          | categoría          |
+-------+-------+------------------+----------+--------------------+
|       | slug  | Varchar          | NOT NULL | Alternativa de     |
|       |       |                  |          | búsqueda para el   |
|       |       |                  |          | frontend           |
+-------+-------+------------------+----------+--------------------+

TOPIC
~~~~~

+-------+-------------+----------------+----------+----------------+
| Clave | Campo       | Tipo de        | Es Nulo  | Descripción    |
|       |             | Atributo       |          |                |
+=======+=============+================+==========+================+
| P     | id          | Integer        | NOT NULL | Almacena el    |
|       |             |                |          | código que     |
|       |             |                |          | identifica un  |
|       |             |                |          | tema o módulo  |
|       |             |                |          | del curso      |
+-------+-------------+----------------+----------+----------------+
|       | name_topic  | Varchar        | NOT NULL | Nombre del     |
|       |             |                |          | tema a         |
|       |             |                |          | estudiar       |
+-------+-------------+----------------+----------+----------------+
|       | description | Varchar        | NOT NULL | La descripción |
|       |             |                |          | del tema       |
+-------+-------------+----------------+----------+----------------+

EXAMINATION
~~~~~~~~~~~

+-------+----------------+----------------+----------+----------------+
| Clave | Campo          | Tipo de        | Es Nulo  | Descripción    |
|       |                | Atributo       |          |                |
+=======+================+================+==========+================+
| P     | id             | Integer        | NOT NULL | Clave primaria |
+-------+----------------+----------------+----------+----------------+
| F     | id_student     | Integer        | NOT NULL | Relación con   |
|       |                |                |          | STUDENT        |
+-------+----------------+----------------+----------+----------------+
| F     | id_module      | Integer        | NOT NULL | Relación con   |
|       |                |                |          | MODULE         |
+-------+----------------+----------------+----------+----------------+
|       | type           | Varchar(50)    | NOT NULL | Es el tipo de  |
|       |                |                |          | examen que se  |
|       |                |                |          | aplicará,      |
|       |                |                |          | opción         |
|       |                |                |          | múltiple o de  |
|       |                |                |          | pregunta       |
|       |                |                |          | abierta        |
+-------+----------------+----------------+----------+----------------+
|       | na             | Varchar(50)    | NOT NULL | Nombre del     |
|       | me_examination |                |          | examen         |
+-------+----------------+----------------+----------+----------------+
|       | grade          | Double         | NOT NULL | La             |
|       |                |                |          | calificaación  |
|       |                |                |          | de un examen   |
+-------+----------------+----------------+----------+----------------+

GROUP_ACTIVITY
~~~~~~~~~~~~~~

+-------+---------------+----------------+----------+----------------+
| Clave | Campo         | Tipo de        | Es Nulo  | Descripción    |
|       |               | Atributo       |          |                |
+=======+===============+================+==========+================+
| P     | id            | Integer        | NOT NULL | Llave primaria |
|       |               |                |          | de la tabla    |
+-------+---------------+----------------+----------+----------------+
| F     | id_module     | Integer        | NOT NULL | Llave foránea  |
|       |               |                |          | de MODULE con  |
|       |               |                |          | ésta           |
+-------+---------------+----------------+----------+----------------+
|       | activity_name | Varchar        | NOT NULL | Nombre de la   |
|       |               |                |          | actividad      |
+-------+---------------+----------------+----------+----------------+
|       | instructions  | Varchar        | NOT NULL | Instrucciones  |
|       |               |                |          | de la          |
|       |               |                |          | actividad      |
+-------+---------------+----------------+----------+----------------+
|       | grade         | DOUBLE         | NULL     | La             |
|       |               |                |          | calificación   |
|       |               |                |          | que se le      |
|       |               |                |          | otorgará a un  |
|       |               |                |          | estudiante     |
+-------+---------------+----------------+----------+----------------+
|       | comments      | Varchar        | NULL     | Comentarios    |
|       |               |                |          | acerca de la   |
|       |               |                |          | actividad una  |
|       |               |                |          | vez que es     |
|       |               |                |          | calificada     |
+-------+---------------+----------------+----------+----------------+

GRADE_PER_COURSE
~~~~~~~~~~~~~~~~

+-------+-------------+----------------+----------+----------------+
| Clave | Campo       | Tipo de        | Es Nulo  | Descripción    |
|       |             | Atributo       |          |                |
+=======+=============+================+==========+================+
| P     | id          | Integer        | NOT NULL | Llave primaria |
|       |             |                |          | de la boleta   |
+-------+-------------+----------------+----------+----------------+
| F     | id_student  | Integer        | NOT NULL | Relación de    |
|       |             |                |          | STUDENT con    |
|       |             |                |          | GRA            |
|       |             |                |          | DEE_PER_COURSE |
+-------+-------------+----------------+----------+----------------+
|       | final_grade | DOUBLE         | NOT NULL | La             |
|       |             |                |          | calificación   |
|       |             |                |          | que obtiene un |
|       |             |                |          | estudiante al  |
|       |             |                |          | finalizar un   |
|       |             |                |          | curso          |
+-------+-------------+----------------+----------+----------------+
|       | isApproved  | Bool           | NOT NULL | Determina si   |
|       |             |                |          | pasó la        |
|       |             |                |          | materia el     |
|       |             |                |          | estudiante o   |
|       |             |                |          | no             |
+-------+-------------+----------------+----------+----------------+

MODULE
~~~~~~

+-------+-------------+----------------+----------+----------------+
| Clave | Campo       | Tipo de        | Es Nulo  | Descripción    |
|       |             | Atributo       |          |                |
+=======+=============+================+==========+================+
| P     | id          | Integer        | NOT NULL | Llave primaria |
|       |             |                |          | de MODULE      |
+-------+-------------+----------------+----------+----------------+
| F     | id_course   | Varchar        | NOT NULL | Relación de    |
|       |             |                |          | COURSE con     |
|       |             |                |          | MODULE         |
+-------+-------------+----------------+----------+----------------+
|       | description | Varchar        | NOT NULL | La             |
|       |             |                |          | descrripción   |
|       |             |                |          | del modulo o   |
|       |             |                |          | unidad         |
+-------+-------------+----------------+----------+----------------+

ENROLLMENT
~~~~~~~~~~

+-------+------------+------------------+----------+------------------+
| Clave | Campo      | Tipo de Atributo | Es Nulo  | Descripción      |
+=======+============+==================+==========+==================+
| F     | id_student | Integer          | NOT NULL | Relación entre   |
|       |            |                  |          | STUDENT Y        |
|       |            |                  |          | ENROLLMENT       |
+-------+------------+------------------+----------+------------------+
| F     | id_course  | Integer          | NOT NULL | Relación entre   |
|       |            |                  |          | COURSE Y         |
|       |            |                  |          | ENROLLMENT       |
+-------+------------+------------------+----------+------------------+

QUESTION
~~~~~~~~

+-------+----------------+----------------+----------+----------------+
| Clave | Campo          | Tipo de        | Es Nulo  | Descripción    |
|       |                | Atributo       |          |                |
+=======+================+================+==========+================+
| P     | id             | Integer        | NOT NULL | Llave primaria |
|       |                |                |          | de QUESTION    |
+-------+----------------+----------------+----------+----------------+
| F     | id_examination | Integer        | NOT NULL | Relación entre |
|       |                |                |          | EXAMINATION y  |
|       |                |                |          | QUESTION       |
+-------+----------------+----------------+----------+----------------+
|       | content        | Varchar        | NOT NULL | Se guarda el   |
|       |                |                |          | contenido de   |
|       |                |                |          | la pregunta    |
+-------+----------------+----------------+----------+----------------+
|       | open_answer    | Varchar        | NULL     | Se guarda el   |
|       |                |                |          | contenido de   |
|       |                |                |          | la pregunta en |
|       |                |                |          | caso de que    |
|       |                |                |          | ésta sea de    |
|       |                |                |          | opción         |
|       |                |                |          | múltiple       |
+-------+----------------+----------------+----------+----------------+

ANSWER
~~~~~~

+-------+-------------+----------------+----------+----------------+
| Clave | Campo       | Tipo de        | Es Nulo  | Descripción    |
|       |             | Atributo       |          |                |
+=======+=============+================+==========+================+
| F     | id_question | Integer        | NOT NULL | Relación entre |
|       |             |                |          | QUESTION y     |
|       |             |                |          | ANSWER         |
+-------+-------------+----------------+----------+----------------+
|       | content     | Varchar        | NOT NULL | Contenido de   |
|       |             |                |          | la respuesta   |
+-------+-------------+----------------+----------+----------------+
|       | isTrue      | Bool           | NOT NULL | Determina si   |
|       |             |                |          | es correcta la |
|       |             |                |          | respuesta o no |
+-------+-------------+----------------+----------+----------------+
