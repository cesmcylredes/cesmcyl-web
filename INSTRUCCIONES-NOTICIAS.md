# Cómo añadir o editar una noticia (sin saber programar)

Todas las noticias de la web viven en la carpeta `noticias/`, cada una en su
propio archivo. La página web las lee automáticamente: no hace falta tocar
el diseño ni el código para publicar algo nuevo.

Una vez publicada una noticia, se actualiza sola en dos sitios a la vez:
- El "Tablón" de la portada (arriba a la derecha)
- La sección "Noticias" más abajo en la página

## Para añadir una noticia nueva

1. Copia el archivo `noticias/_plantilla.md`.
2. Ponle un nombre nuevo con este formato: `AAAA-MM-DD-titulo-corto.md`
   Ejemplo: `2026-07-10-nueva-convocatoria-bolsa.md`
3. Rellena estos campos entre las rayas `---`:
   - `title`: el titular de la noticia
   - `date`: la fecha, formato AAAA-MM-DD
   - `category`: una etiqueta corta (OPE, Bolsa, CESM, MIR 2026...)
   - `pinned`: escribe `true` si quieres que salga fija arriba del todo
     (en "Destacado"), o `false` si es una noticia normal
4. Debajo de la segunda raya `---`, escribe el texto de la noticia.
5. Abre el archivo `noticias/indice.json` y añade el nombre de tu nuevo
   archivo a la lista (con una coma después del anterior). Ejemplo:

   ```json
   [
     "2026-07-10-nueva-convocatoria-bolsa.md",
     "2026-02-05-programa-mir-2026.md",
     ...
   ]
   ```

   El orden de la lista no importa: la web ordena las noticias sola por
   fecha, de la más reciente a la más antigua.

6. Guarda los cambios. En cuanto se publiquen, la web se actualiza sola.

## Para editar una noticia existente

Abre su archivo `.md` dentro de `noticias/`, cambia lo que haga falta y
guarda. No es necesario tocar `indice.json`.

## Para quitar una noticia de la web

Quita su nombre de la lista en `noticias/indice.json`. No hace falta borrar
el archivo `.md` (puedes dejarlo guardado por si se quiere reutilizar).

## Noticias fijas ("Destacado")

Cualquier noticia con `pinned: true` aparece en la sección "Destacado" del
Tablón, con un botón de descarga/enlace si le añades:

```
url: "https://enlace-al-documento-o-pagina"
cta: "Descargar programa"
description: "Frase corta opcional bajo el título"
```

Puede haber tantas noticias fijas como haga falta: el espacio se ajusta solo.

## Trabajar en equipo (varios compañeros a la vez)

Recomendamos gestionar esta carpeta en GitHub (gratis) para que:
- Varias personas puedan editar sin pisarse el trabajo
- Quede guardado un historial de quién cambió qué y cuándo
- Los cambios se publiquen solos en la web (con Netlify conectado a GitHub)

Cada persona solo necesita:
1. Una cuenta de GitHub (gratis)
2. Permiso de acceso al repositorio (te lo da quien administre la cuenta)
3. Editar los archivos `.md` desde el propio navegador, con el botón del
   lápiz (✏️) que aparece en GitHub al abrir un archivo

No hace falta instalar nada ni saber programar para seguir estos pasos.
