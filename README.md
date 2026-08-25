# pabloblazquez.es

Web personal y de negocio de **Pablo Blázquez Campos** — desarrollo web a medida para
pequeños negocios de Antequera y provincia de Málaga.

🔗 https://pabloblazquez.es

## Qué es

Landing page de una sola página, sin frameworks ni dependencias de build.
Incluye un **estimador de presupuesto interactivo** que calcula la horquilla de precio
según el tipo de web y los extras seleccionados.

## Stack

- HTML5 semántico
- CSS moderno: custom properties, `clamp()`, `color-mix()`, grid
- JavaScript vanilla (sin librerías)
- Google Fonts: Bricolage Grotesque · Karla · IBM Plex Mono

## Características

- Tema claro/oscuro conmutable
- Responsive de 320px a 4K
- Animaciones al hacer scroll con `IntersectionObserver`
- Botón flotante de WhatsApp con mensaje predefinido
- Estimador de presupuesto en tiempo real
- SEO completo: canonical, Open Graph, JSON-LD `ProfessionalService`, sitemap
- Accesibilidad: `aria-pressed`, `:focus-visible`, `prefers-reduced-motion`
- Cero dependencias, cero build, cero JavaScript de terceros

## Despliegue

Alojado en Hostinger. Despliegue por Git:

```bash
ssh -p 65002 usuario@servidor
cd domains/pabloblazquez.es/public_html
git pull origin main
```

## Estructura

```
index.html      Página completa (HTML + CSS + JS en un solo archivo)
.htaccess       HTTPS forzado, compresión, caché, cabeceras de seguridad
favicon.svg     Icono
robots.txt      Indexación
sitemap.xml     Mapa del sitio
```
