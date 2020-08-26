---
layout: default
title: Ejemplo TDD con Node
parent: Tutorials
nav_order: 2
---

# Ejemplo TDD con Node
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Example TDD in Node Js

### Uso de la [metodología TDD](https://es.wikipedia.org/wiki/Desarrollo_guiado_por_pruebas) en una aplicación de ejemplo, desarrollada en Node Js

Según Wikipedia, el significado de la metodología Test Driven Development o TDD por sus siglas en ingles, es la siguiente:

> Desarrollo guiado por pruebas de software, o Test-driven development (TDD) es una práctica de ingeniería de software que involucra otras dos prácticas: Escribir las pruebas primero (Test First Development) y Refactorización (Refactoring). Para escribir las pruebas generalmente se utilizan las pruebas unitarias (unit test en inglés). En primer lugar, se escribe una prueba y se verifica que la nueva prueba falla. A continuación, se implementa el código que hace que la prueba pase satisfactoriamente y seguidamente se refactoriza el código escrito. El propósito del desarrollo guiado por pruebas es lograr un código limpio que funcione. La idea es que los requisitos sean traducidos a pruebas, de este modo, cuando las pruebas pasen se garantizará que el software cumple con los requisitos que se han establecido. - Wikipedia

En este tutorial, vamos a desarrollar una aplicación que simule el comportamiento de una lista de tareas, los conocidos ToDo List.

### Requerimientos

Inicialmente debemos conocer cuales serán los requerimientos de esta aplicación, para poder desarrollar los tests.

1. El usuario debe poder agregar una tarea a su lista.
2. El usuario debe poder  consultar el listado de todas las tareas
3. El usuario debe poder eliminar una tarea de su lista.
4. El usuario debe poder cambiar el estado de su tarea en cualquier momento.

Para este ejemplo, no vamos a implementar ningún tipo de autenticación. 

