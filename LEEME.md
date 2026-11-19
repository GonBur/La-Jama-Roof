# La Jama Roof Garden — Sitio web

Sitio estático (HTML + CSS + JavaScript, sin compilación ni Node.js). Listo para `public_html` de Hostinger.

## Publicar en Hostinger
1. hPanel → **Archivos → Administrador de archivos** → abre `public_html`.
2. Sube el ZIP `la-jama-web.zip` y usa **Extraer** (o sube el contenido de la carpeta).
3. Verifica que `index.html` y `.htaccess` queden directamente dentro de `public_html`.
4. Si tu dominio tiene SSL, descomenta el bloque "HTTPS redirect" en `.htaccess`.
5. Tras cada cambio, sube la fecha de `?v=20261119` en `index.html` (evita caché antigua).

## Actualizar contenido (solo `assets/js/data.js`)
- **Carta y precios:** lista `menu`. `price: 25` muestra "S/ 25"; `price: null` muestra "Consultar". `featured: true` lo lleva a *Especialidades*.
- **Fotos:** guarda la foto en `assets/img/` (ideal .webp, mín. 800×800 px) y cambia `img`.
- **Promociones vigentes:** lista `promos` (con `until: 'AAAA-MM-DD'` se ocultan solas al vencer).
- **Horario, teléfono, WhatsApp, redes:** bloques `business` y `social`.
- **Galería y publicaciones:** listas `gallery` y `posts`.

## Fuentes de las fotografías
18 fotos + logo, todas de La Jama (archivos del cliente tomados de sus redes oficiales). Se usan las versiones mejoradas por el cliente (reducción de ruido, contraste, Lanczos 4×, enfoque suave; 824×824 px), exportadas a WebP en 824 px y 480 px (`srcset`). Sin bancos de imágenes ni IA. Detalle por archivo: `FOTOS-FUENTES.json`.

## Investigación (fuentes verificadas)
- Instagram oficial @lajamaroofgarden — bio: "las maaaas ricas alitas de sullana".
- TikTok @lajamaroofgarden — video: "de miércoles a lunes desde las 7pm hasta las 11y30pm 949491220".
- Facebook "La Jama" — dirección "López Albújar mz p lote 9 2da etapa", +51 949 491 220, menciona "Visítanos o Delivery".
- Facebook "La jama food truck" (enlace del cliente) — "Volvieron nuestras costillitas".
- Google Maps y las páginas de redes no se pudieron abrir directamente desde el entorno (bloqueo de acceso). No se encontraron reseñas verificables: no se publican reseñas ni valoraciones.

## Pendiente de confirmar con el cliente
1. **Horario:** informacion.txt dice 6:30 p. m.; TikTok dice 7:00 p. m. El sitio usa 6:30 (dato del cliente).
2. **Dominio:** envíalo y se activan canonical, og:url, imagen social absoluta, sitemap.xml y robots.txt (script `set_domain.py` listo).
3. Que el 949 491 220 tenga **WhatsApp**.
4. **Delivery:** Facebook lo menciona, sin fecha. El sitio ofrece solo "Consultar pedido".
5. **Precios** (solo Mollejitas S/ 10, flyer sin fecha) y **carta completa** (Facebook indica que la envían por interno). También hay hashtags de *boba tea* sin foto.
6. Nombres exactos: Costillitas, Refresco de sandía, Coronarita.
7. **Coordenadas** verificadas para el Schema (no se incluyeron).
8. **Fotos originales en alta resolución:** las 824 px son ampliaciones de 206 px; con originales grandes el hero puede ir a pantalla completa.
9. Historia del local para *Nosotros*.

## Técnico
- Hero: foto real con revelado por máscara, Ken Burns, polaroids con profundidad y sello "Las más ricas alitas de Sullana" (bio oficial).
- GSAP 3.12.5 + ScrollTrigger desde jsDelivr. Si no cargan, el sitio funciona igual con IntersectionObserver + CSS.
- Respeta `prefers-reduced-motion` (apaga parallax, fijado horizontal, marquesina y revelados grandes).
- Reservas: el formulario arma el mensaje y abre WhatsApp; no confirma reservas automáticamente.
