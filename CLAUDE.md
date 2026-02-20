# Proyecto: Presentaciones de Economía — Felipe Venancio

## Quién es Felipe
- Docente de Economía en universidad (Ciencia Política + Diseño Gráfico/Industrial)
- CEO de VetaCap (https://vetacap.com.ar/), un ALyC
- Estilo Ted Talk: descontracturado, conceptual, con rigor epistemológico y científico
- Explica papers complejos con ejemplos didácticos, referencias a películas/series norteamericanas
- Máxima: "Si verdaderamente entendés algo, por más complejo que sea, tiene que haber una forma simple y concreta de explicarlo"

## Objetivo
Crear presentaciones HTML para clases de economía, publicadas en GitHub Pages. Las presentaciones son standalone (un solo archivo .html con CSS y JS embebido).

## Repositorio
- Repo: `github.com/FelipeVenancio93/clases-economia`
- URL pública: `felipevenancio93.github.io/clases-economia/`
- Directorio local: `C:/Users/felip/Desktop/Claude Docencia/`
- Cada presentación nueva se commitea, pushea, y se agrega al `index.html`

## Dos tipos de presentación

Siempre preguntar a Felipe de cuál tipo es si no lo aclara.

### Divulgación
- Público: estudiantes no-especialistas (Ciencia Política, Diseño), público general
- Tono: accesible, ejemplos cotidianos, analogías, películas/series
- Papers referenciados al pasar ("Stiglitz y Weiss explicaron que...")
- Puede llevar branding VetaCap si el tema es de mercado de capitales
- Ejemplo: `presentacion_credito_v2.html`

### Académica
- Público: estudiantes universitarios, contexto más formal
- Tono: riguroso, citas formales de papers, fórmulas cuando correspondan
- Papers referenciados con cita completa (autor, año, journal)
- Branding VetaCap o académico según el tema
- Ejemplo: `presentacion_credito_academica.html`

## Branding (preguntar si no está claro)

### Con VetaCap
- Logo VetaCap en portada: `https://vetacap.com.ar/wp-content/uploads/2024/11/cropped-Vetacap-logo-ok-1.png`
- Logo container posicionado arriba a la izquierda
- Slide final: logo grande + "Conectamos finanzas con economía real" + vetacap.com.ar
- Usar para: temas de mercado de capitales, crédito, finanzas, SGR

### Sin VetaCap (Felipe Venancio)
- Sin logo en portada
- Slide final: cierre académico con mensajes clave
- Usar para: temas de política económica general, política fiscal, comercio exterior

## Formato de input

Felipe puede enviar:

### Input detallado (.md slide por slide)
- Cada slide especificado con título, contenido, fondo, notas del orador
- Ejemplo: `Presentacion_Credito_Motor_Produccion.md`
- Seguir la estructura fielmente, mejorando la visualización

### Input libre (tema, ideas sueltas, paper)
- Felipe da el tema y/o ideas generales
- Yo estructuro las slides, busco papers relevantes, armo el guion
- Presentar la estructura propuesta antes de construir el HTML

## Línea gráfica

### Colores (CSS variables en todas las presentaciones)
```css
--azul-impulso: #1036E2;   /* Principal, títulos, acentos */
--verde-activo: #00C600;   /* Destacados, energía, bullet points */
--azul-respaldo: #021751;  /* Fondos oscuros, seriedad */
--blanco: #FFFFFF;
--negro: #000000;
--rojo-alerta: #DC2626;    /* Alertas, problemas */
--amarillo: #F59E0B;       /* Precaución */
```

### Tipografía
- Google Fonts: Albert Sans (weights 300-800)
- Fallback: -apple-system, BlinkMacSystemFont, sans-serif
- h1: ~4rem, weight 700
- h2: ~2.8rem, weight 600
- h3: ~2rem, weight 500
- Body: ~1.6rem, line-height 1.6

### Fondos de slides
- `.bg-respaldo` — Azul oscuro (#021751), texto blanco
- `.bg-impulso` — Azul principal (#1036E2), texto blanco
- `.bg-verde` — Verde activo (#00C600), texto blanco
- `.bg-blanco` — Blanco, texto azul oscuro
- `.bg-imagen` — Con imagen de fondo + gradient overlay

### Clase `.highlight`
- En fondos oscuros: color verde activo
- En fondo blanco: color azul impulso

## Componentes visuales disponibles

Usar estos componentes según el contenido de cada slide:

| Componente | Clase CSS | Uso |
|---|---|---|
| Stat boxes | `.stats-grid`, `.stat-box`, `.stat-numero`, `.stat-label` | Números de impacto (2-4 datos grandes) |
| Bar charts | `.bar-chart`, `.bar-row`, `.bar`, `.bar-label` | Comparativas (países, períodos) |
| Tablas | `<table>`, `<th>`, `<td>` | Datos estructurados |
| Flow diagrams | `.flow-diagram`, `.flow-box`, `.flow-arrow` | Procesos, cadenas causales |
| Versus | `.versus`, `.versus-center` | Comparar dos conceptos |
| Concepto box | `.concepto-box` con `<h4>` + `<p>` | Explicar 2-3 ideas en columnas |
| Problema/Solución | `.problema-box`, `.solucion-box` | Contrastar diagnóstico y respuesta |
| Blockquotes | `<blockquote>` con `<cite>` | Citas de papers/economistas |
| Cita paper | `.cita-paper` con `.titulo`, `.autores`, `.contenido` | Referencia académica formal |
| Fórmulas | `.formula`, `.formula-grande` | Expresiones matemáticas |
| Timeline | `.timeline`, `.timeline-item`, `.timeline-year` | Cronologías históricas |
| Círculo virtuoso | `.circulo`, `.circulo-item`, `.circulo-arrow` | Ciclos/feedback loops |
| SVG charts | Inline `<svg>` | Gráficos de líneas, oferta/demanda |
| Imágenes | `.bg-imagen` con gradient overlay | Slides cinematográficos |
| Actor cards | `.actor-card` con `.icono`, `<h4>`, `<p>` | Presentar actores/instituciones |
| Two/Three cols | `.two-cols`, `.three-cols` | Layouts de columnas |
| Big number | `.big-number` | Un dato enorme con impacto visual |

## Navegación (JS estándar en todas las presentaciones)

Todas las presentaciones incluyen:
- **Teclado:** ← → para navegar, Space/Enter = siguiente, Home/End, F = fullscreen
- **Touch:** Swipe izq/der (threshold 50px)
- **Click:** Mitad derecha = avanzar, mitad izquierda = retroceder
- **UI:** Counter abajo-izquierda ("X / Total"), hint abajo-derecha ("← → para navegar | F para pantalla completa")

## Responsive mobile

Todas las presentaciones llevan `@media (max-width: 768px)` con:
- Padding reducido en slides
- Font-sizes escalados proporcionalmente
- Grids colapsados a una columna
- Stat numbers y chart elements reducidos
- NO alterar la visualización desktop (solo agregar, nunca sobreescribir)

## Workflow paso a paso

### Paso 1: Recibir el input
- Felipe pasa un .md detallado O ideas sueltas + tema
- Si no aclara el tipo (divulgación/académica), preguntar
- Si no aclara el branding (VetaCap/Felipe Venancio), preguntar

### Paso 1.5: Validación previa (OBLIGATORIO)
Antes de construir el HTML, SIEMPRE presentar a Felipe:
1. **Punteo de slides:** título + una línea de contenido por cada slide propuesto
2. **Listado de papers académicos citados:** autor, año, título, y una línea explicando la idea que se usa del paper
3. Esperar aprobación o comentarios de Felipe
4. Recién después de la validación, construir el HTML

### Paso 2: Construir el HTML
- Archivo standalone: un solo `.html` con `<style>` y `<script>` embebidos
- Nombrar: `presentacion_[tema].html` (snake_case, sin tildes)
- Seguir la línea gráfica y componentes documentados arriba
- Variar los fondos de slides para ritmo visual (no más de 3 slides seguidos del mismo fondo)
- Agregar responsive mobile

### Paso 3: Actualizar index.html
- Agregar la nueva presentación al `index.html` en la sección que corresponda
- Secciones existentes: "Mercado de Capitales y Crédito" y "Política Económica"
- Crear nueva sección si el tema no encaja en las existentes
- Badge "Nuevo" en la card

### Paso 4: Deploy
- `git add` los archivos nuevos/modificados
- `git commit` con mensaje descriptivo
- `git push` al repositorio
- Verificar que la URL funcione

### Paso 5: Iteración
- Felipe revisa la presentación en el navegador
- Ajustes de contenido, visuales, orden de slides
- Cada ajuste se commitea y pushea

## Presentaciones existentes (referencia)

| Archivo | Slides | Tipo | Branding | Tema |
|---|---|---|---|---|
| `presentacion_credito_v2.html` | 31 | Divulgación | VetaCap | El crédito como motor productivo |
| `presentacion_credito_academica.html` | 31 | Académica | VetaCap | El crédito (versión con papers) |
| `presentacion_sgr_deuda_pyme.html` | 27 | Divulgación | VetaCap | SGR y financiamiento PyME |
| `presentacion_politica_fiscal.html` | 75 | Académica | Felipe | Política fiscal argentina (con anexo de 4 papers) |
| `presentacion_coordinacion_fiscal_monetaria.html` | 51 | Académica | Felipe | Coordinación fiscal y monetaria (con anexo de 6 papers) |
| `presentacion_comercio_exterior.html` | 82 | Académica | Felipe | Comercio internacional (con anexo de 8 papers) |
| `presentacion_mercado_cambios.html` | 74 | Académica | Felipe | Mercado de cambios (con anexo de 7 papers) |
| `presentacion_politica_monetaria.html` | 82 | Académica | Felipe | Política monetaria (con anexo de 7 papers) |

## Imágenes locales en el repo
- `good_bad_ugly_poster.jpg` — El Bueno, el Malo y el Feo
- `michael_k_williams.jpg` — Omar (The Wire)
- `sarmiento.jpg` — Domingo F. Sarmiento
- `trump_liberation_day.jpg.webp` — Trump Liberation Day
- `img_monumental.jpg` — Estadio Monumental (River)
- `Clint_Eastwood_-_1960s.jpg` — Clint Eastwood

## Notas técnicas
- El repo es GitHub Pages (rama main, root como source)
- Las imágenes se referencian con path relativo (mismo directorio)
- Google Fonts se carga via CDN (Albert Sans)
- Logo VetaCap se carga desde vetacap.com.ar (CDN)
- Todas las presentaciones son ~1000-2500 líneas de HTML
- El JS de navegación es prácticamente idéntico en todas (copiar de cualquier existente)
