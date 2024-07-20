<h1 align="center">Listeners</h1>

En Java, los `Listeners` son interfaces que permiten capturar y manejar eventos, como clics de botones, movimientos del ratón, pulsaciones de teclas, etc. Los Listeners son una parte fundamental del modelo de eventos de Java, especialmente en la programación de interfaces gráficas de usuario (GUI) con AWT (Abstract Window Toolkit) y Swing.

<h2>Modelo de Eventos de Java</h2>

- <b>Fuente de Eventos (Event Source)</b>: Es el objeto que genera el evento. Por ejemplo, un botón que es presionado.
- <b>Evento</b> (`Event Object`): Es un objeto que contiene información sobre el evento. Por ejemplo, un objeto ActionEvent para un clic de botón.
- <b>Listener</b>: Es una interfaz que define uno o más métodos que reciben eventos y los procesan. Por ejemplo, ActionListener para manejar clics de botones.
- <b>Registro del Listener</b>: Es el proceso de asociar un `Listener` con una fuente de eventos para que la fuente pueda notificar al `Listener` cuando ocurra un evento.

<h1 align="center">ServletContextListener, ServletRequestListener, y HttpSessionListener</h1>

En Java, los `ServletContextListener`, `ServletRequestListener`, y `HttpSessionListener` son interfaces de escucha (`listeners`) que permiten a los desarrolladores de aplicaciones web realizar acciones en momentos específicos del ciclo de vida de un servlet, petición o sesión HTTP. Estas interfaces forman parte de la especificación de Java Servlet y se utilizan comúnmente en aplicaciones web para inicializar recursos, realizar limpieza, o gestionar el estado de la aplicación.

<h2>ServletContextListener</h2>

`ServletContextListener` se utiliza para recibir notificaciones sobre los cambios en el contexto del servlet (`ServletContext`). Los eventos relevantes son la creación y destrucción del contexto del servlet, que típicamente corresponden al inicio y apagado de la aplicación web.

<h3>Métodos Clave</h3>

- `contextInitialized`(ServletContextEvent sce): Se llama cuando se <b>inicializa</b> el `ServletContext`. Es el lugar adecuado para configurar recursos compartidos como conexiones a bases de datos, hilos de fondo, etc.
- `contextDestroyed`(ServletContextEvent sce): Se llama cuando se <b>destruye</b> el `ServletContext`. Es el lugar adecuado para liberar recursos compartidos.

<h2>ServletRequestListener</h2>

`ServletRequestListener` se utiliza para recibir notificaciones sobre los cambios en las peticiones (`ServletRequest`). Los eventos relevantes son la creación y destrucción de las peticiones.

<h3>Métodos Clave</h3>

- `requestInitialized`(ServletRequestEvent sre): Se llama cuando se crea una nueva petición.
- `requestDestroyed`(ServletRequestEvent sre): Se llama cuando se destruye una petición.

<h2>HttpSessionListener</h2>

`HttpSessionListener` se utiliza para recibir notificaciones sobre los cambios en las sesiones HTTP (`HttpSession`). Los eventos relevantes son la creación y destrucción de las sesiones.

<Métodos Claveh3></h3>

- `sessionCreated`(HttpSessionEvent se): Se llama cuando se crea una nueva sesión HTTP.
- `sessionDestroyed`(HttpSessionEvent se): Se llama cuando una sesión HTTP se invalida o expira.
