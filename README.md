# Receptáculo Recursivo

Sitio de Juan O. Costa hecho con Jekyll y publicado en GitHub Pages.

## Estructura

- `_config.yml` — título, autor, dirección pública, newsletter y redes.
- `_relatos/` — un archivo HTML por relato; cada uno es su propia página.
- `_posts/` — un archivo HTML por entrada de la bitácora; cada una es su propia página.
- `assets/img/relatos/` y `assets/img/bitacora/` — una ilustración por página (ver más abajo).
- `assets/css/paginas/` — un CSS por página, para darle diseño propio.
- `_data/navegacion.yml` — el menú. `_data/premios.yml` — premios de la página El autor.
- `_layouts/` y `_includes/` — plantillas (cabecera, pie, relato, entrada, suscripción).
- `style.css` — tu diseño original, sin tocar. `assets/css/extra.css` — estilos añadidos.
- `_plantillas/` — modelos para copiar al crear un relato o una entrada. No se publican.

## Direcciones

- Cada relato vive en `/nombre-del-archivo/` (por ejemplo, `_relatos/ronda-nocturna.html` sale en `.../ronda-nocturna/`).
- Cada entrada de la bitácora vive en `/bitacora/nombre/` (por ejemplo, `_posts/2026-10-05-entrada-00.html` sale en `.../bitacora/entrada-00/`).
- Para cambiar una dirección, cambia el nombre del archivo.

## Publicar un relato

1. Copia `_plantillas/relato.html` a `_relatos/` y ponle un nombre sin espacios ni tildes.
2. Completa `title` y `orden` (el lugar que ocupa en el índice) y escribe el texto debajo, un párrafo por etiqueta `<p>`.
3. Sube el archivo a GitHub. En un par de minutos aparece en el índice de la portada, en Relatos y en Archivo.
4. Para una pausa de escena, escribe `<div class="corte" aria-hidden="true"></div>`.
5. También puedes crear el relato como `.md` (Markdown) si te resulta más cómodo escribir sin etiquetas: funciona igual.

Los relatos no muestran fecha, etiquetas ni otros datos: solo el título y el texto.

## Publicar una entrada de la bitácora

Copia `_plantillas/entrada-bitacora.html` a `_posts/` con el nombre `AAAA-MM-DD-nombre.html` (la fecha solo ordena las entradas; no se muestra). Si el texto ya trae su propio encabezado, deja `sin_titulo: true` para que el título no se repita arriba.

## Ilustración propia en cada página

Guarda la imagen con el mismo nombre que el archivo de la página y en la carpeta que corresponde:

- relatos: `assets/img/relatos/ronda-nocturna.png` (también sirve `.jpg`, `.jpeg`, `.webp` o `.svg`)
- bitácora: `assets/img/bitacora/entrada-00.png`

Si la imagen existe, aparece sola arriba del texto; si no existe, no se muestra nada. No hay que tocar ningún HTML.

## Diseño propio en cada página

Cada página tiene un CSS de partida en `assets/css/paginas/nombre.css`, con ejemplos comentados (fondo, tamaño de letra, ancho del texto, alineación del título). Se aplica automáticamente solo a esa página. Para activar una regla, borra las marcas de comentario de su línea.

Para una página totalmente independiente, sin el menú ni el pie del sitio, añade `layout: null` en su encabezado y escribe el HTML completo (con sus etiquetas `<html>`, `<head>` y `<body>`).

## Newsletter

En `_config.yml`, rellena `suscripcion.action` con la URL del formulario de tu servicio (por ejemplo Buttondown), o `suscripcion.enlace` con tu página de suscripción (por ejemplo Substack). El bloque aparece solo cuando hay uno de los dos.

## Redes, premios y tienda

- Redes: descomenta el ejemplo de `redes` en `_config.yml` y pon tus enlaces reales.
- Premios: completa `_data/premios.yml`.
- Tienda: está oculta (`published: false` en `tienda.html`). Cuando haya algo que vender, cámbialo a `true` y activa la línea de la tienda en `_data/navegacion.yml`.

## Dirección del sitio

Si usas dominio propio, cambia `url` por tu dominio y deja `baseurl: ""` en `_config.yml`.

## Probar en tu ordenador (opcional)

Requiere Ruby. En la carpeta del proyecto: `bundle install` y luego `bundle exec jekyll serve`. El sitio se abre en `http://localhost:4000/receptaculo-recursivo/`.
