<h1 align="center">Listeners</h1>

En Java, los `Listeners` son interfaces que permiten capturar y manejar eventos, como clics de botones, movimientos del ratón, pulsaciones de teclas, etc. Los Listeners son una parte fundamental del modelo de eventos de Java, especialmente en la programación de interfaces gráficas de usuario (GUI) con AWT (Abstract Window Toolkit) y Swing.

<h2>Modelo de Eventos de Java</h2>

- <b>Fuente de Eventos (Event Source)</b>: Es el objeto que genera el evento. Por ejemplo, un botón que es presionado.
- <b>Evento</b> (`Event Object`): Es un objeto que contiene información sobre el evento. Por ejemplo, un objeto ActionEvent para un clic de botón.
- <b>Listener</b>: Es una interfaz que define uno o más métodos que reciben eventos y los procesan. Por ejemplo, ActionListener para manejar clics de botones.
- <b>Registro del Listener</b>: Es el proceso de asociar un `Listener` con una fuente de eventos para que la fuente pueda notificar al `Listener` cuando ocurra un evento.

