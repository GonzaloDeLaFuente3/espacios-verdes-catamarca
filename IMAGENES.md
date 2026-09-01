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
| Paseo de la Alameda | `assets/img/plazas/plaza-la-alameda.jpg` |
| Parque Adán Quiroga | `assets/img/plazas/plaza-adan-quiroga.jpg` |
| Plaza del Maestro | `assets/img/plazas/plaza-del-maestro.jpg` |

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

## 4b. Fotos históricas de cada plaza (sección "Historia")

La ficha de plaza muestra **2 fotos históricas** debajo del texto de "Historia".
Se hacen clic para ampliar (mismo visor que la galería).

- Ruta: `assets/img/plazas/historicas/plaza-<slug>-h<n>.jpg`  (n = 1, 2)
- Medida sugerida: **1200 × 900 px**, JPG < 400 KB
- Contenido: imagen de archivo / postal antigua de la plaza. El epígrafe (año y
  descripción) se edita por plaza en `PLAZAS_DETALLE[...].historicas[n].cap`.

```
assets/img/plazas/historicas/plaza-25-de-mayo-h1.jpg
assets/img/plazas/historicas/plaza-25-de-mayo-h2.jpg
assets/img/plazas/historicas/plaza-virgen-del-valle-h1.jpg
assets/img/plazas/historicas/plaza-virgen-del-valle-h2.jpg
assets/img/plazas/historicas/plaza-la-alameda-h1.jpg
assets/img/plazas/historicas/plaza-la-alameda-h2.jpg
assets/img/plazas/historicas/plaza-adan-quiroga-h1.jpg
assets/img/plazas/historicas/plaza-adan-quiroga-h2.jpg
assets/img/plazas/historicas/plaza-del-maestro-h1.jpg
assets/img/plazas/historicas/plaza-del-maestro-h2.jpg
```

> Los epígrafes cargados son **de ejemplo** para el mockup. Reemplazar por datos
> reales cuando llegue el material de archivo.

---

## 5. Mapa de ubicación (opcional)

La ficha de plaza (`plaza.html`) muestra el mapa en la sección **"Cómo llegar"**,
con un mapa embebido + un botón **"Abrir en Google Maps"**. Se configura por plaza,
en `PLAZAS_DETALLE`, con cualquiera de estos campos (en orden de prioridad):

### a) `coords` — recomendado, lo más simple

Una sola línea. Genera el mapa embebido **y** hace que "Abrir en Google Maps" caiga
en el punto exacto.

```js
"25-de-mayo": {
  …,
  coords: "-28.469257,-65.780347"   // "latitud,longitud"
},
```

Cómo obtener las coordenadas: en Google Maps, **clic derecho sobre el punto → copiar
las coordenadas** (o clic izquierdo y se ven abajo).

### b) `mapaEmbed` — para un embed específico

URL del `src` de "Insertar un mapa" de Google, la de OpenStreetMap, o el `<iframe>`
entero pegado tal cual (en ese caso, entre backticks `` ` `` en vez de comillas).
Las coordenadas para el botón se extraen solas de ese embed.

- **Google**: buscá la plaza → **Compartir → "Insertar un mapa"** → copiá lo que está
  entre comillas después de `src="…"`.
- **OpenStreetMap** (sin cuenta): openstreetmap.org → **Compartir → "HTML"** → copiá el `src`.

### c) Imagen estática

- Ruta: `assets/img/plazas/mapa-<slug>.png` · Medida sugerida **1600 × 700 px**.
- Captura del mapa con el punto marcado. Se usa solo si no hay `coords` ni `mapaEmbed`.

### d) Nada

Recuadro con la instrucción. El botón "Abrir en Google Maps" igual funciona: busca
por **nombre** de la plaza + "San Fernando del Valle de Catamarca".

---

## Checklist de carga

- [ ] `hero-espacios-verdes.jpg`
- [ ] 5 fotos `plaza-<slug>.jpg`
- [ ] 15 fotos de galería `galeria/plaza-<slug>-<n>.jpg`
- [ ] 10 fotos históricas `historicas/plaza-<slug>-h<n>.jpg`
- [ ] 5 mapas `mapa-<slug>.png` (opcional)

## Recomendaciones generales

- Formato **JPG** para fotos, **PNG** para mapas/gráficos.
- Comprimir antes de subir (TinyPNG, Squoosh). Objetivo: cada foto < 500 KB.
- Derechos: usar fotos propias de la Municipalidad o con licencia libre.
- Nombres **en minúscula, sin tildes ni espacios** (usar guiones).
