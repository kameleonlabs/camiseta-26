# Generador de camiseta "26" con nombres

Web de una sola página (`index.html`, sin servidor) que rellena un número grande
con los nombres del grupo. Cada nombre se coloca **letra a letra sobre una curva**,
con **cada letra de un tamaño**, usando **tipografías orgánicas** de Google Fonts.
Ningún nombre se corta ni se solapa (colisión por letra contra la silueta del número).

## Para Isabel (uso)

Abre `index.html` (doble clic) o la URL publicada. Desde el panel izquierdo:

- **Tipografía del número (26)** y **Tipografía de los nombres**: dos selectores
  independientes. Además puedes escribir el nombre de **cualquier fuente de Google Fonts**
  y pulsar *Cargar*.
- **🎲 Regenerar**: nueva distribución al azar.
- **Curvatura / Densidad / Variación de tamaño por letra**: tres sliders.
- **♥ Guardar**: guarda la versión actual (con su miniatura) en *Favoritas*.
  Se quedan en tu navegador; clic en una miniatura para recuperarla tal cual.
- **Descargas**: `SVG`, `PNG` y `PDF`.
- **Editar lista de nombres**: despliega abajo para cambiar los nombres.

### ¿Qué descargo para la imprenta?
- **PDF** → recomendado. Al pulsar *PDF* se abre *Imprimir*; elige **"Guardar como PDF"**.
  Sale **vectorial y con la fuente incrustada** (se imprime perfecto en cualquier sitio).
- **PNG** → imagen de alta resolución (la fuente va "quemada", también fiable).
- **SVG** → vectorial editable, pero **depende de que tengan instalada la fuente**;
  úsalo solo si vas a abrirlo en Illustrator/Inkscape con esa tipografía.

## Publicar la web (rápido y gratis)

Es estático: solo hay que subir `index.html`.

- **Netlify Drop** (lo más rápido): entra en <https://app.netlify.com/drop> y
  **arrastra la carpeta** (o el `index.html`). Te da una URL pública al instante.
- **GitHub Pages**: sube `index.html` a un repo y activa Pages.
- **Vercel / Cloudflare Pages / surge.sh**: igual de simple.

Requiere conexión (las fuentes se cargan desde Google Fonts).

## Notas técnicas
- Algoritmo: silueta del número rasterizada a una máscara; imagen integral para
  comprobar contención en O(1) y rejilla de ocupación para los solapes; los nombres
  se disponen sobre arcos de curvatura aleatoria, con tamaño por letra y un límite
  que evita que queden boca abajo.
- Todo ocurre en el navegador (sin backend). Las favoritas se guardan en `localStorage`.
