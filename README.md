<h1 align="center">Filters</h1>

En Java, los `Filters` (filtros) son componentes que se utilizan para realizar operaciones comunes en solicitudes y respuestas HTTP antes o después de que se procesen por un servlet. Los filtros se definen en el contexto de aplicaciones web Java (Servlets y JSP) y forman parte del API de Servlets.
Los filtros permiten realizar tareas como:
- La autenticación
- El registro de actividades
- La compresión de datos
- La modificación de solicitudes y respuestas.

<h3>Características de los Filters</h3>

- <b>Intercepción de Solicitudes y Respuestas</b>: Los filtros interceptan las solicitudes HTTP antes de que lleguen a los servlets y las respuestas HTTP antes de que se envíen al cliente.
- <b>Encadenamiento</b>: Varios filtros pueden estar encadenados juntos. Cada filtro puede pasar la solicitud y la respuesta al siguiente filtro en la cadena o al servlet.
- <b>Reutilización de Código</b>: Los filtros permiten la reutilización de código común, como la autenticación, en diferentes servlets sin necesidad de duplicar el código.
- <b>Configuración en</b> `web.xml`: Los filtros se configuran en el archivo `web.xml` de la aplicación web o mediante anotaciones en la clase del filtro.

<h3>Ejemplos de Uso de Filters</h3>

- <b>Autenticación</b>: Verificar si un usuario está autenticado antes de permitirle acceder a ciertos recursos.
- <b>Registro de Actividades</b>: Registrar todas las solicitudes y respuestas para análisis posterior.
- <b>Compresión de Contenido</b>: Comprimir las respuestas HTTP para reducir el tiempo de carga.
- <b>Conversión de Datos</b>: Convertir datos en la solicitud o respuesta, como cambiar el formato de la fecha.

<h1 align="center">ServletRequest, ServletResponse, y FilterChain</h1>
<h2>ServletRequest</h2>

La clase `ServletRequest` es una interfaz que representa la solicitud que un cliente realiza a un servlet. Proporciona varios métodos para acceder a los datos de la solicitud, como parámetros, atributos, y la información del cliente.

<h3>Métodos Comunes:</h3>

- `getParameter(String name)`: Devuelve el valor del parámetro de solicitud especificado.
- `getAttribute(String name)`: Devuelve el atributo de la solicitud con el nombre especificado.
- `getInputStream()`: Devuelve un ServletInputStream para leer los datos binarios de la solicitud.
- `getReader()`: Devuelve un BufferedReader para leer los datos de texto de la solicitud.

En el contexto de un `filter`, se puede utilizar `ServletRequest` para inspeccionar o modificar los datos de la solicitud antes de que se pase al siguiente `filter` o `servlet`.

<h2>ServletResponse</h2>

La clase `ServletResponse` es una interfaz que representa la respuesta que se envía al cliente desde un servlet. Proporciona métodos para configurar la respuesta, como establecer el tipo de contenido y obtener un flujo de salida para escribir los datos de la respuesta.

<h3>Métodos Comunes:</h3>

- `setContentType(String type)`: Establece el tipo MIME de la respuesta.
- `getOutputStream()`: Devuelve un `ServletOutputStream` para escribir datos binarios a la respuesta.
- `getWriter()`: Devuelve un `PrintWriter` para escribir datos de texto a la respuesta.
- `setCharacterEncoding(String charset)`: Establece el conjunto de caracteres de la respuesta.

En un `filter`, se puede utilizar `ServletResponse` para modificar la respuesta antes de enviarla al cliente.

<h2>FilterChain</h2>

La interfaz `FilterChain` representa la cadena de filtros que se ejecutan antes de que una solicitud llegue al servlet y después de que la respuesta salga del servlet. La cadena de filtros es responsable de pasar la solicitud y la respuesta al siguiente filtro en la cadena o, si no hay más filtros, al servlet.

<h3>Método Principal:</h3>

`doFilter(ServletRequest request, ServletResponse response)`: Pasa la solicitud y la respuesta al siguiente filtro en la cadena. Si no hay más filtros, la solicitud se pasa al servlet destino.
