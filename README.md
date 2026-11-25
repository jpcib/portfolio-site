# portfolio-site

Portada de [juancib.ar](https://juancib.ar), hecha con Quarto.

- Publica GitHub Actions al pushear `main` (`.github/workflows/publish.yml`).
- Solo se renderizan `index.qmd` y `cv.qmd` (ver `project.render` en `_quarto.yml`).
- Las tarjetas de la portada salen de `secciones.yml`.
- Las demás secciones viven en sus propios repos y subdominios (`blog.juancib.ar`, etc.).
