---
title: 'Guía de Estilo de Markdown'
description: 'Aquí tienes un ejemplo de sintaxis básica de Markdown que se puede usar al escribir contenido Markdown .'
pubDate: '17 Jun 2025'
heroImage: '../../assets/blog-placeholder-1.jpg'
---

Aquí tienes un ejemplo de sintaxis básica de Markdown que se puede usar al escribir contenido Markdown. Está traducido directamente del ejemplo que suele dar Astro para empezar a escribir sus posts.

## Encabezados

Los siguientes elementos HTML `<h1>`—`<h6>` representan seis niveles de encabezados de sección. `<h1>` es el nivel de sección más alto, mientras que `<h6>` es el más bajo.

# \# H1 

## \## H2

### \### H3

#### \#### H4

##### \##### H5

###### \###### H6

## Párrafo
Lorem ipsum dolor sit amet consectetur adipisicing elit. Ab quo tempore a neque. Dignissimos sequi dolore unde dolor, molestiae aut provident distinctio nostrum, non dicta consequatur ab dolores asperiores. Quo!

Itatur? Quiatae cullecum rem ent aut odis in re eossequodi nonsequ idebis ne sapicia is sinveli squiatum, core et que aut hariosam ex eat.

## Imágenes

### Sintaxis

```markdown
![Texto alternativo](./ruta/completa/o/relativa/de/la/imagen)
````

### Resultado

![blog placeholder](../../assets/blog-placeholder-about.jpg)

## Citas en bloque

El elemento blockquote representa contenido citado de otra fuente, opcionalmente con una cita que debe estar dentro de un elemento `footer` o `cite`, y opcionalmente con cambios en línea como anotaciones y abreviaciones.

### Cita en bloque sin atribución

#### Sintaxis

```markdown
> Tiam, ad mint andaepu dandae nostion secatur sequo quae.  
> **Nota** que puedes usar _sintaxis Markdown_ dentro de una cita en bloque.
```

#### Resultado

> Tiam, ad mint andaepu dandae nostion secatur sequo quae.
> **Nota** que puedes usar *sintaxis Markdown* dentro de una cita en bloque.

### Cita en bloque con atribución

#### Sintaxis

```markdown
> No comuniques compartiendo memoria, comparte memoria comunicando.<br>
> — <cite>Rob Pike[^1]</cite>
[^1]: La cita anterior está extraída de la charla de Rob Pike [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) durante Gopherfest, 18 de noviembre de 2015.
```

#### Resultado

> No comuniques compartiendo memoria, comparte memoria comunicando.<br>
> — <cite>Rob Pike[^1]</cite>

[^1]: La cita anterior está extraída de la charla de Rob Pike [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) durante Gopherfest, 18 de noviembre de 2015.


Tendrás que mirar al pie de la página para ver la atribución completa
## Tablas

### Sintaxis

```markdown
| Cursiva   | Negrita  | Código  |
| --------- | -------- | ------- |
| _cursiva_ | **negrita** | `código` |
```

### Resultado

| Cursiva   | Negrita     | Código   |
| --------- | ----------- | -------- |
| *cursiva* | **negrita** | `código` |

## Bloques de código

### Sintaxis

Podemos usar 3 acentos graves \`\`\` en una nueva línea, escribir el fragmento y cerrar con 3 acentos graves en otra línea. Para resaltar la sintaxis de un lenguaje específico, escribe el nombre del lenguaje después de los primeros 3 acentos graves, por ejemplo: html, javascript, css, markdown, typescript, txt, bash.

````markdown
```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <title>Ejemplo de Documento HTML5</title>
  </head>
  <body>
    <p>Prueba</p>
  </body>
</html>
```
````

## Tipos de listas

### Lista ordenada

#### Sintaxis

```markdown
1. Primer elemento
2. Segundo elemento
3. Tercer elemento
```

#### Resultado

1. Primer elemento
2. Segundo elemento
3. Tercer elemento

### Lista desordenada

#### Sintaxis

```markdown
- Elemento de la lista
- Otro elemento
- Y otro más
```

#### Resultado

- Elemento de la lista
- Otro elemento
- Y otro más

### Lista anidada

#### Sintaxis

```markdown
- Frutas
  - Manzana
  - Naranja
  - Plátano
- Lácteos
  - Leche
  - Queso
```

#### Resultado

* Frutas
  * Manzana
  * Naranja
  * Plátano
* Lácteos
  * Leche
  * Queso

## Otros elementos — abbr, sub, sup, kbd, mark

### Sintaxis

```markdown
<abbr title="Formato de Intercambio de Gráficos">GIF</abbr> es un formato de imagen de mapa de bits.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Presiona <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>Supr</kbd> para finalizar la sesión.

La mayoría de las <mark>salamanquesas</mark> son nocturnas y cazan insectos, gusanos y otras criaturas pequeñas.
```

### Resultado

<abbr title="Formato de Intercambio de Gráficos">GIF</abbr> es un formato de imagen de mapa de bits.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Presiona <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>Supr</kbd> para finalizar la sesión.

La mayoría de las <mark>salamanquesas</mark> son nocturnas y cazan insectos, gusanos y otras criaturas pequeñas.

