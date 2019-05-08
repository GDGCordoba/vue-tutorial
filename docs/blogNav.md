# Blog navigation

Creado nuestro layout básico, el siguiente paso será crear un componente que nos permite controlar la navegación a través de nuestro blog. Esta navegación se situará en la parte superior de nuestro blog (Header).

Por defecto mostrará siempre el título del blog, y secciones en el caso de que las haya (fuera del propósito del tutorial). Así mismo, cuando entremos dentro de un artículo, veremos un botón que nos permitirá volver al listado de entradas del blog.

Para crear nuestra navegación, lo primero que tendrás que hacer es crear el fichero `src/components/BlogNav.vue`. Dentro del mismo deberás copiar el siguiente código:

```javascript
<template>
  <nav class="nav">
    <h1 class="nav__title">
      {{ title }}
    </h1>

    <transition-group tag="menu" class="nav__menu" v-if="">
      <li class="nav__item" @click="navBack">
        <i class="nav__item--icon"></i>
        <span class="nav__item--label">
          Exit reading mode
        </span>
      </li>
    </transition-group>
  </nav>
</template>

<script>
export default {
  name: 'blog-nav',
  props: {
    title: String
  },
  computed: {
  },
  methods: {
    navBack() {
      this.$router.push('/');
    }
  }
}
</script>
```

Como hicimos con el layout, vamos a pasar a explicar todas las partes que aparecen en el código:

- `<template>...</template>` - El contenido de esta etiqueta contiene elementos HTML. Sin embargo, existen varios elementos que se diferencia de un código HTML normal y que nos permite conectarlo con nuestra lógica disponible en Vue.

El primero que aparece se encuentra entre dos grupos de llaves `{{ title }}`. Todo lo que se encuentre entre los dos grupos de llaves nos permite ejecutar código Javascript. El uso habitual de esta notación es representar los datos que aparecen en `props`, `data` o `computed` dentro de la lógica Javascript de nuestro fichero Vue.

El siguiente elemento diferente es el que aparece como `@click="navBack"`. Como habrás adivinado, todos los atributos que vayan precedidos por `@` nos permiten indicar eventos en nuestros elementos que aparezcan en el componente. En este caso capturamos el evento `click` que realizamos sobre el botón que nos permitirá volver al listado desde una entrada concreta y ejecutamos la función `navBack` que aparece en `methods`.

- `<script>...</script>`- El contenido de esta etiqueta contiene la lógica Javascript. A diferencia del Layout, en este caso aparecen sí aparecen algunos elementos dentro de las etiquetas básicas:

  - `props` - Aquí aparece nuestra primera propiedad `title`. Como puedes observar, además del nombre de la misma indicamos el tipo de dato, que será un string/cadena en este caso.
  - `methods`- Aquí encontramos nuestra primera función `navBack`. Como su nombre indica, nos permitirá navegar hacia atrás, al listado en este caso.

  `$router` es un módulo dentro de Vue que nos permite movernos a las diferentes vistas de nuestra aplicación. Aunque aún no hemos visto el sistema de rutas de nuestra aplicación, el listado de entradas/posts estará disponible desde la raíz de nuestra web `/`, para que así sea la primera página que ven nuestros usuarios. De esta manera, la línea `this.$router.push('/')` nos permite redirigir a nuestros usuarios de nuevo al listado desde el interior de una entrada/post.

## Integración con nuestro layout

Una vez creado el componente que representará la cabecera de nuestra aplicación, el siguiente paso será usarlo. Para ello, vamos a integrarlo dentro del componente Layout que creamos en la anterior sección.

Lo primero que tenemos que hacer es importar nuestro componente de navegación `BlogNav` dentro del componente `Layout`. Para ello, tan sólo tendrás que añadir la siguiente línea justo a continuación de la etiqueta `<script>` de tu fichero `src/layout/index.vue`:

```javascript
...
<script>
import BlogNav from '../components/BlogNav'
...
```

A continuación, si revisas de nuevo el código verás que la propiedad `components` del mismo nos permite incluir componentes que vamos a usar dentro de nuestro Layout. Para hacerlo, vamos a incluir la siguiente línea dentro de esta propiedad:

```javascript
...
components: {
  BlogNav
},
...
```

Hecho esto, el último paso consistirá en añadir nuestro componente en la plantilla `<template>` del Layout. Para ello, añadimos el siguiente código dentro del mismo:

```javascript
// Vista
<template>
  <main class="blog">
    <blog-nav/>
  </main>
</template>

...
```
