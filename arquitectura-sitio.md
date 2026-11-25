# Arquitectura del sitio

Decisión (25/11/2026): una sección por subdominio, un repo por sección, cada uno con su propio GitHub Pages y dominio. Los repos de proyecto son el laboratorio; los repos de sección son la vidriera y solo reciben la versión que se decide publicar.

| Sección | Dominio | Repo | Publica |
|---|---|---|---|
| Portada | juancib.ar | `portfolio-site` | GitHub Actions al pushear `main` |
| Blog | blog.juancib.ar | `blog` | `quarto publish gh-pages` |
| CV | cv.juancib.ar | `cv` | `quarto publish gh-pages` |
| Clases | clases.juancib.ar | `clases` | `quarto publish gh-pages` |
| Gráficos | graficos.juancib.ar | `graficos` | `quarto publish gh-pages` |

Repos de proyecto (p. ej. `subte_estaciones`): trabajo libre, no se publican. Cuando un post está listo se copia su carpeta (qmd, helpers, figuras) al repo `blog` y se etiqueta el commit de origen.

## Alta de un subdominio (una vez)

1. Cloudflare: `CNAME <sección> → jpcib.github.io`, DNS only (nube gris).
2. Repo: archivo `CNAME` con `<sección>.juancib.ar`, incluido en `resources` de `_quarto.yml`.
3. GitHub: Settings → Pages → rama `gh-pages`, custom domain, Enforce HTTPS cuando haya certificado.

## Convenciones

- Navbar con links absolutos a las otras secciones (`https://blog.juancib.ar`).
- Mismo `_brand.yml` en todos los repos (después, extensión de Quarto).
- Blog: listado `type: grid` con imagen, título, categorías y bajada. Serie con categoría `SobrePensar`.
- En cada repo: borradores con `draft: true`, `freeze: auto`, un tag por publicación.
