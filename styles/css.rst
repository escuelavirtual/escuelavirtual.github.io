HTML & CSS Style Guide
==============

Separe las palabras de los nombres de ID y Clases con un guion (-)

No concatenar palabras y abreviaturas en los selectores con ningún
carácter que no sean guiones, para mejorar la comprensión y la capacidad
de escaneo.

.. code:: css

   /* Not recommended: does not separate the words “demo” and “image” */
   .demoimage {}

   /* Not recommended: uses underscore instead of hyphen */
   .error_status {}

.. code:: css

   /* Recommended */
   #video-id {}
   .ads-sample {}

Para más detalles, consulte esta
`guía <https://google.github.io/styleguide/htmlcssguide.html>`__
