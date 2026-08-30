---
title: 'Guía de estilo para commits en Git'
description: 'Esta guía práctica explica los tipos de commits, convenciones de formato, cuándo usar inglés o español, y ejemplos listos para aplicar en tus proyectos.'
pubDate: 'MAr 16 2025'
heroImage: '../../assets/blog-commits.jpg'
---

Mantener los commits claros y consistentes no es solo estética: ayuda a entender el historial del proyecto y facilita la colaboración. Aquí tienes una guía práctica basada en  <a href="https://www.conventionalcommits.org/en/v1.0.0/" target="_blank" rel="noopener noreferrer">**Conventional Commits**</a>.

---

## 1. Estructura básica

```
<tipo>[alcance]: <mensaje breve>
[opcional: cuerpo del commit]
[opcional: footer]
```

* `tipo` → qué hace el commit (`feat`, `fix`, `style`, etc.)
* `alcance` → opcional, indica la parte del proyecto afectada (`auth`, `cart`, `ui`)
* `mensaje breve` → resumen de máximo \~50 caracteres, imperativo presente

**Ejemplo mínimo:**

```
feat: añadir buscador en la lista de productos
```

**Ejemplo con cuerpo y footer:**

```
refactor(auth): simplifica la lógica de validación de tokens

Se ha extraído la validación de tokens a un helper independiente
y se han añadido comentarios para mayor claridad.

BREAKING CHANGE: se elimina la función `validateOldToken`
```

---

## 2. Tipos de commits

<table class="formato-tabla">
  <thead>
    <tr>
      <th>Tipo</th>
      <th>Cuándo usarlo</th>
      <th>Ejemplo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>feat</strong></td>
      <td>Nueva funcionalidad</td>
      <td><code>feat: soporte login social</code></td>
    </tr>
    <tr>
      <td><strong>fix</strong></td>
      <td>Corrección de bug</td>
      <td><code>fix: corrige cálculo de impuestos</code></td>
    </tr>
    <tr>
      <td><strong>docs</strong></td>
      <td>Documentación</td>
      <td><code>docs: actualizar README con ejemplos API</code></td>
    </tr>
    <tr>
      <td><strong>style</strong></td>
      <td>Formato, limpieza, indentación (sin afectar lógica)</td>
      <td><code>style: aplicar prettier en todos los archivos</code></td>
    </tr>
    <tr>
      <td><strong>refactor</strong></td>
      <td>Cambios internos sin añadir features ni fixes</td>
      <td><code>refactor: extrae función de envío de emails</code></td>
    </tr>
    <tr>
      <td><strong>perf</strong></td>
      <td>Optimización de rendimiento</td>
      <td><code>perf: optimiza consulta SQL de productos</code></td>
    </tr>
    <tr>
      <td><strong>test</strong></td>
      <td>Tests</td>
      <td><code>test: añade pruebas unitarias para Button</code></td>
    </tr>
    <tr>
      <td><strong>chore</strong></td>
      <td>Mantenimiento, configuración, dependencias</td>
      <td><code>chore: actualizar dependencias Node</code></td>
    </tr>
  </tbody>
</table>

💡 Para cambios de **formato o limpieza**, puedes usar tanto  **`style:`** como **`refactor:`**.

---

## 3. Reglas prácticas

### Mensaje breve

* Imperativo presente: “añade”, “corrige”, “actualiza”
* Sin punto final
* \~50 caracteres máximo

**Ejemplo:**

```
fix: corrige error en envío de formularios
```

### Cuerpo del commit

* Explica **por qué**, no solo qué
* Líneas de \~72 caracteres

**Ejemplo:**

```
refactor: separar lógica de validación

Se ha movido validateInput a un helper independiente para
reutilización y tests más claros.
```

### Footer

* Para notas especiales: `BREAKING CHANGE`, referencias a issues

```
BREAKING CHANGE: se elimina método antiguo de autenticación
Closes #123
```

### Alcance (opcional)

* Indica área del proyecto afectada

```
feat(auth): login con Google
fix(cart): total incorrecto al eliminar producto
```

---


## 4. Verbos y tiempo

Para los mensajes de commit, la convención es usar el **imperativo presente**, que indica una acción directa. Esta regla sigue el estándar en inglés (`add`, `fix`, `update`). En español, puedes usar dos formas:

### 1. Infinitivo (interpretado como acción)

Esta es una opción común en la comunidad hispanohablante. El infinitivo se interpreta como una orden o acción a realizar por el commit.

* `feat: añadir soporte para exportar PDF`
* `fix: corregir cálculo de impuestos`

### 2. Imperativo real

Similar a la convención en inglés, puedes usar la forma imperativa directa.

* `feat: agrega soporte para exportar PDF`
* `fix: corrige cálculo de impuestos`

Ambas formas son válidas, pero lo más importante es que mantengas la **consistencia** en todo el proyecto.

### ¿Qué evitar?

Evita siempre el uso de verbos en otros tiempos, ya que rompen la convención de acción directa.

* **Pasado**: `añadí`, `corregí`
* **Gerundio**: `añadiendo`, `corrigiendo`
* **Participio**: `añadido`, `corregido`

---

## 5. Idioma

* **Proyectos internos / equipo que habla español:** puedes usar español en los commits.
  Ejemplo:

  ```
  feat: añadir soporte para exportar PDF
  fix: corregir cálculo de impuestos
  ```
* **Proyectos públicos o colaborativos / open source:** se recomienda **inglés**, porque es el estándar global y facilita contribuciones externas.
  Ejemplo:

  ```
  feat: add PDF export support
  fix: correct tax calculation
  ```
* En general, otra vez lo más importante es **mantener consistencia**: no mezclar español e inglés en el mismo proyecto.

---

## 6. Consejos finales

* Relaciona commits con **issues** (`Closes #n`)
* Divide commits grandes en partes lógicas
* Mantén consistencia en todo el equipo

---

## 7. Cheat sheet descargable

Para que tengas siempre a mano los tipos de commits y ejemplos prácticos, **he preparado un cheat sheet** que puedes <a href="https://gist.github.com/Heipry/ed9b4844e65715b9214d82933f1e13f5" target="_blank" rel="noopener noreferrer">consultar en gist</a> o descargar en PDF:
<iframe src="/assets/commits.pdf" width="100%" height="600px">
  <p>Tu navegador no soporta iframes. Puedes descargar el PDF <a href="/assets/commits.pdf">aquí</a>.</p>
</iframe>

¡Con esta información no volverás a tener dudas al escribir tus mensajes de commit!