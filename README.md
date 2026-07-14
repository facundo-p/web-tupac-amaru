# Web — Biblioteca Popular Tupac Amaru

Landing page de donaciones para un proyecto comunitario barrial: huerta urbana,
biblioteca popular y espacio de encuentro. Autogestivo, asambleario e
independiente, con más de veinte años de trabajo territorial.

El objetivo de la web es contar de qué se trata el espacio de forma ágil y
emotiva, y que quien llega tenga ganas de aportar para que siga creciendo.

## Estado

Prototipo funcional (estático, un solo archivo). Contenido mayormente de
ejemplo — ver [`docs/CONTENIDO.md`](docs/CONTENIDO.md) para qué es real y qué
falta reemplazar.

## Estructura

```
web-tupac-amaru/
├── index.html              Landing completa (HTML + CSS + JS inline)
├── assets/
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

HTML + CSS + JavaScript vanilla, sin frameworks ni build. Pensado para poder
publicarse gratis en cualquier hosting estático (Netlify, Cloudflare Pages,
GitHub Pages, Vercel).

## Pendientes principales

- Reemplazar contenido de ejemplo por el real (números, hitos, metas, alias).
- Definir método de donación real (ver `docs/DECISIONES-DISENO.md`).
- Sumar más fotos para la galería.
- Datos de contacto y redes reales en el footer.
