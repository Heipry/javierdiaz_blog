---
title: 'Lightbox sin JavaScript (Con un truco de CSS)'
description: 'Veemos un fragmento de código que ofrece la funcionalidad de lightbox para una imagen sin usar JavaScript.'
pubDate: '21 Aug 2025'
heroImage: '../../assets/blog-placeholder-5.jpg'
---

### La Magia de un Lightbox sin JavaScript: Trucos con HTML y CSS

Como desarrollador, siempre me ha fascinado encontrar soluciones elegantes y sencillas para problemas complejos. En la búsqueda de un rendimiento óptimo y una experiencia de usuario fluida, a menudo redescubrimos el poder de las herramientas más fundamentales de la web: HTML y CSS.

Hoy quiero compartir un truco ingenioso que demuestra que a veces, la mejor manera de resolver un problema es con los fundamentos. Te voy a mostrar cómo crear un **lightbox completamente funcional sin una sola línea de JavaScript**.

#### El Truco: Un Checkbox Oculto y el Selector `~`

El secreto de esta técnica reside en combinar dos elementos clave:

1.  Un **`input` de tipo `checkbox`** oculto.
2.  Un **selector de hermanos generales (`~`)** en CSS.

Cuando un usuario hace clic en la miniatura de la imagen, un `label` la envuelve y está asociado al `checkbox`. Esto hace que el `checkbox` cambie de estado, de "no marcado" a "marcado".

En ese momento, nuestra regla de CSS detecta el cambio de estado y hace que el overlay del lightbox se vuelva visible.

```css
input[type="checkbox"]:checked ~ .lightbox-overlay {
  display: flex;
}
```

Esta simple línea de código dice: "Cuando el `checkbox` esté **marcado**, encuentra a su hermano posterior con la clase `.lightbox-overlay` y cámbiale la visualización a `flex`." Al volver a hacer clic en el overlay, el `checkbox` se desmarca y la imagen se oculta de nuevo.

#### El Código y la Demo en Vivo

Puedes ver el código completo y la demo interactiva en este [CodePen](https://codepen.io/jadigar/pen/gbavMEp). He simplificado el HTML y el CSS para que te sea fácil de entender y reutilizar en tus propios proyectos.

**HTML**

```html
<label class="lightbox-trigger">
  <input type="checkbox" id="lightbox-checkbox-1" class="lightbox-checkbox" />
  <img src="https://picsum.photos/600/400" alt="Imagen de ejemplo" class="thumb" />
  <label class="lightbox-overlay" for="lightbox-checkbox-1">
    <img src="https://picsum.photos/600/400" alt="Imagen de ejemplo ampliada" />
  </label>
</label>
```

-----

**CSS**

```css
.lightbox-checkbox {
  display: none;
}

.lightbox-overlay {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.8);
  justify-content: center;
  align-items: center;
  z-index: 999;
  cursor: pointer;
}

.lightbox-overlay img {
  width: auto;
  height: 90vh;
  object-fit: contain;
}

.thumb {
  max-width: 100%;
  cursor: pointer;
}

.lightbox-checkbox:checked ~ .lightbox-overlay {
  display: flex;
}
```

-----

#### Ventajas y Desventajas

Como toda solución, esta técnica tiene sus pros y contras que debemos considerar:

**Ventajas:**

  * **Rendimiento Superior:** Al no depender de JavaScript, no hay scripts que cargar o ejecutar, lo que resulta en una carga de página casi instantánea.
  * **Simplicidad:** El código es mínimo y fácil de entender. Es una solución elegante para proyectos donde no se necesita funcionalidad avanzada.
  * **Compatibilidad:** Funciona en prácticamente cualquier navegador moderno.

**Desventajas:**

  * **Accesibilidad Semántica:** Usar un `checkbox` para algo que no es un formulario puede ser confuso para lectores de pantalla, ya que el elemento no cumple su función semántica original.
  * **Funcionalidad Limitada:** No podemos cerrar el lightbox con la tecla "Esc" ni añadir navegación entre múltiples imágenes sin JavaScript adicional.

Sabiendo esto debo decir que este truco es un excelente recordatorio de que a veces la mejor solución ya está integrada en los estándares de la web. Es una forma de construir de manera inteligente, poniendo el rendimiento primero.