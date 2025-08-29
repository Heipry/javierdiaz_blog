---
title: 'Subir Proyectos a GitHub: Guía Práctica'
description: 'Guía sobre cómo subir un proyecto local a GitHub, presentando dos metodologías principales'
pubDate: '12 Apr 2025'
heroImage: '../../assets/blog-github.jpg'
---
## Subir un Proyecto Local a GitHub

Este documento resume los métodos y pasos clave para integrar un proyecto local existente en GitHub, utilizando tanto la interfaz de GitHub Desktop como la línea de comandos, según la documentación proporcionada.

## Conceptos Clave

Abordaremos dos métodos principales para subir un proyecto local a GitHub:

- **Uso de GitHub Desktop**: Un enfoque más visual y guiado para quienes prefieren una interfaz gráfica.  
- **Uso de la Línea de Comandos (CLI)**: Un método más tradicional y potente para usuarios familiarizados con Git.  

Ambos métodos requieren la creación de un repositorio en GitHub para alojar el proyecto y la configuración adecuada para vincular el repositorio local con el remoto.  

---

## 1. Agregar un Proyecto Existente a GitHub Usando GitHub Desktop

Este método se centra en la facilidad de uso a través de la aplicación GitHub Desktop.

### Pasos Clave

#### Eliminar Remotos Existentes (si aplica)
Si el repositorio local ya tiene configurado un remoto Git (por ejemplo, de otro servidor), es recomendable eliminarlo antes de vincularlo a GitHub. Esto se hace desde la línea de comandos:

```bash
git remote -v
git remote remove origin
```

Esto asegura una conexión limpia con el nuevo repositorio de GitHub.

#### Agregar el Repositorio a GitHub Desktop

1. Abrir GitHub Desktop y "agregar el repositorio" a la aplicación.
2. En la barra del repositorio, hacer clic en **Publicar repositorio**.

#### Configurar la Publicación del Repositorio

En la ventana "Publicar repositorio" se deben especificar los detalles:

* **Nombre**: se puede usar el predeterminado o escribir uno nuevo.
* **Descripción (Opcional)**: añadir una breve descripción del proyecto.
* **Visibilidad (Público/Privado)**: por defecto es privado si tienes una cuenta pro. Para hacerlo público, desmarcar la opción "Mantener este código privado". Si tu cuenta es free no tendrás opción.
* **Organización (Opcional)**: si se desea publicar en una organización, se selecciona en el menú desplegable. De lo contrario, dejar en "Ninguno".

Finalmente, hacer clic en **Publicar repositorio**.

---

## 2. Subir un Proyecto Local a GitHub Desde la Línea de Comandos

Este método es preferido por muchos desarrolladores por su control y flexibilidad.

### Pasos Clave

#### Crear un Nuevo Repositorio en GitHub (Web)

1. Acceder a <a href="https://github.com" target="_blank" rel="noopener noreferrer">github.com</a> y crear un nuevo repositorio.
2. Asignar un nombre y una descripción.
3. Elegir si será público o privado.

**Importante**: dejar sin marcar la opción de crear README.

Finalmente, hacer clic en **Crear repositorio**.

#### Inicializar y Configurar el Repositorio Local (Terminal)

Desde la carpeta del proyecto local:

```bash
git init
git add .
git commit -m "first commit"
```

#### Vincular el Repositorio Local con el Remoto

```bash
git remote add origin https://github.com/NOMBRE_USUARIO/NOMBRE_PROYECTO.git
```

> Reemplazar `NOMBRE_USUARIO` y `NOMBRE_PROYECTO` por los correctos.

#### Sincronizar y Subir el Proyecto

```bash
git pull origin main
git push -u origin main
```

#### Manejo de Conflictos: *fatal: refusing to merge unrelated histories*

Si el remoto ya tiene commits y el local también, puede aparecer este error. Pasa mucho si finalmente no desmarcaste la opción de crear README.

**Solución**:

```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

Esto permite fusionar ambos historiales.

---

## Conclusión

Tenemos dos métodos comunes de subir proyectos locales a GitHub.

* **GitHub Desktop** ofrece una experiencia más visual y simplificada.
* **La línea de comandos** brinda un control más granular.

Ambos métodos son efectivos para lograr el mismo objetivo: alojar un proyecto local en la plataforma de GitHub.

Solo debes entender los pasos de inicialización, commit y vinculación con el remoto, así como las soluciones para posibles conflictos de historial.

Te dejo un video con esta misma información:

<video width="100%" controls>
  <source src="/assets/uso-github.mp4" type="video/mp4" />
  Tu navegador no soporta la etiqueta <code>video</code>.
</video>
