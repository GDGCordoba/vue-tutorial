# Arquitectura de la aplicación

A muy alto nivel, las aplicaciones webs siempre van a tener dos partes diferenciadas, los llamados Backend y Frontend. En este tutorial te vamos a ahorrar la parte Backend para que así nos podamos centrar en aprender VueJS. De todas formas, te podemos proporcionar el código para acceder al mismo si eres curios@ (y esperamos que lo seas :P).

Como te dijimos arriba, VueJS es un framework orientado a componentes. Para tratar de encontrar nuestros componentes, vamos a tratar de analizar los comportamientos que vamos a tener interactuando con nuestra app, diferenciando entre usuarios logueados y no logueados.

- Usuarios no logueados
  - Cuando entremos a la app, veremos un listado con las entradas más recientes y botones para loguearnos y registrarnos.
  - Al pulsar en cualquier entrada, vemos el detalle de las mismas con los comentarios de otros usuarios y entradas relacionadas.
- Usuarios logueados
  - Cuando entremos, veremos un listado con las entradas más recientes y botones para crear nuevas entradas.
  - Al pulsar en cualquier entrada, vemos el detalle de las mismas con los comentarios de otros usuarios y entradas relacionadas. En este caso veremos además botones para añadir comentarios y editar la entrada si es nuestra.

De estas interacciones se pueden sacar los siguientes componentes:

- Listado de entradas (posts)
- Creación/Edición de entradas
- Listado de comentarios (comments)
- Creación/Edición de comentarios

Aunque el login/registro también podrían considerarse como un componente por sí mismo, no vamos a incluirlo en el tutorial para tratar de simplificarlo.

## MVC (Modelo, vista, controlador)

> - ¿En serio?, me prometiste que ibamos a tener poca teoría y todavía no he visto código :(
> - Tranquil@, esta va a ser la última sección con teoría pero te aseguramos que lo vas a agradecer

Todos los desarrollador@s tratamos de seguir unas buenas prácticas de desarrollo, para lo que nos apoyamos en una serie de patrones de diseño. Aquí no queremos ser menos, así que vamos a enseñarte uno de los más importantes, el MVC. Este patrón permite separar los datos de su representación y de su comunicación con otros componentes, haciendo una división lógica en tres partes:

- Modelo - Es la representación de la información con el cual opera el componente.
- Vista - La Vista: Presenta el 'modelo' (información y lógica de negocio) en un formato adecuado para interactuar.
- Controlador - Responde a eventos e invoca peticiones al 'modelo' cuando se hace alguna solicitud sobre la información.

De momento lo dejamos aquí pero cuando crees tu primer componente, conectaremos estos conceptos con el mismo para que lo veas más claro.
