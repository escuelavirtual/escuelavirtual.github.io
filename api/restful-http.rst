Api Endpoints
==============================================

*Esta sección esta sujeta a futuras modificaciones*

Para documentar sus endpoints en este archivo, deben utilizar el siguiente formato:

Code
````

.. code-block:: python
    :caption: Example code.
    
    ..  http:example:: curl wget httpie
       :request: ../optional/rel/path/to/plaintext/request
       :response: ../optional/rel/path/to/plaintext/response

       Raw plaintext HTTP request example, which is
       required only when :request: is not specified.
       
.. note::

   Request and response must be separated with two or more blank lines and
   the first response line must start with string "HTTP/" or "HTTP ".

Result
``````
       
..  http:example:: curl wget httpie
       :request: ../endpoints/001.request.txt
       :response: ../endpoints/001.response.txt

