# Imágenes del mockup

Todas las imágenes están **referenciadas** en el código pero **no incluidas** (salvo los
logos). Mientras un archivo no exista, la página muestra un bloque de relleno con
degradado verde y un ícono — el mockup nunca se ve "roto".

Colocá cada archivo en la ruta exacta indicada abajo, respetando el nombre. No hay
que tocar código: las páginas lo toman solo.

---

## 1. Logos — ✅ ya incluidos

| Archivo | Uso | Origen |
|---|---|---|
| `assets/logos/logo-blanco.png` | Navbar y footer (fondo azul marino) | Copiado de la skill municipal |
| `assets/logos/logo-color.png` | Disponible para fondos claros | Copiado de la skill municipal |
| `assets/logos/logo-azul.png` | Disponible para fondos muy claros | Copiado de la skill municipal |

Si la Dirección de Modernización tiene una versión más nueva del logo, reemplazá el archivo con el mismo nombre.

---

## 2. Portada (hero)

| Archivo | Medida sugerida | Formato | Contenido | `alt` |
|---|---|---|---|---|
| `assets/img/hero/hero-espacios-verdes.jpg` | 1920 × 1080 px (apaisada, se recorta a lo ancho) | JPG optimizado (< 400 KB) | Vista amplia de una plaza o parque de Catamarca con gente, arbolado y cielo. Que "respire" verde. | Decorativa (va como fondo, no necesita alt) |

> El texto del hero va en blanco sobre una capa oscura. Elegí una foto sin zonas
> muy claras en el centro-izquierda para que el título se lea bien.

---

## 3. Foto principal de cada plaza

Se usa en **dos lugares**: la tarjeta de la grilla (recorte 4:3) y la cabecera de la
ficha de detalle (apaisada). Subí una sola imagen por plaza, en **4:3 y buena resolución**.

- Ruta: `assets/img/plazas/plaza-<slug>.jpg`
- Medida sugerida: **1600 × 1200 px**, JPG < 500 KB
- Contenido: vista general representativa de la plaza (día, con vegetación visible)

| Plaza | Archivo a subir |
|---|---|
| Plaza 25 de Mayo | `assets/img/plazas/plaza-25-de-mayo.jpg` |
| Plaza Virgen del Valle | `assets/img/plazas/plaza-virgen-del-valle.jpg` |
| Plaza San Martín | `assets/img/plazas/plaza-san-martin.jpg` |
| Paseo de la Alameda | `assets/img/plazas/plaza-la-alameda.jpg` |
| Parque Adán Quiroga | `assets/img/plazas/plaza-adan-quiroga.jpg` |
| Plaza Cristo Rey | `assets/img/plazas/plaza-cristo-rey.jpg` |
| Plaza Fray Mamerto Esquiú | `assets/img/plazas/plaza-fray-mamerto-esquiu.jpg` |
| Plaza del Maestro | `assets/img/plazas/plaza-del-maestro.jpg` |
| Plaza Juan Chelemín | `assets/img/plazas/plaza-juan-chelemin.jpg` |
| Plaza Sarmiento | `assets/img/plazas/plaza-sarmiento.jpg` |

> El listado de plazas es **de ejemplo**. Cuando llegue el listado oficial (MD),
> se ajustan los `slug` en `index.html` y `plaza.html`, y estos nombres de archivo
> cambian en consecuencia.

---

## 4. Galería de cada plaza (ficha de detalle)

- Ruta: `assets/img/plazas/galeria/plaza-<slug>-<n>.jpg`  (n = 1, 2, 3)
- Medida sugerida: **1200 × 900 px**, JPG < 400 KB
- 3 imágenes por plaza (se puede cambiar la cantidad en `PLAZAS_DETALLE[...].galeria`)

Ejemplo para Plaza 25 de Mayo:
```
assets/img/plazas/galeria/plaza-25-de-mayo-1.jpg
assets/img/plazas/galeria/plaza-25-de-mayo-2.jpg
assets/img/plazas/galeria/plaza-25-de-mayo-3.jpg
```
…y lo mismo para cada slug de la tabla anterior.

---

## 5. Mapa de ubicación (opcional)

- Ruta: `assets/img/plazas/mapa-<slug>.png`
- Medida sugerida: **1600 × 700 px**
- Captura estática del mapa con el punto de la plaza marcado.
- Si no se sube, la ficha muestra un recuadro "Espacio para el mapa". Alternativa
  futura: reemplazar el bloque por un `<iframe>` de mapa embebido.

---

## Checklist de carga

- [ ] `hero-espacios-verdes.jpg`
- [ ] 10 fotos `plaza-<slug>.jpg`
- [ ] 30 fotos de galería `galeria/plaza-<slug>-<n>.jpg`
- [ ] 10 mapas `mapa-<slug>.png` (opcional)

## Recomendaciones generales

- Formato **JPG** para fotos, **PNG** para mapas/gráficos.
- Comprimir antes de subir (TinyPNG, Squoosh). Objetivo: cada foto < 500 KB.
- Derechos: usar fotos propias de la Municipalidad o con licencia libre.
- Nombres **en minúscula, sin tildes ni espacios** (usar guiones).
