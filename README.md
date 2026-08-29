# Web — Biblioteca Popular Tupac Amaru

Landing page de donaciones para un proyecto comunitario barrial: huerta urbana,
biblioteca popular y espacio de encuentro. Autogestivo, asambleario e
independiente, con más de veinte años de trabajo territorial.

El objetivo de la web es contar de qué se trata el espacio de forma ágil y
emotiva, y que quien llega tenga ganas de aportar para que siga creciendo.

## Estado

Prototipo funcional (estático, sin build). Contenido mayormente de
ejemplo — ver [`docs/CONTENIDO.md`](docs/CONTENIDO.md) para qué es real y qué
falta reemplazar.

## Estructura

```
web-tupac-amaru/
├── index.html              Landing completa (HTML + JS inline)
├── assets/
│   ├── css/
│   │   └── styles.css      Todos los estilos
│   └── images/             Fotos reales del espacio
│       ├── hero-huerta.jpeg   Hero (recortada del original)
│       ├── huerta-1.jpeg      Canteros de la huerta
│       ├── almacigos.jpeg     Plantines en el invernadero
│       ├── construccion-1.jpeg Construcción del salón (SUM)
│       └── maleza-1.jpeg      Sin usar aún (posible "antes / basural")
└── docs/
    ├── PROYECTO.md         Esencia, objetivo y filosofía del espacio
    ├── DECISIONES-DISENO.md Decisiones de diseño y por qué
    └── CONTENIDO.md        Contenido real vs. placeholder y pendientes
```

## Cómo verlo

Abrir `index.html` en el navegador (doble clic). No requiere build ni
dependencias. Las fuentes se cargan desde Google Fonts (necesita conexión).

## Stack

HTML + CSS + JavaScript vanilla, sin frameworks ni build. El CSS vive en
`assets/css/styles.css`; el poco JS que hay está inline en `index.html`.

## Deploy

Dos entornos, cada uno atado a una rama. No hay build: se publican los
archivos tal cual están en el repo.

| Rama | Entorno | Dónde | URL |
|---|---|---|---|
| `staging` | Previa | GitHub Pages | https://facundo-p.github.io/web-tupac-amaru/ |
| `main` | Producción | Cloudflare Pages | https://latupac.org |

Flujo de trabajo:

```bash
git switch staging
# ... cambios, commit ...
git push origin staging          # se publica solo en la URL de GitHub

# cuando está aprobado, se promueve a producción:
git switch main
git merge --ff-only staging
git push origin main             # Cloudflare deploya solo
```

`index.html` incluye `<link rel="canonical" href="https://latupac.org/">` para
que la previa no compita con producción en buscadores. Es el mismo archivo en
las dos ramas, así que no hay que tocarlo al promover.

## Pendientes principales

- Reemplazar contenido de ejemplo por el real (hitos 2011/2017, metas, alias).
- Definir método de donación real (ver `docs/DECISIONES-DISENO.md`).
- Sumar más fotos para la galería.
- Datos de contacto y redes reales en el footer.
- Sumar `meta description` y etiquetas Open Graph: hoy el sitio se comparte por
  WhatsApp sin título, descripción ni imagen de preview.