En primer lugar, debemos configurar un entorno de trabajo con NodeJs, utilizamos Express y realizaremos los test con Mocha + Chai. Para eso he creado un repositorio limpio utilizando como base, un [boilerplate](https://github.com/madhums/node-express-mongoose-demo.git), solamente he removido un par de librerias y le añadi las dependencias para los tests.

El codigo final con sus correspondientes pasos estarán disponible en [https://github.com/alejandro088/tdd-node-example/](https://github.com/alejandro088/tdd-node-example/tree/01-getting-started)

Para comenzar con el ejemplo, deben dirigirse a la rama `01-getting-started` del repositorio.

### Elegir un requisito

El primer paso consiste en seleccionar un requisito de la lista previamente confeccionada. En esta primer ocasión vamos a elegir el requerimiento número 1. Hay que tener en cuenta que, los primeros requisitos deben ser fáciles de implementar.

Primer requisito: El usuario debe poder agregar una tarea a su lista.

Debemos determinar que datos el usuario necesita ingresar a la lista. Si ya contamos con las especificaciones del proceso, este paso es sencillo. Para este ejemplo, vamos a decirle que nuestro datos de entrada es el titulo y la descripción de la tarea. A partir de estos datos deseamos obtener un identificador, la fecha de creación, el estado inicial de la tarea y la fecha de actualización. Vamos a mantener lo mas simple esta aplicación de ejemplo.

### Escribir una prueba

A partir de este punto, ya tenemos especificado cuales serán nuestras entradas y nuestras salidas. En este paso debemos comprender claramente cuales son los requerimientos de la funcionalidad que vamos a implementar.

Creamos un archivo de tests, llamado `test-create-a-task.js` y lo ubicamos dentro de la carpeta `test`

Ahora creamos dentro de ese archivo, nuestro primer test con la siguiente estructura.

```jsx
const chai = require('chai');
const chaiHttp = require('chai-http');
const app = require('../server');
const { expect } = chai;
chai.use(chaiHttp);

describe('Task tests', () => {

    describe('create a task', () => {

        //Aqui comienza el test.
        it('should return a task created', (done) => {            

            chai.request(app)
                .post('/tasks')
                .send({                    
                    'title': 'My first task',
                    'description': 'This task is for a demo  example'
                })
                .end(function(err, res){

                    if (err) done(err)

                    expect(res).to.have.status(201);
                    expect(JSON.parse(res.text)).to.have.all.keys('id', 'title', 'description', 'status', 'created_at', 'updated_at');
                    done()
                   
                });
        })
    })
})
```

¿Qué observamos aquí? Chai al llamar `request(app)` nos inicia el servidor, luego como vamos a agregar una tarea, debemos pasarle un endpoint con el verbo POST.

```jsx
// POST: http://localhost:3000/tasks
.post('/tasks')
```

Luego le pasamos los datos que le enviaremos al servidor.

```jsx
.send({                    
    'title': 'My first task',
    'description': 'This task is for a demo  example'
})
```

Por ultimo, en la sección end, le pasamos una función que contendrá todo lo que esperamos recibir

```jsx
.end(function(err, res){
			//si ocurre un error inesperado finalizar el proceso.
      if (err) done(err)
      
      //aqui detallamos lo que esperamos recibir como respuesta a la peticion
      expect(res).to.have.status(201);
      expect(JSON.parse(res.text)).to.have.all.keys('id', 'title', 'description', 'status', 'created_at', 'updated_at');
      done()
     
  });
```

En este ejemplo, esperamos que nuestro codigo de estado sea 201, ya que estamos creando un recurso. Ademas esperamos que en el mensaje nos retorne un JSON con las propiedades id, title, description , status, created_at y updated_at.

Puedes ver más aserciones en la documentación de chai:  [https://www.chaijs.com/](https://www.chaijs.com/)

Ejecutamos el test en la terminal.

```jsx
npm run test
```

Como era de esperarse, el test ha fallado.

```bash
Task tests
    create a task
      1) should return a task created

  0 passing (469ms)
  1 failing

  1) Task tests
       create a task
         should return a task created:

      Uncaught AssertionError: expected { Object (_events, _eventsCount, ...) } to have status code 201 but got 404
      + expected - actual

      -404
      +201

      at C:\Users\Alejandro\Desktop\node-express\test\test-create-a-task.js:26:41
      at Test.Request.callback (node_modules\superagent\lib\node\index.js:716:12)
      at C:\Users\Alejandro\Desktop\node-express\node_modules\superagent\lib\node\index.js:916:18
      at IncomingMessage.<anonymous> (node_modules\superagent\lib\node\parsers\json.js:19:7)
      at endReadableNT (_stream_readable.js:1220:12)
      at processTicksAndRejections (internal/process/task_queues.js:84:21)
```

Si les aparece otro error diferente a éste, puede que no tenga correctamente configurado el comando test de su `package.json`. Para este ejemplo, en este repositorio de prueba, los scripts son los siguientes.

```json
"scripts": {
    "start": "nodemon server.js",
    "debug": "nodemon --debug server.js",
    "test": "mocha test/ --recursive --exec babel-node --exit"
  },
```

### Verificar que la prueba falla

Como observamos, los errores suelen ser descriptivos, en este caso, nos dice que esperabamos un codigo de estado 201 y nos devolvió un codigo de estado 404, es decir, recurso no encontrado. Como no tenemos nada implementado, la razón de este mensaje es que, al acceder al endpoint `/tasks` mediante el metodo POST, no existe.

Si nuestra prueba no hubiera fallado, es porque el requisito ya estaba implementado o bien, hemos hecho mal la prueba.

### Escribir la implementación

En este punto, vamos a implementar el código más simple posible para que la prueba no falle.

Nos dirigimos al archivo `routes.js` y escribimos lo siguiente a continuación de la ruta home:

```jsx
// add task
  app.post('/tasks', function(req, res) {
    res.status(201).json({
      id: 1,
      title:  req.body.title,
      description: req.body.description,
      status: 'to do',
      created_at: '24/08/2020',
      updated_at: '24/08/2020'
    });
  });
```

Corremos el test con `npm run test` y comprobamos el resultado.

```bash
Task tests
    create a task
      √ should return a task created (413ms)

  1 passing (553ms)
```

Nuestro primer test ha pasado. Simple, verdad? Pues, no tan simple. Todo no termina aquí, ahora debemos crear otro caso. Por ejemplo, que pasa si el usuario no ingresa un titulo o una descripción. Vamos a ellos. Actualizamos la suite de pruebas. A continuación del cierre del primer `it`, escribimos lo siguiente:

```bash
it('should return an error if title is empty', (done) => {            

    chai.request(app)
        .post('/tasks')
        .send({                    
            'description': 'This task is for a demo  example'
        })
        .end(function(err, res){

            if (err) done(err)
            //console.log(res)

            expect(JSON.parse(res.text)).to.own.include({error: 'title does not exists!'});
            expect(res).to.have.status(500)

            done()
           
        });
})

it('should return an error if description is empty', (done) => {            

    chai.request(app)
        .post('/tasks')
        .send({                    
            'title': 'My first task'
        })
        .end(function(err, res){

            if (err) done(err)
            //console.log(res)

            expect(JSON.parse(res.text)).to.own.include({error: 'description does not exists!'});
            expect(res).to.have.status(500)

            done()
           
        });
})
```

Aquí creamos dos casos de prueba mas para nuestro primer test, en el primero indicamos que debe pasar cuando no ingresamos el titulo, y en el segundo, lo mismo con la descripción. 

Nótese las descripciones que se muestran en la función it(..). Deben ser lo mas descriptivas posibles.

Ejecutamos los test.

```bash
Task tests     
    create a task
      √ should return a task created (837ms)
      1) should return an error if title is empty
      2) should return an error if description is empty

  1 passing (2s)
  2 failing

  1) Task tests
       create a task
         should return an error if title is empty:
     Uncaught AssertionError: expected { Object (id, description, ...) } to have own property 'error'     
      at C:\Users\Alejandro\Desktop\node-express\test\test-create-a-task.js:46:57
      at Test.Request.callback (node_modules\superagent\lib\node\index.js:716:12)
      at C:\Users\Alejandro\Desktop\node-express\node_modules\superagent\lib\node\index.js:916:18
      at IncomingMessage.<anonymous> (node_modules\superagent\lib\node\parsers\json.js:19:7)
      at endReadableNT (_stream_readable.js:1220:12)
      at processTicksAndRejections (internal/process/task_queues.js:84:21)

  2) Task tests
       create a task
         should return an error if description is empty:
     Uncaught AssertionError: expected { Object (id, title, ...) } to have own property 'error'
      at C:\Users\Alejandro\Desktop\node-express\test\test-create-a-task.js:66:57
      at Test.Request.callback (node_modules\superagent\lib\node\index.js:716:12)
      at C:\Users\Alejandro\Desktop\node-express\node_modules\superagent\lib\node\index.js:916:18
      at IncomingMessage.<anonymous> (node_modules\superagent\lib\node\parsers\json.js:19:7)
      at endReadableNT (_stream_readable.js:1220:12)
      at processTicksAndRejections (internal/process/task_queues.js:84:21)
```

Los errores son bastantes descriptivos, no requieren demasiada explicación, vamos a implementar la menor lógica posible en nuestro endpoint `/tasks` del archivo `routes.js` para que los tests no fallen.

```jsx
app.post('/tasks', function(req, res) {
    
   //se añadió unas validaciones 
   if (!req.body.title) {
      res.status(500).json({error: 'title does not exists!'});
    } else if (!req.body.description) {
      res.status(500).json({error: 'description does not exists!'});
    } else {
   
    res.status(201).json({
      id: 1,
      title:  req.body.title,
      description: req.body.description,
      status: 'to do',
      created_at: '24/08/2020',
      updated_at: '24/08/2020'
    });
  }
  });
```

Volvemos a  comprobar nuestro código con el comando `npm run test`

```bash
Task tests
    create a task
      √ should return a task created (387ms)
      √ should return an error if title is empty (89ms)
      √ should return an error if description is empty

  3 passing (1s)
```

Todas las pruebas pasan.

### Refactorización

Una vez que nuestra primera prueba no ha fallado en ningún caso. Lo que debemos hacer es refactorizar el código, esto implica eliminar código duplicado que nos haya quedado, implementar las funcionalidades reales que debemos tener en cuenta, como persistir los datos de la tarea que creamos a una base de datos, o a un archivo externo, etc.

### Actualización de la lista de requisitos

Ahora es momento de actualizar nuestra lista de requisitos, marcando como completada esta tarea. Debemos repetir todo este proceso para el siguiente requisito.

### Ventajas

A pesar de que al principio puede resultar en una labor muy tediosa, aplicando esta metodología, TDD, nos proporciona un valor añadido a nuestro desarrollo y podemos minimizar los tiempos de trabajo, así como también, añadir calidad a nuestras aplicaciones.

Evitamos errores inesperados, al disponer de todas nuestras implementaciones cubiertas por pruebas. Como programadores también nos da un mayor nivel de confianza.

Con TDD, el programador se centra en la tarea actual, lo que en muchos casos es, hacer que la prueba pase, es por ello que el objetivo de TDD es ir avanzando paso a paso a medida que el sistema lo requiera.
