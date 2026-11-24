# Plantilla MF0493_3

Proyecto Astro base para la prueba práctica. **No hay que hacer fork**: clonas este repositorio y, cuando vayas a publicar, apuntas tu Git a un repositorio propio.

## 1. Clonar y trabajar en local

```bash
git clone https://github.com/canodelacuadra/mf0493-3-plantilla.git
cd mf0493-3-plantilla
npm install
npm run dev
```

La web se abre en `http://localhost:4321`.

## 2. Publicar en tu cuenta de GitHub

1. Crea en tu cuenta un repositorio **público** (Pages no publica desde repos privados en cuentas gratuitas), por ejemplo `mf0493-3-tu-usuario`. Créalo vacío: sin README ni licencia.
2. Cambia el remoto del proyecto para que apunte a tu repositorio:

   ```bash
   git remote set-url origin https://github.com/TU_USUARIO/TU_REPO.git
   ```

3. Edita `astro.config.mjs`: pon tu usuario y el nombre de tu repo en `site`, y descomenta `base: '/TU_REPO'`. No hace falta cambiar los enlaces: las rutas del menú, del blog y de la imagen usan `import.meta.env.BASE_URL` y se adaptan solas (en local valen `/` y al publicar valen `/TU_REPO/`). Si las sustituyes por rutas fijas empezadas en `/`, se romperán en GitHub Pages.
4. Comprueba que `.github/workflows/deploy.yml` está en el proyecto.
5. Sube los cambios:

   ```bash
   git add .
   git commit -m "Prepara el despliegue en GitHub Pages"
   git push -u origin main
   ```

6. En tu repositorio, entra en **Settings → Pages → Build and deployment → Source** y elige **GitHub Actions**. En la pestaña **Actions**, habilita los workflows si GitHub te lo pide.
7. Cuando el workflow termine, abre `https://TU_USUARIO.github.io/TU_REPO/` y comprueba que se ven las imágenes y los enlaces.

## Qué contiene

- `src/layouts/BaseLayout.astro`: cabecera, menú, pie y etiquetas SEO (`title`, `description`).
- `src/pages/index.astro`: página de inicio.
- `src/pages/servicios.astro`: página de información.
- `src/pages/blog/index.astro`: índice automático del blog; edita el array `articulos` con el título, enlace y resumen de cada entrada. Si cambias un título, actualízalo también aquí.
- `src/pages/blog/roma.astro` y `src/pages/blog/florencia.astro`: los dos artículos (enlazan de vuelta al índice).
- `src/styles/global.css`: estilos básicos.
- `public/images/`: imágenes de Roma y Florencia usadas en la portada, además de `ejemplo.svg`.
- `.github/workflows/deploy.yml`: configuración de GitHub Actions.

Sustituye los textos, las imágenes y los datos de contacto por los de tu propio proyecto.

## Recordatorio antes de empezar

La plantilla incluye `src/pages/blog/index.astro` y el enlace «Blog» del menú apunta a esa página. Completa el array `articulos` con el título, el enlace y el resumen de cada entrada. **Si cambias el título de un artículo, actualízalo también en el índice.**

> Para el profesor: conviene leer este párrafo en voz alta al entregar la prueba, porque el examen impreso no menciona explícitamente el índice del blog.

## Entrega

La ficha se entrega firmada en papel con la URL del repositorio y la URL de GitHub Pages. Como respaldo se puede entregar también la carpeta del proyecto (en memoria o comprimida, incluyendo la carpeta oculta `.git`).
