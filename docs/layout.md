# Layout

El layout contendrá toda la estructura de nuestra aplicación, de manera que sobre ella aparecerán todos los componentes y vistas que crearemos a continuación. Para añadirlo, lo primero que tendrás que hacer será crear el fichero `src/layout/index.vue` con el siguiente contenido:

```javascript
<template>
  <main class="blog">
  </main>
</template>

<script>
export default {
  name: 'layout',
  components: {},
  props: {
  },
  data() {
    return {
    }
  },
  computed: {
  },
  watch: {
  },
  mounted() {
  }
}
</script>
```

Ahora mismo no entenderás nada de lo que aparece, así que vamos a ir explicando cada parte por separado:

- `<template>` - Nos permite escribir el contenido HTML de nuestro componente.
- `<script>` - Nos permite escribir la lógica Javascript ligada a nuestro componente, el cual contiene varias partes a su vez:
  - `name` - Indica el nombre de nuestro componente, que en este caso es `Layout`.
  - `components` - Indica los componentes que formarán parte del layout. En este momento no hemos indicado ninguno pero a medida que añadamos más componentes a nuestro blog, tendremos que añadirlos aquí.
  - `props` - Atributos que se pueden pasar a nuestro componente cuando lo usamos. En este caso no será necesario añadir ninguno de momento pero veremos su uso cuando creemos otros componentes.
  - `data` - Datos usados internamente por el componente. A diferencia de los usados en `props`, estos no se pasan como parámetro al mismo. Al igual que en el anterior, de momento lo dejaremos vacío.
  - `computed` - Se comportan como los campos que aparecen en `data` pero a diferencia de los anteriores, son calculados en función de los datos que usen en tiempo real. Veremos su uso más adelante.
  - `watch` - Nos permite observar el comportamiento de la información y actuar en base a los cambios que observemos sobre ellos.
  - `mounted` - Hook que nos permite añadir la lógica necesaria para controlar el comportamiento del componente cuando entramos en el mismo. Existen más hooks pero para este tutorial nos basta con este.
