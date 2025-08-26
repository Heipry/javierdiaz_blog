---
title: 'Acordeón en HTML: Guía para usar Details y Summary'
description: 'Como fabricar un elemento de Acordeón mediante las etiquetas html Details y Summary'
pubDate: 'Aug 26 2025'
heroImage: '../../assets/blog-summary.jpg'
---
La etiqueta **details** es uno de los tesoros escondidos de HTML que permite crear elementos interactivos sin necesidad de escribir una sola línea de JavaScript. ¿Alguna vez has necesitado implementar un acordeón para organizar contenido extenso en tu sitio web?

Este elemento nativo de HTML, junto con la etiqueta **summary**, ofrece una solución elegante y ligera para desarrolladores web. Además, estos componentes nativos son completamente funcionales por defecto, compatibles con todos los navegadores modernos y representan una tendencia creciente en el desarrollo web emergente. A lo largo de esta guía, aprenderás a crear, personalizar y optimizar acordeones utilizando CSS sin javascript, mejorando tanto la experiencia de usuario como el rendimiento de tu sitio.

## ¿Qué es un acordeón en HTML y para qué sirve?

Un acordeón en HTML es un componente de interfaz de usuario que permite mostrar y ocultar secciones de contenido, funcionando de manera similar al instrumento musical: al hacer clic en un encabezado, se expande una sección mientras otras pueden contraerse. Es una solución elegante para presentar información de forma organizada sin sobrecargar visualmente la página.

### Definición y propósito del acordeón

El acordeón HTML, también conocido como elemento desplegable o colapsable, muestra un texto o icono identificativo que el usuario puede pulsar para desplegar más información que por defecto está oculta. Su propósito fundamental es permitir la presentación de grandes volúmenes de contenido en espacios reducidos.

La implementación nativa en HTML se realiza mediante las etiquetas `<details>` y `<summary>`, que funcionan como una joya oculta para crear estos componentes sin dependencias externas. La etiqueta `<details>` actúa como un contenedor similar a un `<div>`, con la diferencia de que todo su contenido permanece inicialmente oculto hasta que el usuario decide expandirlo.

Esta estructura proporciona una fantástica forma de añadir contenido en una página sin ocupar demasiado espacio inicial, dejando que el usuario decida si quiere ampliar información rápidamente o continuar leyendo el resto del contenido. El comportamiento predeterminado de los acordeones permite tener varias secciones abiertas simultáneamente, garantizando que los usuarios mantengan el control total sobre qué contenido permanece visible .

### Casos de uso comunes: FAQs, menús, contenido oculto

Los acordeones han demostrado ser particularmente efectivos en ciertos escenarios específicos:

