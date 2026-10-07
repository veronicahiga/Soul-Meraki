# Soul Meraki — Sistema de diseño

> *Sentiments encaixats en l'exclusivitat d'un instant.* · *Sentimientos encajados en la exclusividad de un instante.*
> Regla que lo gobierna todo: cada pieza debe poder leerse en voz baja.

## Contexto

Soul Meraki es un regalo premium y muy personalizado (~300 €): una botella de vino (Josep Grau Viticultor) o aceite de autor (Aureli Mas), una vela perfumada envuelta en cuero, una carpeta de dedicatoria atada con cordón de piel y un código QR que abre una landing personal con imagen de fondo, el texto de la dedicatoria y una playlist.

Dos públicos:
- **B2B** — directores de marketing, RR. HH. y relaciones institucionales en banca privada, gestión de activos, formación premium y lujo. Ocasiones: clientes, accionistas y consejo, talento interno. Casos: MoraBanc, IESE, Bagués.
- **B2C Condolencia** — familias y amigos que envían condolencias, a través de funerarias premium.

Superficies: landing B2B · landing de condolencia B2C · landing personal del destinatario (QR) · LinkedIn (carruseles 1080×1350, imágenes 1200×1200) · impresión (carpeta y tarjetas de dedicatoria). Idiomas: catalán, español, inglés — uno por pieza.

### Fuentes recibidas
- `uploads/MERAKI_SOUL_marca.svg` — logo oficial vertical (símbolo + MERAKI / SOUL). Copiado y recoloreado en `assets/`. La versión horizontal se ha compuesto a partir de los mismos trazados (ver Logo).
- `uploads/SoulMeraki_palette.png` — hoja de color (en `assets/reference/palette-reference.png`).
- OTF de Gill Sans (Light, Light Italic, Regular, Italic, Medium, Medium Italic, Condensed, Condensed Bold) — en `fonts/`.
- Briefing de marca escrito por el cliente; este README lo recoge.
- Referencia de estructura para la landing B2B: https://www.fsqgourmet.com/ (solo estructura editorial; no se copia su identidad).
- No hay código, Figma ni web existente. Los UI kits se construyen desde el briefing.

---

## Fundamentos de contenido

**Personalidad:** poética, sobria, cálida. **No** comercial, urgente, fría-corporativa ni sentimental kitsch.

- Frases cortas. Sin signos de exclamación. Sin emoji. Mayúscula inicial solo al comienzo de frase; mayúsculas completas solo en antetítulos, etiquetas y botones Gill Sans.
- **Condolencia en segunda persona del plural**: «Acompañamos vuestro silencio.» / «Acompanyem el vostre silenci.»
- **B2B en español, trato de usted**: «Hablemos de la relación que desea cuidar.»
- **Vocabulario B2B**: *capital relacional*, memoria, reconocimiento, vínculo, gesto. Nunca «merchandising», «pack de regalo corporativo», «swag».
- Nunca descuentos, ofertas, stock, cuentas atrás, «limitado» ni comparativas de precio.
- **Precio**: B2B nunca. B2C una sola vez, con calma, sin justificarlo («300 €» + una línea de entrega).
- **CTAs** — B2B: «Solicitar propuesta» / «Sol·licitar proposta» / «Request a proposal». B2C: «Pedir para [nombre]» / «Demanar per a [nom]». Nunca «Comprar ahora», «Empezar», «Saber más», «Tienda».
- **Cifras**: solo las de la marca, p. ej. «85% más recuerdo de marca frente a los regalos tradicionales». Nunca inventar estadísticas, testimonios ni resultados.
- **Historia de la fundadora** solo donde se pida (nota de la fundadora, «Tres ànimes de Soul Meraki», un post de LinkedIn). Nunca como gancho comercial.
- Un idioma por composición, nunca mezclados.

Ejemplos:
- Hero B2B: «El gesto que se recuerda.»
- Manifiesto: «No es un regalo. Es un instante para una sola persona.»
- Condolencia: «Acompanyem el vostre silenci.»
- Confirmación: «Lo prepararemos con cuidado.»

---

## Fundamentos visuales

**Color — base neutra + UN color de sentimiento por pieza.**
- Neutros (~90%): **Blanco `#FFFFFF` (fondo por defecto)**, Marfil `#F6F3EE` (fondo alterno, como el packaging; token `--sm-paper`), Tinta `#1C1D1D` (todo el texto, logo por defecto), Tinta 70% (texto secundario), Tinta 15% (filetes).
- Familias de sentimiento (~10%), nunca más de una por página, carrusel o pieza:
  - Verde 1 `#293B38` / Verde 2 `#37534F` — Felicitación, Bienvenida, B2B por defecto.
  - Burdeos 1 `#783132` / Burdeos 2 `#91373A` — Amor.
  - Marrón 1 `#5D5049` / Marrón 2 `#796057` — Agradecimiento (cuero).
  - Condolencia — sin color de sentimiento: solo Blanco + Tinta.
