# Cómo subir tu Landing Page a GitHub Pages

¡Listo! Ya tienes la base de tu landing page premium en Astro. Estos son los pasos para que aparezca publicada en internet gratis con GitHub Pages:

## Paso 1: Configurar el repositorio en GitHub
1. Entra a tu cuenta de GitHub y crea un **Nuevo Repositorio** (ej. `mi-landing-page`).
2. Abre la terminal en esta carpeta (`C:\Users\ferna\.gemini\antigravity\scratch\landing-page`) y ejecuta:
   ```bash
   git init
   git add .
   git commit -m "Commit inicial"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
   git push -u origin main
   ```

## Paso 2: Editar la configuración de Astro (Solo si no usas un dominio personalizado)
1. Abre el archivo `astro.config.mjs`.
2. Verás dos líneas comentadas: `site` y `base`. 
   - Cambia `site` por `https://TU_USUARIO.github.io`
   - Cambia `base` por `'/TU_REPOSITORIO'` (nota la barra inicial).
   Esto es importante para que Astro sepa dónde cargar los estilos (CSS e imágenes).

## Paso 3: Configurar GitHub Pages en tu Repositorio
1. En la página de tu repositorio en GitHub, ve a la pestaña **Settings** (Configuración).
2. En la barra lateral izquierda, haz clic en **Pages**.
3. En la sección **Build and deployment**, busca la opción **Source**.
4. Cambia el *Source* de "Deploy from a branch" a **"GitHub Actions"**.

## ¡Y listo!
Eso es todo. La próxima vez que hagas un cambio y hagas `git push`, GitHub ejecutará automáticamente el archivo `.github/workflows/deploy.yml` que ya te he dejado creado. En unos minutos, tu sitio estará en vivo.

### Para probarlo localmente ahora mismo:
Ejecuta:
```bash
npm run dev
```
Y abre tu navegador en `http://localhost:4321`
