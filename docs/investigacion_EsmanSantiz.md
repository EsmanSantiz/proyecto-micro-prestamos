1.0 Fase 1 Investigación Técnica

1.1 Métodos HTTP Semánticos

Para iniciar esta investigación técnica, explicaré los pilares de la arquitectura de transferencia de estado representacional o REST, centrándome específicamente en sus verbos de comunicación. Estos métodos son las acciones estandarizadas que nos permiten interactuar con los recursos de un servidor de manera organizada. A continuación, detallo el propósito de los cuatro métodos principales utilizados en el desarrollo web.

GET: Lo utilizo exclusivamente para solicitar o leer información de un servidor sin modificar su estado interno, tal como ocurre cuando consultamos el saldo de una cuenta bancaria.

POST: Su propósito principal es enviar datos al servidor con la firme intención de crear un recurso completamente nuevo, por ejemplo, al enviar la información de un formulario para registrar a un nuevo cliente.

PUT: Lo aplico para actualizar un recurso existente en su totalidad o para crearlo si este no existe bajo una ruta específica. Básicamente, toma un objeto nuevo y reemplaza por completo la información que residía anteriormente en el servidor.

DELETE: Como su traducción lo indica, empleo este método para solicitar la eliminación definitiva de un recurso específico en la base de datos de nuestro sistema.

1.2 Estructura JSON

Para continuar con la descripción de las tecnologías de intercambio de información, abordaré el formato que elegí para estructurar los datos de nuestro sistema. En el desarrollo moderno, comprender la organización de los mensajes que viajan por la red es vital para garantizar la rapidez de las aplicaciones. A continuación, detallo el significado de este estándar y los motivos técnicos de su dominio en la industria por encima de las alternativas del pasado.

Las siglas corresponden a la Notación de Objetos de JavaScript. Se trata de un formato de texto plano completamente independiente del lenguaje de programación, el cual utilicó para almacenar y transportar información mediante colecciones sencillas de atributos y valores de una manera muy limpia.

Su consolidación como el estándar de la industria frente al Lenguaje de Marcado Extensible, denominado comúnmente XML, se debe principalmente a su ligereza técnica. Al eliminar las etiquetas redundantes de apertura y cierre, reduce drásticamente el tamaño de los mensajes, lo que optimiza el consumo de ancho de banda. Asimismo, su estructura se mapea de forma directa a los objetos nativos de los lenguajes de programación modernos, evitando el uso de analizadores complejos y acelerando el tiempo de procesamiento en el servidor.

1.3 Códigos de Error HTTP

Para garantizar que nuestra aplicación sea robusta y fácil de depurar, comprendí que necesitamos un lenguaje común entre la interfaz y el servidor cuando las peticiones fallan. Por ello, investigué cómo se agrupan estas respuestas numéricas. A continuación, explico las dos familias principales de errores y las diferencias exactas entre los tres códigos más críticos para nuestro desarrollo.

Familia de errores del cliente: Corresponde a la serie de códigos que inician con el número cuatrocientos. Indican que el problema se originó en el lado del usuario o en el Frontend, ya sea por enviar datos mal estructurados o solicitar información inexistente.

Familia de errores del servidor: Corresponde a la serie de códigos que inician con el número quinientos. Señalan que la solicitud del cliente era perfectamente válida, pero el Backend falló al intentar procesarla debido a un error de código interno o a la caída temporal del sistema.

Diferencias específicas de los códigos solicitados:

Error 400 conocido como Bad Request: Ocurre cuando enviamos desde la pantalla una petición mal formada o con datos que no cumplen las reglas del servidor, como intentar enviar texto en un campo diseñado exclusivamente para números.

Error 404 conocido como Not Found: Sucede cuando el cliente intenta acceder a un recurso, ruta o enlace que simplemente no existe o fue eliminado de nuestra base de datos.

Error 503 conocido como Service Unavailable: Representa una falla del servidor que nos advierte que el sistema está temporalmente fuera de línea y no puede recibir peticiones en ese momento exacto, generalmente por mantenimiento programado o sobrecarga técnica.

1.4 Especificación OpenAPI o Swagger

