# CLAUDE.md — pabloblazquez.es

## Qué es este proyecto

Web personal y de negocio de **Pablo Blázquez Campos**, desarrollador web freelance
en Antequera (Málaga). No es un portfolio de programador: es una **página de venta**
dirigida a dueños de pequeños negocios locales (bares, clínicas, tiendas, clubes).

El objetivo único de la página es que un dueño de negocio escriba por WhatsApp
pidiendo presupuesto. Toda decisión debe evaluarse contra eso.

## Audiencia

Dueños de negocio de 35-60 años, poco técnicos, mirando desde el móvil, a veces con
mala cobertura. **No son desarrolladores.** Nunca uses jerga técnica en el texto visible:
"zona privada" no, "acceso para clientes" sí. "SEO" no, "salir en Google Maps" sí.

## Stack y restricciones

- **HTML + CSS + JavaScript vanilla. Un solo archivo: `index.html`.**
- Sin frameworks, sin build, sin npm, sin dependencias.
- Única dependencia externa: Google Fonts (Bricolage Grotesque, Karla, IBM Plex Mono).
- **No uses `localStorage` ni `sessionStorage`.**
- No añadas librerías. Si algo necesita una librería, propón la alternativa vanilla.

## Sistema de diseño

Colores definidos como custom properties en `:root`. **Nunca escribas un color literal
en una regla nueva** — usa siempre las variables o `color-mix()`.

| Token | Valor | Uso |
|---|---|---|
| `--albero` | `#E8A33D` | Acento principal, CTAs, precios |
| `--barro` | `#C1502E` | Acento secundario, estados negativos |
| `--pino` | `#1F6F62` | Acento terciario, estados positivos |
| `--bg` / `--surface` / `--surface-2` | según tema | Fondos |
| `--line` | según tema | Bordes |
| `--text` / `--muted` | según tema | Texto |

**Tema claro y oscuro:** todo cambio de color debe funcionar en ambos. Se conmuta con
`data-theme` en `<html>`. Compruébalo siempre en los dos.

Tipografía: Bricolage Grotesque (titulares, `font-weight:800`), Karla (cuerpo),
IBM Plex Mono (etiquetas, en mayúsculas con `letter-spacing`).

## Reglas no negociables

1. **Responsive primero.** Se rompe a 900px y a 600px. Todo debe verse bien en 375px.
2. **Accesibilidad.** `aria-pressed` en botones de estado, `aria-label` en botones
   sin texto, `:focus-visible` visible, y respetar `prefers-reduced-motion`.
3. **Rendimiento.** Cero dependencias nuevas. Las animaciones, con `transform` y
   `opacity`, nunca con propiedades que provoquen reflow.
4. **Nada de efectos por lucirse.** Sin partículas, sin cursor personalizado, sin
   preloader. Cada elemento tiene que ayudar a convertir.

## Estructura de la página

```
Hero → Servicios → Estimador de precio → Trabajos → Escaparate → Proceso → Contacto
```

- **Estimador**: calcula una horquilla según tipo de web + extras. Base de cálculo:
  45 €/hora. Precios actuales: una página 950 €, 4-6 páginas 1.600 €,
  acceso para clientes 2.000 €. Mantenimiento 40 €/mes.
- **Escaparate**: seis componentes interactivos reales (galería, antes/después,
  carta desplegable, abierto ahora, contadores, reservas). Cada uno con un botón
  que abre WhatsApp con el mensaje ya escrito. **Es la sección que más convierte:
  al añadir componentes nuevos, sigue exactamente ese patrón.**

## Archivos

```
index.html      Todo: HTML + CSS + JS
.htaccess       HTTPS forzado, CSP, cabeceras de seguridad, caché
favicon.svg     Icono
robots.txt      Indexación
sitemap.xml     Mapa del sitio
```

## Despliegue

GitHub → Hostinger vía Git.

```bash
# local: commit y push
# servidor:
ssh -p 65002 usuario@servidor
cd domains/pabloblazquez.es/public_html
git pull
```

**Nunca edites archivos directamente en el servidor.** La única fuente de verdad es
el repositorio.

## Pendientes conocidos

- [ ] Sustituir `34600000000` por el número real de WhatsApp (aparece 3 veces;
      la del JSON-LD lleva `+` delante)
- [ ] Añadir capturas reales de lepetitmonde.net y clubhipicoantequera.blog
      en las tarjetas de Trabajos
- [ ] Páginas legales: `aviso-legal.html`, `privacidad.html`, `cookies.html`
      (los enlaces del footer apuntan a `#`)
- [ ] Activar HSTS en `.htaccess` cuando el SSL esté emitido (está comentado)
- [ ] Añadir sección "quién soy" con foto real
- [ ] Reseñas de los dos clientes actuales

## Cómo quiero que trabajes

- Cambios pequeños y revisables. Nada de reescribir el archivo entero.
- Explícame el porqué de cada decisión, no solo el qué.
- Si algo que te pido perjudica la conversión, el rendimiento o la accesibilidad,
  **dímelo antes de hacerlo**.
- No inventes datos: ni clientes, ni cifras, ni reseñas, ni testimonios.
- Nunca escribas credenciales, tokens ni contraseñas en ningún archivo del repo.
