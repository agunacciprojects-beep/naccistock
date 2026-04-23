# NacciStock — Landing page (flyer)

Single-file landing en estilo GitHub (dark, geométrico, sticky nav, cards) con
la marca de NacciStock / agunacci, lista para subirse a GitHub Pages.

## Archivos

```
flyer/
├── index.html            ← la página completa
├── README.md             ← este archivo
└── assets/
    ├── logo.png          ← escudo NacciTech vertical (1.2 MB)
    ├── hero-bg.png       ← versión landscape (se usa como OG image)
    └── favicon.ico       ← ícono para la pestaña del navegador
```

## Cómo subirlo a GitHub Pages (5 minutos)

### Opción A — página de repo dedicada

1. En [github.com](https://github.com/) → botón verde **New repository**.
   - Nombre: `naccistock` (o lo que prefieras).
   - Visibilidad: **Public** (GitHub Pages gratis sólo en público).
2. Subí el contenido de esta carpeta:
   - Opción rápida vía web: **Add file → Upload files** → arrastrá `index.html` y la carpeta `assets/`.
   - Opción con git:
     ```bash
     cd flyer
     git init
     git add .
     git commit -m "NacciStock landing"
     git branch -M main
     git remote add origin https://github.com/TU_USUARIO/naccistock.git
     git push -u origin main
     ```
3. En el repo → **Settings → Pages**.
4. En **Source**, elegí **Deploy from a branch**.
5. En **Branch** seleccioná `main` y carpeta `/ (root)`.
6. Click **Save**.
7. GitHub te muestra la URL pública en ~1 minuto:
   `https://TU_USUARIO.github.io/naccistock/`

### Opción B — página personal

Si querés la URL raíz (sin `/naccistock` al final):
- Creá un repo llamado **exactamente** `TU_USUARIO.github.io`.
- Subí los mismos archivos ahí.
- La URL queda `https://TU_USUARIO.github.io/`.

## Personalización antes de publicar

Editá `index.html` y buscá/reemplazá:

| Qué | Dónde | Valor actual |
|---|---|---|
| Número de WhatsApp | 2 lugares (CTA final + footer) | `5493834000000` (placeholder) |
| Email | Footer | `agunacci@example.com` |
| Año copyright | Footer | `© 2026` |

También podés ajustar:
- **Precios** (`$30.000/mes`, `$160.000`) en la sección `#pricing`.
- **Versión** (`1.0`) en el badge del hero y el footer.
- **Testimonios**: si querés sumar una sección de "qué dicen los clientes",
  insertála antes de `#pricing` copiando el estilo de `.features-grid`.

## Verificar localmente

Abrí `index.html` directamente con doble click en Windows (Chrome/Edge/Firefox
funcionan). Todo está autocontenido — no hay build ni servidor necesario.

Si querés un servidor local simple:
```bash
cd flyer
npx serve .   # o: python -m http.server 8000
```

## Tecnologías

- HTML5 + CSS3 puro (sin frameworks).
- Google Fonts: Poppins + JetBrains Mono.
- IntersectionObserver para animaciones fade-in on scroll.
- Grid + Flexbox responsive (mobile-first break en 720-820px).

## SEO / meta

El `<head>` incluye:
- `<meta name="description">` optimizada para "POS despensa Catamarca".
- Open Graph (`og:title`, `og:description`, `og:image`) — al pegar el link en
  WhatsApp / Facebook aparece una preview con el logo y el pitch.
- `<meta name="theme-color">` para que la barra del navegador en móvil tome el
  color del brand.

## Paleta (por si querés replicar en otro lado)

```css
--nt-black:    #0a0b0e;
--nt-blue:     #3b9fe8;
--nt-success:  #3be89a;
--nt-warn:     #f5a623;
```

Poppins 700/800 para títulos, Poppins 400/500 para texto, JetBrains Mono para
detalles tipo terminal.
