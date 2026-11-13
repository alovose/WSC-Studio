# WSC Studio Web

Editor de datos estático para publicar en GitHub Pages. No requiere servidor ni instalación: el navegador abre el APK y edita `assets/template.db` localmente. La página no envía el APK ni la base de datos a un servicio externo. Las bibliotecas SQLite y ZIP se cargan desde una CDN, por lo que se necesita conexión a Internet.

## Publicar

1. Crea un repositorio en GitHub y sube `index.html` a la raíz.
2. En el repositorio, abre **Settings → Pages**.
3. En **Build and deployment**, elige **Deploy from a branch**, selecciona la rama `main` y la carpeta `/ (root)`, y guarda.
4. Abre la dirección de Pages que indique GitHub.

También puedes probarlo localmente abriendo `index.html` en el navegador con conexión a Internet.

## Usar

1. Haz clic en **Abrir APK o template.db** y selecciona el APK o una base SQLite compatible.
2. Edita equipos, competiciones, jugadores o transiciones de ascensos/plazas.
3. Haz clic en **Descargar template.db editado** para exportar la base de datos.

El sitio no empaqueta ni firma APKs. Para aplicar la base al juego, hay que reemplazar `assets/template.db` en el APK y firmar el paquete con herramientas locales. Conserva una copia del APK y de la base originales. Al añadir registros se copia un registro existente como modelo; añadir equipos, jugadores y especialmente competiciones puede requerir completar relaciones y otros datos del juego.

## Límites actuales

- El editor está preparado para la estructura `Club`, `Competition` y `Player` del APK indicado, no para cualquier versión del juego.
- Las transiciones de ascenso/plazas se guardan en el banco; no se calculan posiciones ni calendario.
- Al eliminar equipos o competiciones no se borran automáticamente todas las referencias asociadas.
- La lista muestra hasta 3000 registros por vez.