- Nivel 1 es el color de trabajo (acentos, relleno del CTA, reglas, logo). Nivel 2 solo para hover/secundario dentro de la familia.
- Tintes de la hoja: Marrón 1 · 8% `#F2F1F0` y Marrón 1 · 25% `#D6D3D2` (divisores, selección).
- La familia se fija con `data-sentiment="verd|burdeus|marro|condol"` en la raíz; los componentes leen `--accent` / `--accent-hover`.
- Tokens semánticos: `--surface-page` (blanco), `--surface-alt` (marfil), `--surface-raised` (blanco), `--text-inverse` y `--on-accent` (blanco).
- **Sin degradados. Sin tintes fuera de estos valores. Sin transparencias ni desenfoques** salvo Tinta 70/15%.

**Tipografía.** Fraunces lleva la emoción; Gill Sans lleva la función.
- Fraunces Light 300 — titulares y hero (56–72px, interlineado 1.15, −0.01em). Regular 400 — texto largo y dedicatorias (18–20px, 1.6). SemiBold 600 — énfasis corto y titulares pequeños. Light Italic 300 — lemas, nombres de sentimiento, citas, nota de la fundadora.
- Titular en dos tiempos (landing B2B): línea cursiva pequeña (30px) + línea grande Light (64px). «Una caja, / cuatro gestos».
- Gill Sans Regular/Light — interfaz, navegación, etiquetas, botones, pies, notas. Medium en mayúsculas +0.15em — antetítulos y etiquetas.
- Nunca un titular en Gill Sans; nunca un formulario en Fraunces. Énfasis con peso o cursiva, nunca solo con color, nunca párrafos en negrita.

**Geometría.** Radio **0** en todo; píldoras y tarjetas redondeadas están fuera de marca (el único círculo es el punto del radio). Filetes de 1px en Tinta 15% o sentimiento-1. **Sin sombras**: la separación se hace con filetes y cambios de fondo (blanco ↔ marfil).

**Tarjetas.** Rectangulares, blancas o marfil, filete Tinta 15%, relleno 32–40px, sin sombra, sin radio, sin borde lateral de color.

**Motivos.** Regla firma: cursiva centrada entre dos reglas de 48px («—— Sentimientos ——»). Ornamento: el símbolo o la cruz de pétalos a 16–24px como divisor, máx. 3 seguidos (excepción: la banda de cruces de los posts «Motivo nº»).

**Redes sociales.** Predominan Blanco, Marfil y Marrón (`data-sentiment="marro"`). Seis plantillas: foto a sangre, palabra con inicial gigante, titular con imagen inserta, historia, playlist y «Motivo nº». Ver `ui_kits/social-media/README.md`.

**Composición.** Centrada y simétrica en momentos emocionales (hero, dedicatoria, nota de la fundadora, bloques de la landing B2B); columnas editoriales a la izquierda para texto explicativo. Medida 60–68 caracteres. Espaciado 8pt (8/16/24/32/48/64/96/128); relleno de sección 96–128px. 12 columnas, medianil 24px, máx. 1200px. Bloques partidos imagen/texto al 50% a sangre, alternando lado. El aire es el lujo: ante la duda, quitar. Cabeceras no fijas; sin chats ni pop-ups. El menú a pantalla completa de la landing B2B es navegación, no un pop-up; no se usa en condolencia.

**Secciones oscuras.** Un bloque a sangre sentimiento-1 o Tinta con texto blanco por página, como pausa. Nunca el tema por defecto.

**Imagen.** Solo producto real: caja marfil con asas de cuero, interior marrón oscuro, lacre, vela envuelta en cuero, carpeta con cordón de piel, botellas. Luz natural suave, madera cálida o piedra oscura; manos permitidas, caras rara vez. Una imagen por idea, a sangre o grande, nunca collages. Condolencia: máximo una imagen discreta de producto, sin personas. Sin stock, sin renders de IA. Hasta tener fotos, usar el marcador `Photo`.

**Movimiento.** Ninguno, o un único fundido lento (≥400ms, `ease`). Hover = cambio de nivel 1 a nivel 2 (botones) o subrayado/color en enlaces, 400ms. Sin encogimiento al pulsar, sin rebotes. Condolencia: cero animación.

**Estados.** Foco: contorno Tinta 1px, separación 3px. Deshabilitado: 40% de opacidad. Error: borde Burdeos 1 + mensaje. Áreas táctiles ≥44px.

**Accesibilidad.** WCAG AA en todo el texto. Sentimiento-1 sobre blanco: Verde ≈11:1, Burdeos ≈8.6:1, Marrón ≈7.3:1; blanco sobre sentimiento-1 cumple AA. Cuerpo ≥18px en web. Etiquetas visibles. Las páginas de condolencia deben funcionar sin JS y cargar al instante.

