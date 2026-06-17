# Landing: Show de Tango no Café Tortoni (PT-BR)

Implementar la landing en `/pt/show-de-tango-cafe-tortoni` aplicando el Design System oficial de Sensaciones de Tango (oscuro, dramático, ámbar/rojo pasión, romance porteño).

## 1. Design System en `src/styles.css`

Reescritura completa con tokens del PDF:

- **Colores rojos:** Pasión `#B32825`, Rojo vivo `#E11B22`, Bordó `#6E1622`, Bordó deep `#45101A`
- **Luz cálida:** Ámbar `#E0913F`, Ámbar soft `#C8772E`, Oro `#D9A441`
- **WhatsApp:** `#25D366` — exclusivo para conversión
- **Neutros:** Black `#000`, Noir `#0B0807`, Surface `#15100F`, Raised `#201817`, Press `#2C211F`
- **Texto blanco:** 100% / 82% / 58% / 34%
- **Gradientes:** spotlight, passion glow, scrim top/bottom
- **Radios:** 2 / 4 / 8 / 14 / 999
- **Sombras/glow:** elev 1-3 con glow rojo, ámbar, verde
- **Espaciado base-8:** 4, 8, 16, 24, 40, 64, 96

## 2. Tipografía (`src/routes/__root.tsx`)

Cambiar las fuentes de Google a las del DS:
- **Cormorant Garamond** — display, mayúsculas espaciadas (tracking .06em)
- **Hanken Grotesk** — cuerpo (300) y eyebrows (600, caps, tracking .34em)
- **Sacramento** — script para adornos ("show")

## 3. Ruta y SEO (`src/routes/pt.show-de-tango-cafe-tortoni.tsx`)

- `createFileRoute("/pt/show-de-tango-cafe-tortoni")`
- Meta title: `Show de Tango no Café Tortoni em Buenos Aires — Sensaciones de Tango`
- Meta description: `Viva uma noite de tango no histórico Café Tortoni, em Buenos Aires. Veja horários, localização, experiência e reserve seu show com Sensaciones de Tango.`
- og:title, og:description, og:image (tango-hero), og:url, twitter
- Canonical relativo `/pt/show-de-tango-cafe-tortoni`
- JSON-LD: `FAQPage` + `Event` con location Café Tortoni

`src/routes/index.tsx` ya redirige a la landing.

## 4. Componentes UI (todo en el route file, secciones internas)

| # | Sección | H | Contenido clave |
|---|---|---|---|
| 1 | Nav fijo dark | — | SHOW · FUNÇÕES · RESEÑAS + botón Reservar (WhatsApp verde) |
| 2 | Hero | H1 | "Show de Tango no Café Tortoni em Buenos Aires" + subtítulo voseo + 2 CTAs sobre `tango-hero.jpg` con scrim |
| 3 | Respuesta rápida | H2 | 4 micro-respuestas a intenciones de búsqueda |
| 4 | Por qué Café Tortoni | H2 | Historia + experiencia, foto `tortoni-interior.jpg` |
| 5 | Sensaciones de Tango | H2 | Baile, música, voz, bandoneón — foto `bandoneon.jpg` |
| 6 | Horários, duração, localização | H2 | Info-cards con días, duración, dirección, mapa link |
| 7 | Info para brasileiros | H2 | FAQ pequeña, atendimento PT |
| 8 | Café Tortoni de dia, tango à noite | H2 | Comparativa día/noche con `tango-couple.jpg` |
| 9 | Testimonios | H2 | 3 reseñas con badges público internacional |
| 10 | FAQ SEO | H2 | 7 preguntas en `<details>` con `FAQPage` JSON-LD |
| 11 | CTA final | H2 | "Reserve seu show de tango no Café Tortoni" + WhatsApp |
| 12 | Footer | — | Sensaciones de Tango · Av. de Mayo 825 · WhatsApp |

## 5. Reglas del DS aplicadas

- Verde SOLO en CTAs de WhatsApp (jamás decorativo)
- Sin fondos claros — todo Noir/Surface/Raised
- Botones: Conversión (verde WA), Primario (rojo Pasión), Secundario (ghost bordó), Terciario (text-only ámbar)
- Badges: Disponível (ámbar) · Últimos lugares (rojo) · Esgotado (faint)
- Imágenes con scrims y glows ámbar
- Sin ornamento vacío

## Notas técnicas

- Las 4 imágenes ya están en `src/assets/`
- Sin lógica de backend — la landing es estática con `href="https://wa.me/..."` para WhatsApp (placeholder, el número real se puede editar luego)
- TanStack Start file-based routing, sin libs nuevas

Cuando aprobes, ejecuto los cambios.
