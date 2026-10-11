# Portfolio — Pablo Caprio

Sitio estático de una sola página. No necesita build ni servidor: es un único `index.html`.

## Cómo publicarlo (cualquier opción sirve)
- **Netlify**: entrá a app.netlify.com/drop y arrastrá esta carpeta.
- **Vercel**: `vercel` dentro de la carpeta, o importá el repo.
- **Cloudflare Pages / GitHub Pages**: subí los archivos tal cual (la raíz debe contener `index.html`).
- **Hosting tradicional (cPanel, FTP)**: subí `index.html` y `robots.txt` a `public_html`.

Funciona con HTTPS y también abriendo `index.html` directamente.

## Qué carga desde internet (CDN)
- Fuentes: Google Fonts (Geist, Geist Mono).
- Three.js r128, GSAP 3.12.5 y ScrollTrigger (cdnjs.cloudflare.com).
Si alguna falla, el sitio sigue funcionando: sin Three.js queda un fondo suave, y sin GSAP el fondo se mueve con el scroll sin suavizado.
Si querés que sea 100 % independiente, descargá esos 3 scripts, guardalos en una carpeta `/vendor` y cambiá las 3 etiquetas `<script src=...>` por rutas locales.

## Cosas para completar (buscalas en `index.html`)
1. **Email del formulario**: buscá `const CONTACT = { email: '' ...`. Poné tu email ahí y el formulario "Start a project" abre el correo con el brief armado. Si queda vacío, copia el brief y abre LinkedIn.
2. **Imágenes reales de los proyectos**: en `const PROJECTS = [ ... ]` cada proyecto tiene `img:''` (portada). Poné la ruta o URL de tu imagen 16:9. También podés usar `figs: { wire:'', screens:'', system:'', flow:'' }` para las figuras del case study.
3. **Textos de los case studies**: están en el mismo arreglo `PROJECTS` (contexto, desafío, objetivos, decisiones, resultado). Reemplazalos por lo que realmente hiciste en cada uno.
4. **Dominio y vista previa**: agregá `<link rel="canonical">` y una imagen `og:image` cuando tengas el dominio.
5. **Color primario (botones)**: variable `--primary` (arriba, en `:root`).

## Atajos
- Tema claro/oscuro: botón arriba a la derecha (se guarda en el navegador).
- El sitio respeta "reducir movimiento" del sistema: desactiva las escenas con scroll y deja una versión estática.
