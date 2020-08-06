
***************
Diagrama Entidad Relación
***************


## Diagrama Entidad Relación
![v1 0](https://user-images.githubusercontent.com/58009248/89479317-1c4b1d00-d758-11ea-97af-5718a301042a.png)


Descripción de tablas
-----------

.. list-table:: 
    :widths: 10 10 100
    :header-rows: 1
    :stub-columns: 1

    * - NOMBRE DE TABLA
      - CLAVE PRIMARIA
      - DESCRIPCIÓN
    * - USER
      - id_user
      - Almacena el código (llave primaria), nombre, apellidos, email  y password del usuario.
    * - PROFESOR
      - id_profesor
      - La tabla se encarga de guardar la información del id de un profesor y la valoración que tiene éste(Si es un buen o mal profesor) como referencias.
    * - STUDENT
      - id_student
      - Esta tabla sólo se encargará de almacenar los identificadores de los estudiantes.
    * - COURSE_HISTORY
      - id_course_history
      - La tabla de COURSE_HISTORY existe para guardar su llave primaria, la llave foránea de un profesor para así saber qué cursos ha impartido a lo largo de su estancia en nuestra aplicación y la llave primaria del tabla COURSE
    * - COURSE
      - id_course
      - Se retiene información a cerca de la llave primaria del curso, llave foránea del profesor, título o nombre de la asignatura, una breve descripción del curso, el temario, fecha de inicio, fecha de finalización, requerimientos y si es privado o público el curso.
    * - TOPIC
      - id_topic
      - Nos ayuda a preservar información de la llave primaria de éste, la llave foránea del curso a la cual pertenece, y el nombre del tema o sección.
    * - GROUP
      - id_group
      - Esta tabla mantendrá datos del grupo; el id primario, la llave foránea del estudiante y la llave foránea del course al que pertenece.
    * - EXAMINATION
      - id_examination
      - Nos ayuda a guardar toda la información referente a las pruebas aplicadas por un profesor; el id de la evaluación, la llave foránea del estudiante, la llave foránea del tema, el tipo de examen que se aplicará, nombre del examen, calificación y  la llave foránea de la calificación final
    * - FINAL_GRADE
      - id_final_grade
      - Esta tabla se encarga de la información de la calificación final de un estudiante, facilita a que persistan los siguientes datos; llave primaria de la calificación final, la llave foránea de la prueba, la llave foránea del estudiante, la calificación final y un campo para determinar si aprobó la materia.


Diccionario de datos
-----------

USER
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - P
      - id_user
      - Integer
      - NULL
      - Almacena el código que identifica a cada usuario
      
STUDENT
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PFK
      - id_student
      - Integer
      - NULL
      - Almacena el código que identifica a cada estudiante
      
PROFESSOR
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PFK
      - id_professor
      - Integer
      - NULL
      - Almacena el código que identifica a cada profesor
      
COURSE
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PFK
      - id_course
      - Varchar(50)
      - NOT NULL
      - Almacena el código que identifica un curso
    * - FK
      - id_professor
      - Integer
      - NOT NULL
      - Es el profesor que imparte el curso
    * - 
      - title
      - Varchar(50)
      - NOT NULL
      - Nombre que describa el curso
    * - 
      - description
      - Varchar(50)
      - NOT NULL
      - Es el profesor que imparte el curso
    * - FK
      - id_professor
      - Integer
      - NOT NULL
      - Almacena una descripción más detallada del curso
    * - 
      - syllabus
      - Varchar(500)
      - NOT NULL
      - Almacena el temario del curso
    * - 
      - start_date
      - Date
      - NULL
      - Almacena la fecha inicial del curso
    * - 
      - end_date
      - Date
      - NULL
      - Almacena la fecha final del curso
    * - 
      - requirements
      - Varvhar(50)
      - NOT NULL
      - **Este campo está en proceso de discusión**
    * - 
      - isPrivate
      - Bool
      - NOT NULL
      - Bandera de estado que determina si el curso es privado o público **Este campo está en proceso de discusión**

COURSE_HISTORY
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - P
      - id_course_history
      - Integer
      - NOT NULL
      - **Este campo debe ser discutido**
    * - FK
      - id_professor
      - Integer
      - NOT NULL
      - Profesor que impartió el curso
    * - 
      - id_course
      - VARCHAR(50
      - NOT NULL
      - Almacena el código que identifica a cada curso impartido por un profesor

COURSE_HISTORY
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PK
      - id_topic
      - Integer
      - NOT NULL
      - Almacena el código que identifica un tema o módulo del curso
    * - FK
      - id_course
      - VARCHAR(50)
      - NOT NULL
      - identificador del curso que determina
      
EXAMINATION
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PK
      - id_examination
      - Integer
      - NOT NULL
      - falta descripción
    * - FK
      - id_student
      - Integer
      - NOT NULL
      - falta descripción
    * - FK
      - id_topic
      - Integer
      - NOT NULL
      - falta descripción
    * - 
      - tipo
      - Varchar(50)
      - NOT NULL
      - falta descripción
    * - 
      - name
      - Varchar(50)
      - NOT NULL
      - falta descripción
    * - 
      - grade
      - Double
      - NOT NULL
      - falta descripción
    * - FK
      - id_grade
      - Integer
      - NOT NULL
      - falta descripción
      
GROUP
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PK
      - id_group
      - Integer
      - NOT NULL
      - Almacena el código que identifica a un grupo
    * - FK
      - id_student
      - Integer
      - NOT NULL
      - Estudiante que esta en el grupo
    * - FK
      - id_course
      - Varchar(50)
      - NOT NULL
      - Curso que se imparte en el grupo
      
FINAL_GRADE
^^^^^^

.. list-table:: 
    :widths: 5 10 10 10 50
    :header-rows: 1
    :stub-columns: 1

    * - Clave
      - Campo
      - Tipo de Atributo
      - Es Nulo
      - DESCRIPCIÓN
    * - PK
      - id_grade
      - Integer
      - NOT NULL
      - Almacena el código que identifica a una boleta
    * - FK
      - id_examination
      - Integer
      - NOT NULL
      - test/pruebas presentadas por el alumno para poder realizar el calculo del promedio final
    * - FK
      - id_student
      - Integer
      - NOT NULL
      - Almacena al estudiante que es dueño de la boleta
    * - 
      - final_grade
      - Double
      - NOT NULL
      - Almacena el promedio final de un curso
    * - 
      - isApproved
      - Bool
      - NOT NULL
      - ABandera que determina si el alumno aprobó o no un curso


