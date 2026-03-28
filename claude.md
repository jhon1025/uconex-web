# Uconex — Sitio Web Corporativo

## Qué es este proyecto
Sitio web de Uconex, agencia de marketing digital y automatización con IA en Colombia. Incluye home, blog con artículos, y páginas de servicio. Optimizado para AIO (AI Overview Optimization).

## Stack
- **Framework:** Astro
- **CSS:** Tailwind CSS
- **Despliegue:** (por definir)

## Comandos
- `npm run dev` — Servidor de desarrollo
- `npm run build` — Build de producción
- `npm run preview` — Preview del build

## Paleta de colores (OBLIGATORIA — del brandbook oficial)

| Nombre          | HEX       | RGB             | Uso                                      |
|-----------------|-----------|-----------------|------------------------------------------|
| Chrysier Blue   | `#4924BC` | 73, 36, 188     | Color primario oscuro, CTAs, acentos     |
| Majorelle Blue  | `#7148FC` | 113, 72, 252    | Color primario, gradientes, highlights   |
| Tropical Indigo | `#9D8CF4` | 157, 140, 244   | Color claro, hovers, fondos suaves       |
| Night           | `#161616` | 22, 22, 22      | Fondo oscuro principal, nav, footer      |
| Blanco          | `#FFFFFF` | 255, 255, 255   | Texto sobre fondo oscuro, fondos claros  |

### Configuración Tailwind
```js
// tailwind.config.mjs → theme.extend.colors
colors: {
  'chrysier': '#4924BC',
  'majorelle': '#7148FC',
  'tropical': '#9D8CF4',
  'night': '#161616',
}
```