---

## Logo

- **Vertical (principal)** — símbolo sobre MERAKI / SOUL. Packaging, carpeta, portadas y cierres, pie web. `assets/logo-{ink,white,paper,verd,burdeus,marro}.svg` · `<Logo variant="full" />`.
- **Horizontal** — símbolo a la izquierda + MERAKI / SOUL. Cabecera web, firma de email, espacios bajos. `assets/logo-horizontal-{ink,white,verd,burdeus,marro}.svg` · `<Logo variant="horizontal" />`.
- **Símbolo** — solo como ornamento o en esquina de piezas sociales. `assets/symbol-*.svg`.
- **Color**: un solo color — Tinta por defecto, Blanco sobre pausa oscura o zona oscura de foto, o el sentimiento-1 de la pieza.
- **Tamaño mínimo**: vertical 48px / 15mm · horizontal 24px / 8mm · símbolo 16px / 5mm.
- **Área de respeto**: margen libre igual a dos veces la altura de la palabra SOUL por todos los lados.
- **Nunca**: deformar, girar, añadir sombras o efectos, colores fuera de paleta, mezclar dos sentimientos, colocar sobre fondos sin contraste, encerrar en formas, pegar al borde.

---

## Iconografía

Soul Meraki **no usa set de iconos**. El único recurso gráfico es el símbolo (copa + cruz de pétalos) como ornamento, más recursos tipográficos: filetes, numerales (01, 02…), un chevron de filete en `Select` y las dos líneas del botón Menú. Flechas de texto (←) aceptables en enlaces pequeños. Sin emoji, sin cuadrículas de iconos, sin fuentes de iconos. Si una interfaz necesita un icono utilitario (play/pausa), monolínea, ~1px, Tinta, y señalarlo: no se ha aportado ninguno.

---

## Índice

- `styles.css` — punto de entrada (solo imports) → `tokens/fonts.css`, `colors.css`, `typography.css`, `layout.css`, `base.css`
- `fonts/` — OTF de Gill Sans. Fraunces se carga desde Google Fonts (ver advertencias).
- `assets/` — logo vertical y horizontal, símbolo, cruz de pétalos, wordmark, fotos reales de producto (`assets/photos/`), referencias.
- `guidelines/` — fichas de fundamentos (Colores, Tipografía, Espaciado, Marca, Logo).
- `components/` — primitivas React, cada una con `.d.ts` + `.prompt.md` + una ficha por carpeta.
- `ui_kits/b2b-landing/` — landing B2B de captación (Verde, español, estructura editorial).
- `ui_kits/condol-landing/` — landing de condolencia + pedido (Blanco + Tinta).
- `ui_kits/recipient-landing/` — landing personal QR (cuatro variantes de sentimiento).
- `ui_kits/social-media/` — feed de redes 1080×1350 (seis plantillas de post, Blanco + Marfil + Marrón).
- `ui_kits/social-print/` — carrusel/imagen LinkedIn + carpeta y tarjeta.
- `SKILL.md` — entrada como skill de agente.

### Componentes
- brand: **Logo** (full · horizontal · symbol · wordmark · petal), **SignatureRule**, **Ornament** (symbol · petal)
- core: **Button**, **Heading**, **Eyebrow**
- forms: **TextField**, **Select**, **Checkbox**, **RadioGroup**
- content: **Section**, **Card**, **Quote**, **Dedication**, **Photo**
- media: **Playlist**
- navigation: **SiteHeader** (centered · bar), **SiteFooter**

No existía librería de componentes; este conjunto se ha creado desde el briefing. Omitidos a propósito por estar fuera de marca: Badge, Tag/Píldora, Toast, Tooltip, Diálogo/Pop-up, Switch, Tabs.

### Añadidos intencionados
- `Photo` — marcador rotulado para no recurrir nunca a imágenes de stock.
- `Playlist` — necesario para la landing personal.
- `Dedication` — la dedicatoria impresa y en landing, central en todas las superficies.

### Advertencias
- **Fraunces**: el briefing menciona los TTF de Fraunces, pero no están en el proyecto. Se carga desde Google Fonts (misma familia variable, con eje SOFT). Volver a subir los TTF para alojarla.
- **Gill Sans SemiBold/Bold/Heavy** no están; los antetítulos usan Gill Sans Medium.
- **Logo horizontal**: compuesto a partir de los trazados del logo vertical (símbolo + MERAKI / SOUL a 1.3×). Si existe una versión horizontal oficial, sustituir los archivos `logo-horizontal-*`.
- **Tamaños mínimos y área de respeto**: propuesta del sistema, pendiente de validar.
- Los ejemplos de copy de las fichas y de los kits de condolencia, QR y LinkedIn siguen en catalán, idioma de marca; la landing B2B está en español.