Para conectar adecuadamente la pantalla de nuestro cajero con el servidor, comprendí que necesitamos documentar nuestras rutas de comunicación de forma estandarizada. Por esta razón, analicé la Especificación OpenAPI, conocida popularmente por su nombre original Swagger. A continuación, explico qué es esta tecnología y por qué resulta indispensable al momento de entregar los planos de nuestro sistema al resto del equipo.

Concepto fundamental: Se trata de un formato de descripción estándar e independiente del lenguaje de programación que nos permite documentar, diseñar y consumir interfaces de red. Funciona como un contrato digital legible tanto para nosotros los humanos como para las computadoras, detallando de manera exacta qué rutas existen, qué datos se requieren enviar y qué respuestas numéricas devolverá el sistema.

Objetivo principal: Su mayor utilidad al entregar los planos de software a un equipo de desarrollo radica en eliminar por completo la ambigüedad. Al generar una página visual e interactiva basada en este documento, permite que los desarrolladores frontales entiendan cómo usar los servicios del servidor y prueben las peticiones en tiempo real sin necesidad de leer nuestro código fuente interno, acelerando enormemente el trabajo en paralelo.

1.5 Contratos de Interfaz

Para asegurar el correcto desacoplamiento en nuestro sistema, investigué el papel que juegan las interfaces dentro del paradigma de la programación orientada a objetos. A continuación, defino este concepto y explico la razón por la cual se considera un acuerdo inmutable entre la capa que maneja las reglas del negocio y el acceso a los datos almacenados.

Definición en la programación orientada a objetos: Una interfaz es una estructura puramente abstracta que define un conjunto de métodos, es decir, las firmas de las funciones con sus respectivos componentes y tipos de retorno, pero sin incluir ninguna implementación ni código lógico dentro de ellos. Básicamente, funciona como un mapa que le indica a las clases qué acciones deben realizar obligatoriamente, pero les deja a ellas la libertad de decidir cómo ejecutar esa tarea internamente.

El concepto de contrato inmutable: Se dice que actúa como un pacto que no se puede cambiar porque, una vez que la interfaz queda establecida y es adoptada por los repositorios de datos, cualquier modificación en su estructura obligaría a romper el sistema de forma inmediata. Si la lógica de negocio define que necesita un método específico para guardar la información de una cuenta, la clase que conecta directamente con la base de datos está forzada por el compilador a implementar exactamente esa función. Esto nos garantiza una estabilidad absoluta en la arquitectura, permitiéndonos cambiar el motor de la base de datos en el futuro sin alterar una sola línea de la lógica comercial del cajero.

1.6 Manejo de Excepciones y Resiliencia

Para finalizar con la fase de investigación conceptual, consideré de vital importancia abordar la forma en que nuestro sistema reacciona ante fallas críticas, específicamente cuando perdemos conexión con la infraestructura de persistencia. A continuación, explico qué significa el rastro de ejecución y los motivos de seguridad por los cuales esta información jamás debe quedar expuesta ante el usuario final.

Concepto de rastro de ejecución: Comúnmente conocido por su término en inglés Stacktrace, se trata de un reporte detallado en texto que la consola de nuestro entorno de desarrollo genera automáticamente cuando ocurre un error no controlado en el servidor. Esta lista técnica nos muestra la secuencia exacta de las funciones, los métodos y los archivos de código que el sistema estaba procesando en el momento preciso del fallo, sirviendo como una herramienta de diagnóstico exclusiva para el equipo de desarrollo.

Razones para bloquear su exposición al cliente: Jamás debemos permitir que este bloque de errores crudo llegue a la pantalla del usuario cuando la base de datos colapsa por dos motivos fundamentales. El primero es cuidar la experiencia del cliente, ya que mostrar un texto incomprensible y alarmante en la pantalla del cajero genera confusión y desconfianza operativa. El segundo motivo, y el más crítico a nivel de ciberseguridad, radica en que este reporte expone la estructura íntima de nuestro proyecto al revelar las rutas de nuestras carpetas, las tecnologías que usamos y la arquitectura interna de nuestro código, entregando a posibles atacantes un mapa sumamente detallado para vulnerar nuestra red.