**Preguntas frecuentes (FAQs)**: Quizás el uso más extendido, permite organizar preguntas y respuestas de forma limpia y navegable. Plataformas como Dropbox utilizan este enfoque para que los usuarios naveguen por las preguntas y solo abran aquellas que les interesan. Un ejemplo claro es el FAQ  de [Github](https://github.com/frequently-asked-questions)

**Páginas de precios**: Evitan el desorden y la confusión, especialmente cuando se venden productos o servicios con varios niveles de precios.Puedes ver un ejemplo en [SquareSpace](https://es.squarespace.com/precios#comparison-table)

**Detalles de productos**: Ideales para mostrar características, especificaciones, reseñas y políticas de envío sin saturar la página de producto. Podéis verlo en los productos de [Nike](https://www.nike.com/es/t/court-vision-low-next-nature-zapatillas-sYoDSN1y)

**Formularios extensos**: Particularmente útiles para formularios largos con bloques bien diferenciados.

**Tests autoevaluables**: Permiten a los usuarios evaluar su conocimiento de manera interactiva, mostrando preguntas y respuestas de forma organizada. Yo lo uso para mis [ejercicios de clase](https://heipry.github.io/ejerciciosLinux/)

También son altamente recomendables cuando los usuarios solo necesitan parte del contenido para ejecutar una tarea específica o resolver dudas puntuales, y cuando el espacio está restringido, como ocurre en dispositivos móviles.

En definitiva, los acordeones permiten mostrar gran cantidad de contenido en menor espacio a través de secciones que se despliegan, ayudando a los usuarios a ver solo la información que necesitan.

### Estructura básica del acordeón

Para crear un acordeón básico necesitamos entender cómo funcionan juntas las dos etiquetas principales. El elemento `<details>` actúa como contenedor de todo el widget desplegable, mientras que el elemento `<summary>` define el encabezado visible que funcionará como botón para expandir o contraer el contenido.

La estructura fundamental sigue este patrón:

```
<details>
  <summary>Título o encabezado del acordeón</summary>
  <p>Contenido que estará oculto inicialmente</p>
</details>
```

El elemento `<summary>` debe ser siempre el primer hijo directo dentro de `<details>`. Esta posición es esencial para el correcto funcionamiento del acordeón. Todo el contenido que aparezca después del `<summary>` será parte del área desplegable que se mostrará u ocultará cuando el usuario interactúe con el encabezado.

Por defecto, el navegador muestra una flecha apuntando hacia la derecha cuando el acordeón está cerrado, y cambia a una flecha hacia abajo cuando está abierto. Este indicador visual ayuda a los usuarios a entender la interactividad del elemento.

### Ejemplo simple con HTML puro

Veamos un ejemplo práctico de un acordeón sencillo con tres secciones independientes:

<iframe height="300" style="width: 100%;" scrolling="no" title="Acordeón Details&amp;Summary" src="https://codepen.io/Heipry/embed/preview/WbNYvem?default-tab=html" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Heipry/pen/WbNYvem">
  Acordeón Details&amp;Summary</a> by Javier Diaz (<a href="https://codepen.io/Heipry">@Heipry</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

Este código crea tres secciones independientes donde cada una se puede expandir o contraer sin afectar a las demás. El comportamiento predeterminado permite tener múltiples secciones abiertas simultáneamente.

Para casos como FAQs o listas de información, esta estructura es ideal. Además, podemos incluir cualquier tipo de contenido HTML dentro del área desplegable, no solo texto.

### Cómo mostrar contenido por defecto con el atributo open

En ocasiones, queremos que cierta información esté visible inmediatamente al cargar la página. Para esto, utilizamos el atributo `open` en la etiqueta `<details>`:

```
<details open>
        <summary>¿Qué es HTML?</summary>
        <p>HTML (HyperText Markup Language) es el lenguaje estándar para crear páginas web.</p>
</details>
```

El atributo `open` es un atributo booleano, lo que significa que su mera presencia activa la funcionalidad, sin necesidad de asignarle un valor específico. Cuando está presente, el acordeón se mostrará expandido inicialmente, pero los usuarios podrán cerrarlo si lo desean.

Este comportamiento es particularmente útil para:

- Destacar información crítica que no debe pasarse por alto
- Mostrar la primera pregunta de un FAQ para indicar que hay contenido expandible
- Proporcionar instrucciones iniciales antes de que el usuario comience a interactuar

También podemos alternar dinámicamente el estado, pero para esto ya necesitaríamos JavaScript y el método `toggleAttribute()` o usar una etiqueta "experimental". Para nuestro caso vamos a descartar JavaScript y vamos a hablar del atributo `name`.

### Uso del atributo name para exclusividad

Desde septiembre de 2024, podemos implementar acordeones exclusivos de manera nativa sin escribir JavaScript. La técnica consiste simplemente en añadir el atributo `name` con el mismo valor a todos los elementos `<details>` que queremos agrupar:

<iframe height="300" style="width: 100%;" scrolling="no" title="Acordeón Details&amp;Summary con atributo name" src="https://codepen.io/Heipry/embed/preview/WbQKoRj?default-tab=html" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Heipry/pen/WbQKoRj">
  Acordeón Details&amp;Summary con atributo name</a> by Javier Diaz (<a href="https://codepen.io/Heipry">@Heipry</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

Este comportamiento es similar al de los elementos `<input type="radio">`, donde solo uno puede estar activo a la vez. Cuando utilizamos el mismo valor en el atributo `name`, los elementos `<details>` forman un grupo semántico que funciona como un acordeón exclusivo.

Lo interesante es que los elementos no necesitan ser hermanos directos en el DOM. Pueden estar dispersos por todo el documento y seguirán funcionando como grupo exclusivo gracias al atributo `name`.

⚠️ **Aviso importante**: Esta funcionalidad aún es **experimental** y no cuenta con un soporte completo en todos los navegadores. Antes de usarla en producción conviene revisar su compatibilidad en [Can I Use](https://caniuse.com/?search=details%20name).
Por ahora, lo más recomendable es **evitarla en proyectos reales** o tener preparada una solución alternativa (por ejemplo, el clásico acordeón con `<details>` sin `name`, o un fallback con JavaScript).

## Personalización visual con CSS

Una vez dominada la estructura básica de las etiquetas `<details>` y `<summary>`, el siguiente paso es personalizar su apariencia. El estilo predeterminado es bastante simple, pero con CSS podemos transformar estos elementos en componentes visualmente atractivos.

### Estilizar el contenedor

El elemento `<details>` acepta propiedades CSS como cualquier otro elemento de bloque. Podemos modificar su apariencia general aplicando estilos básicos:

```
details {
  background-color: #f7f7f7;
  border: 1px solid #ccc;
  border-radius: 0.25rem;
  margin-bottom: 1rem;
  text-align: center;
}
```

Además, podemos usar el selector de atributo para aplicar estilos específicos cuando el acordeón está abierto:

```
details[open] {
border-left: 3px solid #3498db;
}
```

### Cambiar la flecha con ::marker

Por defecto, los navegadores muestran una flecha o triángulo que indica el estado del acordeón. Podemos personalizar este indicador con el pseudo-elemento `::marker`:

```
summary::marker {
color: red;
font-size: 1.5rem;
}
```

Para elementos cerrados y abiertos podemos definir diferentes estilos:

```
/* Flecha en contenido desplegado */
details[open] summary::marker {
content: "↕ ";
}
```

### Usar ::before para íconos personalizados

El pseudo-elemento `::marker` tiene limitaciones de estilo. Una alternativa más flexible es ocultarlo y usar `::before`:

```
summary::-webkit-details-marker {
display: none;
}
summary::before {
content: "+";
margin-right: 10px;
}
details[open] summary::before {
content: "-";
}
```

Este enfoque permite mayor control sobre la apariencia y posición del indicador.


## Resumen

Los elementos `<details>` y `<summary>` representan una solución nativa extraordinaria para crear acordeones en HTML sin depender de librerías externas. Estos componentes ofrecen numerosas ventajas para desarrolladores y usuarios por igual: ocupan menos espacio visual, mejoran la navegación y hacen que el contenido sea más accesible para todos.

La personalización mediante CSS transforma estos elementos simples en componentes visualmente atractivos. Además, el soporte inminente del atributo `name` permite implementar comportamientos avanzados como el acordeón exclusivo simplificando aún más el uso sin necesidad de escribir código adicional.

Durante tu próximo proyecto, considera implementar estos elementos nativos antes de recurrir a soluciones más complejas. La simplicidad y elegancia de esta aproximación podría sorprenderte gratamente, tanto por su facilidad de implementación como por los beneficios que aporta a la experiencia del usuario final.