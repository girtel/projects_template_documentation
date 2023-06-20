---
# Title, summary, and page position.
linktitle: Plantilla para proyectos
summary: Crea una página para un proyecto.
weight: 1
icon: book
icon_pack: fas

# Page metadata.
title: Plantilla para proyectos
date: '2023-06-19T00:00:00Z'
type: book # Do not modify.
---

Pasos necesarios para instalar Hugo y crear una página de proyecto.

⚠️ Atención: Si usas GitHub Actions, no es necesario que instales Hugo, pero te recomiendo que lo hagas al principio por si quieres ver cómo está quedando la página en tu ordenador.

## Instalar Hugo

```bash
    mkdir ~/hugo
    cd ~/hugo
    curl -L "https://github.com/gohugoio/hugo/releases/download/v0.107.0/hugo_extended_0.107.0_Linux-64bit.tar.gz" --output hugo.tar.gz
    tar -xvzf hugo.tar.gz
    sudo mv hugo /usr/local/bin
```

## Instalar plantilla

Usa la plantilla que puedes descargar desde [este enlace](https://github.com/ARNTM/projects_website). (Solo tendrás acceso a través del enlace si lo has solicitado)

## ¿Cómo se edita la plantilla?

### Inicio

- Logotipos
- Slider
- Texto

### Concepto

En el archivo `content/concept/cta.md` podrás escribir el texto con el concepto del proyecto. Recuerda que también puedes añadir imágenes a través Markdown.

### Personas

- #### Crear grupos de personas

Para crear un grupo de personas ve a `content/people` y en `User Group` añade los que quieras.

- #### Añadir una persona

Ve a `content/authors/`, duplica el contenido de la carpeta `example` y renómbrala de la siguiente forma. Si el nombre de la persona es `John Doe`, el nombre de la carpeta será `jdoe`.

Dentro de la carpeta, edita el archivo `_index.md` con los datos de la persona. El archivo `avatar.jpg` es la foto de la persona.

- #### Datos de la persona

  - `title`: Nombre de la persona
  - `stud`: Bs.C., Ms.C., Ph.D., ...
  - `role`: FPI Researcher, Profesor titular, ...
  - `superuser`: Siempre en `False`.
  - `weight`: Sirve para ordenar a las personas dentro de un grupo.
  - `user_groups`: Grupo del usuario (sólo poner uno).
  - `social`: Datos de contacto del usuario. Correo corporativo + teléfono del grupo.
  - `externalLink`: Destino al hacer click sobre el nombre de la persona. Si no quieres que lleve a ningún sitio pon "#".

### Publicaciones

Si vas a usar GitHub Actions para desplegar la página sobre el servidor, simplemente tendrás que añadir la información del articulo en el archivo `publication/publication.bib` y el resto se hará automáticamente.

En caso de que no uses GitHub Actions, tendrás que editar el archivo `publication/publication.bib` y a continuación ejecutar el script `academic import --bibtex publications/publications.bib`. [Descarga](#). para generar los archivos `.md` de cada publicación.

### Posts

En la carpeta `content/news/` puedes añadir los posts que quieras. Para ello, duplica el contenido de la carpeta `example` y renómbrala de la siguiente forma. Si el nombre del post es `My Post`, el nombre de la carpeta será `my-post`.

Dentro de la carpeta, edita el archivo `_index.md` con los datos del post. El archivo `featured.jpg` es la foto del post.

Para publicar el post el parámetro `draft` tendrá que estar en `False`.

### Contacto

Para editar la página de contacto abre `content/contact/contact.md` al final de este archivo. En `Example` tendrás que poner en nombre de la/las personas encargadas del proyecto junto a su correo electrónico.