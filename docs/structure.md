# Estructura

El comando que ejecutamos antes nos ha creado un directorio con toda la estructura de nuestra aplicación en VueJS. En la carpeta `src` podemos encontrar todo el código de nuestra aplicación, contando con la siguiente estructura:

- *assets* — Contendrá las imágenes, videos, sonidos, etc que formarán parte de nuestro blog.
- *components* — Todos los componentes que se reutilizarán en las vistas de nuestra web, así como las vistas propiamente dichas.
- *router* — Contendrá todas las rutas que forman nuestro blog, es decir, todos los puntos de acceso a nuestra web a través de las URLs.

Aunque lo entenderás a medida que avancemos en el tutorial, cabe mencionar que todo en VueJS es un componente, incluidas las vistas. La diferencia entre una vista y un componente, es que el componente será usardo varias veces en las vistas. Por su parte, las vistas serán las que se añadirán dentro de las rutas para ser accesibles a los usuarios. Ahora te parecerá un lío pero lo entenderás cuando nos pongamos a crear código.

Además de las carpetas creadas por defecto dentro de `src`, lo primero que vamos a hacer es crear algunas carpetas más dentro de `src` para mejorar la estructura de nuestra aplicación:

- _layout_ - Contendrá la estructura básica de nuestra web, incluyendo cabeceras, menús, footer, etc.
- _resources_ - Contendrá funciones que nos permitirán acceder a todos los recursos del backend.
- _sass_ - A pesar de poder incluir los estilos CSS en los propios componentes de Vue, en esta ocasión vamos a incorporarlos por separado para simplificar los ficheros.
