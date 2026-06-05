Investigación Técnica

1. Métodos HTTP Semánticos

Los métodos HTTP permiten la comunicación entre un cliente y un servidor.

GET se utiliza para consultar información sin modificar los datos.

POST se utiliza para enviar información y crear nuevos registros.

PUT sirve para actualizar información que ya existe.

DELETE se utiliza para eliminar información o registros del sistema.

2. Estructura JSON

JSON significa JavaScript Object Notation. Es un formato utilizado para intercambiar datos entre aplicaciones.

Actualmente es uno de los formatos más utilizados porque es fácil de leer, fácil de escribir y ocupa menos espacio que XML. Además, es compatible con la mayoría de los lenguajes de programación.

3. Códigos de Error HTTP

Los errores de la familia 400 son errores causados por el cliente.

Los errores de la familia 500 son errores causados por el servidor.

400 Bad Request: la solicitud contiene datos incorrectos o incompletos.

404 Not Found: el recurso solicitado no existe o no fue encontrado.

503 Service Unavailable: el servidor no está disponible temporalmente debido a mantenimiento o fallas.

4. Especificación OpenAPI (Swagger)

OpenAPI, también conocida como Swagger, es una herramienta utilizada para documentar APIs.

Su objetivo principal es describir cómo funciona una API, qué información recibe y qué respuestas devuelve. Esto facilita el trabajo de los equipos de desarrollo y mejora la comunicación entre ellos.

5. Contratos de Interfaz (Código)

Una Interface es una estructura de programación que define métodos que deben implementarse en una clase.

Se considera un contrato porque establece reglas que deben cumplirse entre diferentes componentes del sistema. Gracias a esto, las partes del software pueden comunicarse de manera ordenada sin depender de la implementación interna.

6. Manejo de Excepciones y Resiliencia

Un Stacktrace es el detalle de un error que genera una aplicación cuando ocurre una excepción.

No debe mostrarse directamente al usuario porque puede exponer información sensible del sistema. Lo correcto es registrar el error para los desarrolladores y mostrar un mensaje sencillo que indique que ocurrió un problema.

Análisis del Caso de Estudio

El escenario que más se parece a nuestro proyecto es el Cajero Web o Distribuido. Esto se debe a que nuestro sistema de micropréstamos utiliza varios componentes que trabajan juntos, como el Frontend, el Backend API y la Base de Datos.

Además, nuestro proyecto contempla la comunicación con servicios externos, como el Buró de Crédito y los servicios de notificaciones. Esta forma de trabajo es muy similar al ejemplo del cajero distribuido, donde diferentes sistemas se comunican mediante solicitudes y respuestas para completar una operación.
