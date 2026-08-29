# Decisiones de diseño

Registro de las decisiones que tomamos y el porqué, para no perder el hilo ni
repetir discusiones.

## Estética: "cruda DIY militante" sobre estructura ordenada

Evaluamos tres direcciones visuales:

1. **Cruda / DIY militante** — fanzine, afiche callejero, tipografía fuerte,
   texturas de cartón y tierra.
2. **Orgánica y cálida** — tonos tierra y verdes, formas suaves, mucha foto.
3. **Terrosa pero moderna** — base orgánica con layout limpio y ordenado.

**Decisión:** la opción 1 es la que tiene más personalidad y es la más fiel a
la filosofía del espacio, pero por sí sola arriesga volverse caótica. Tomamos
**la crudeza de la 1 (tipografía de afiche, texturas de cartón, sellos, cinta)
montada sobre la estructura ordenada de la 3**. Así hay carácter fuerte sin
sacrificar legibilidad, y se evita la sensación de "web genérica hecha por IA".

## Sistema visual

- **Tipografías**
  - Títulos: `Anton` (grotesca condensada, tipo afiche) en mayúsculas.
  - Cuerpo: `Work Sans`.
  - Sellos y etiquetas: `Special Elite` (máquina de escribir), aporta el aire
    fanzine.
- **Paleta** (tierra / cartón / rojo afiche)
  - Tinta: `#241f1b` · Papel: `#e8dcc4` · Kraft: `#cbb389`
  - Rojo afiche: `#d8532e` (acento principal) · Verde huerta: `#5c6b30`
- **Recursos de personalidad:** cinta sobre las fotos (pseudo-elementos),
  sellos rojos, tarjetas rotadas con sombra dura (no difusa), subrayados
  torcidos, cifras tipo ticket, textura de papel kraft de fondo. Nada de
  degradés suaves ni sombras blandas "corporativas".

## Fotos: repartidas + galería

Las fotos son el activo más fuerte del proyecto. Decisión: **ambas cosas**.
Repartidas por las secciones como narrativa (la huerta en "Sobre nosotros", la
construcción del salón en la galería) y una galería agrupada para quien quiere
ver más. Se usan fotos reales, sin filtros de stock: la crudeza "hecho a pulmón"
se luce.

- **Hero:** foto de la comunidad reunida con la bandera wiphala y chicos
  plantando. Recortada del original (1200×1600 → 1200×992) para sacar el pasto
  vacío de abajo. Lleva un gradiente oscuro encima para que el título blanco se
  lea nítido.

## Donación

- **Aparece varias veces**, no una sola: es una landing cuyo objetivo es donar.
  Regla: el botón siempre a un scroll de distancia (hero, después de "en qué se
  usa tu aporte", y en el cierre) + botón fijo en el header.
- **Método (pendiente de definir).** Recomendación para un espacio autogestivo y
  anticapitalista en Argentina:
  - **Alias / CVU (transferencia directa)** como opción principal: cero
    comisiones, cero intermediarios, la más coherente con la práxis.
  - **Cafecito** como segunda opción de baja fricción: permite aportes únicos o
    mensuales con tarjeta, muy usado en la escena independiente/militante.
  - MercadoPago como tercera opción opcional (cómodo pero más "sistema" y con
    comisión).
- La sección **"en qué se usa tu aporte"** es la que más mueve donaciones:
  conviene mostrar 3-4 destinos concretos y costeados, con barra de progreso.

## Textos y tono

- **CTA con identidad**, no un frío "Donar": se usa "Sembrá el cambio" (hero),
  "Sembrá con nosotros" (header y cierre), "Bancá lo que creés".
- Tono directo y combativo pero cálido. Castellano rioplatense.

## Decisiones técnicas

- **Sin build ni dependencias** (salvo Google Fonts por CDN). El CSS se separó a
  `assets/css/styles.css`; el JS que queda es mínimo e inline. Prioriza
  simplicidad: cualquiera puede abrir el repo y entender qué toca.
- **Hosting elegido: Cloudflare Pages para producción, GitHub Pages para la
  previa.** La rama `main` se publica en `latupac.org` (dominio registrado en
  Cloudflare, así que el DNS y el certificado los maneja la misma cuenta) y la
  rama `staging` en `facundo-p.github.io/web-tupac-amaru/`.

  Por qué así: se probó tener un repo aparte sólo para hostear
  (`huerta-tupac-amaru.github.io`) y terminó siendo dos repos con la misma
  historia que había que sincronizar a mano. Un solo repo con dos ramas
  atadas a dos entornos hace explícito qué está publicado dónde, y promover a
  producción es un `merge --ff-only`.

  La integración de Cloudflare es por Git (no por CI): no hay secrets ni
  workflows que mantener, y si el proyecto cambia de manos hay menos piezas
  que explicar. Los "preview branches" de Cloudflare están apagados a
  propósito para que la previa viva en un solo lugar.

## Cosas abiertas / a decidir

- Método de donación definitivo y links reales.
- Tratamiento de color de las fotos: ¿a color pleno (más auténtico) o duotono
  tierra/rojo (más integrado a la paleta)?
- Nivel de crudeza: se puede llevar más extremo (más collage) o más contenido.
- Uso de `maleza-1.jpeg`: candidata para un "antes/basural" en la línea de
  tiempo o una comparación antes/después.
