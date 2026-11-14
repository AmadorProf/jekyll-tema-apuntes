# jekyll-tema-apuntes

Layout base compartido por los repos de apuntes de [AmadorProf](https://github.com/AmadorProf) (Rust, SQL, Python-Pandas, Virtualizacion, ApuntesIAD, ApuntesGithub, CiberOT-Apuntes, CyberIT-Apuntes).

No es un tema visual: cada repo conserva su propia paleta de colores y tipografía en su propio `assets/css/style.scss`, sobre `jekyll-theme-cayman`. Este repo solo centraliza `_layouts/default.html` (sidebar de navegación entre módulos, cabecera, pie de página) para que un cambio estructural — por ejemplo un bug en el layout — se corrija una sola vez en lugar de repetirlo en cada repo.

## Uso

En el `_config.yml` de cada repo:

```yaml
remote_theme: AmadorProf/jekyll-tema-apuntes
plugins:
  - jekyll-remote-theme

# Variables que lee el layout:
github_repo: AmadorProf/<nombre-del-repo>   # usado en el pie de página
mermaid: true                                # opcional, activa soporte de diagramas Mermaid
```

Cada repo necesita además su propio `_data/modules.yml` con, por cada módulo, los campos `title`, `filename` y `url` (este último, el nombre de archivo con `urllib.parse.quote` aplicado si tiene espacios o acentos).