### Gradientes de marca
- **Glow morado:** `radial-gradient(ellipse, rgba(113,72,252,0.4), transparent 70%)`
- **Fondo hero:** Night (#161616) con grid pattern + glow Majorelle
- **Cards highlight:** `linear-gradient(135deg, #4924BC, #7148FC, #9D8CF4)`
- NUNCA usar otros morados. Solo `#4924BC`, `#7148FC`, `#9D8CF4`.

## Tipografías (OBLIGATORIAS — del brandbook oficial)

### ITC Avant Garde Gothic Pro → Títulos y headlines
- Ubicación: `public/fonts/avant-garde/`
- Pesos para web: Book (400), Medium (500), Demi (600), Bold (700)
- Cada peso tiene variante Oblique
- Estilo: geométrica, limpia, futurista

### Graphie → Párrafos, subtítulos y cuerpo de texto
- Ubicación: `public/fonts/graphie/`
- Pesos para web: Regular (400), SemiBold (600), Bold (700)
- Cada peso tiene variante Italic
- Estilo: rounded, amigable, moderna

### Configuración CSS
```css
@font-face {
  font-family: 'Avant Garde';
  src: url('/fonts/avant-garde/ITC_Avant_Garde_Gothic_Pro-Book.otf') format('opentype');
  font-weight: 400;
  font-display: swap;
}
@font-face {
  font-family: 'Avant Garde';
  src: url('/fonts/avant-garde/ITC_Avant_Garde_Gothic_Pro-Medium.otf') format('opentype');
  font-weight: 500;
  font-display: swap;
}
@font-face {
  font-family: 'Avant Garde';
  src: url('/fonts/avant-garde/ITC_Avant_Garde_Gothic_Pro-Demi.otf') format('opentype');
  font-weight: 600;
  font-display: swap;
}
@font-face {
  font-family: 'Avant Garde';
  src: url('/fonts/avant-garde/ITC_Avant_Garde_Gothic_Pro-Bold.otf') format('opentype');
  font-weight: 700;
  font-display: swap;
}

@font-face {
  font-family: 'Graphie';
  src: url('/fonts/graphie/Graphie-Regular.otf') format('opentype');
  font-weight: 400;
  font-display: swap;
}
@font-face {
  font-family: 'Graphie';
  src: url('/fonts/graphie/Graphie-SemiBold.otf') format('opentype');
  font-weight: 600;
  font-display: swap;
}
@font-face {
  font-family: 'Graphie';
  src: url('/fonts/graphie/Graphie-Bold.otf') format('opentype');
  font-weight: 700;
  font-display: swap;
}
```

### Configuración Tailwind
```js
// tailwind.config.mjs → theme.extend.fontFamily
fontFamily: {
  'heading': ['"Avant Garde"', 'sans-serif'],
  'body': ['"Graphie"', 'sans-serif'],
}
```

### Uso en el código
- `h1` a `h3`: `font-heading` (Avant Garde), weight 600-700
- `h4` a `h6`: `font-body` (Graphie), weight 700
- `p`, `li`, `span`: `font-body` (Graphie), weight 400
- `button`, `.btn`: `font-body` (Graphie), weight 600-700

## Logo — Variantes

| Archivo                    | Uso                                     |
|----------------------------|-----------------------------------------|
| `Imagotipo_original.svg`   | Logo completo — uso principal           |
| `UCONEX_BLANCO.svg`        | Logotipo para fondos oscuros (nav, footer) |
| `Isotipo.svg`              | Solo el símbolo ✦                       |
| `Isotipo_Negativo.svg`     | Símbolo para fondo oscuro               |
| `UCX.svg`                  | Siglas UCX                              |
| `Siglas_en_Negativo.svg`   | Siglas en negativo                      |

- **Nav:** `UCONEX_BLANCO.svg`
- **Footer:** `UCONEX_BLANCO.svg`
- **Favicon:** `Isotipo.svg`
- Ubicación: `public/images/logo/`

## Texturas de marca
- 5 gradientes en `public/images/textures/` (TEXTURA_UCONEX_1-5.png)
- Usar como overlays decorativos en secciones destacadas

## Grid Pattern (CSS custom)
```css
@layer utilities {
  .bg-grid-pattern {
    --grid-color: rgba(255, 255, 255, 0.06);
    background-image:
      linear-gradient(0deg, transparent 24%, var(--grid-color) 25%, var(--grid-color) 26%, transparent 27%, transparent 74%, var(--grid-color) 75%, var(--grid-color) 76%, transparent 77%, transparent),
      linear-gradient(90deg, transparent 24%, var(--grid-color) 25%, var(--grid-color) 26%, transparent 27%, transparent 74%, var(--grid-color) 75%, var(--grid-color) 76%, transparent 77%, transparent);
    background-size: 60px 60px;
  }
  .mask-fade-down {
    mask-image: linear-gradient(to bottom, black 0%, rgba(0,0,0,0.7) 30%, rgba(0,0,0,0.3) 50%, transparent 70%);
  }
}
```

## Estructura de archivos
```
public/
  fonts/
    avant-garde/     ← .otf ITC Avant Garde Gothic Pro
    graphie/          ← .otf Graphie
  images/
    logo/             ← SVGs del logo
    textures/         ← TEXTURA_UCONEX_1-5.png
docs/
  wireframe-home.html
  wireframe-internas.html
  uconex-hero.html
  uconex-hero-tailwind.html
```

## Arquitectura del sitio
- Ver `docs/` para wireframes de referencia
- Home: Hero, Problema, Servicios (4), Cómo Funciona, Resultados, Testimonios, FAQ (5), Blog Preview, CTA Final, Footer
- Blog: Listing con filtros + Single con sidebar, TL;DR, FAQ interna

## Reglas importantes
- SOLO usar colores de la paleta oficial. No inventar morados ni grises.
- SOLO usar Avant Garde (títulos) y Graphie (cuerpo). No usar Inter, Arial ni system fonts.
- Schema JSON-LD server-rendered en `<head>`
- Todo responsive mobile-first
- Textos en español
- Robots.txt debe permitir: Googlebot, Bingbot, CCBot, anthropic-ai, GPTBot
