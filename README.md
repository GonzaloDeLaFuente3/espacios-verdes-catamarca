# Espacios Verdes y Plazas — Catamarca Capital (mockup)

Prototipo navegable de una página pública sobre los espacios verdes de San Fernando
del Valle de Catamarca. Tres secciones en una sola página:

1. **Conceptos** — qué son los espacios verdes y por qué importan.
2. **Plazas** — grilla de todas las plazas; cada tarjeta lleva a su ficha.
3. **Jugá y aprendé** — cuatro juegos didácticos que repasan los conceptos.

Es un **mockup**: sin backend, con contenido de ejemplo y sin las imágenes finales.
Sirve para validar diseño y flujo antes de programarlo en el stack definitivo.

---

## Cómo verlo

Abrí **`index.html`** en el navegador (doble clic alcanza).

> Para que la navegación a las fichas de plaza (`plaza.html?plaza=…`) funcione bien,
> conviene servir la carpeta con un servidor local en vez de abrir el archivo suelto:
>
> ```
> # con Python instalado, desde esta carpeta:
> python -m http.server 8000
> # luego abrir http://localhost:8000
> ```
> Con VS Code: extensión **Live Server** → "Open with Live Server".

---

## Estructura

```
plazas/
  index.html      Página principal (3 secciones). CSS y JS embebidos.
  plaza.html      Ficha de plaza. Lee ?plaza=<slug>. CSS y JS embebidos.
  IMAGENES.md     Qué imágenes faltan, dónde van y con qué medidas.
  CONTENIDO.md    Qué MD reemplaza qué parte del código.
  README.md       Este archivo.
  assets/
    logos/        Logos oficiales (ya incluidos).
    img/
      hero/       Foto de portada (a cargar).
      plazas/     Foto principal por plaza + mapas (a cargar).
      plazas/galeria/  Galería por plaza (a cargar).
```

---

## Stack

- **Bootstrap 5.3.3** + **Bootstrap Icons 1.11** + tipografía **Inter**, todo por CDN
  (requiere internet la primera vez). Es lo que define la identidad visual municipal.
- CSS y JavaScript **embebidos** en cada HTML — no hay build ni dependencias locales.
- Identidad visual: skill `municipal-frontend-skill`. Método y accesibilidad: `ui-craft`.

### Nota de color (accesibilidad)

El verde institucional `#45803B` queda al límite de contraste sobre blanco (~4.7:1).
Para **texto** se usa el verde oscuro `#005151` (~8.9:1). Los verdes claros
(`#89AE24`, `#CEDD0E`) se usan solo en superficies y detalles, **nunca en texto chico**.

---

## Cómo cargar el contenido real

Ver **`CONTENIDO.md`**. Resumen:

| Contenido | Archivo | Qué se edita |
|---|---|---|
| Conceptos | `index.html` | bloque HTML dentro de `<section id="conceptos">` |
| Listado de plazas | `index.html` | array `PLAZAS` |
| Fichas de plaza | `plaza.html` | objeto `PLAZAS_DETALLE` + array `PLAZAS` |
| Preguntas de los juegos | `index.html` | objeto `JUEGOS` |
| Imágenes | — | ver `IMAGENES.md` |

### Agregar o cambiar una plaza

1. En `index.html`, sumá un objeto al array `PLAZAS` con `slug`, `nombre`, `barrio`, `resumen`.
2. En `plaza.html`, sumá el mismo `slug` al array `PLAZAS` (define el orden) y una
   entrada en `PLAZAS_DETALLE` con la ficha completa.
3. Subí las imágenes con ese `slug` según `IMAGENES.md`.

---

## Qué falta para producción

- Reemplazar todo el contenido de ejemplo por los MD oficiales.
- Cargar las imágenes (`IMAGENES.md`).
- Confirmar el listado y los datos de cada plaza con el área competente.
- Quitar la etiqueta **MOCKUP** (un `<div class="mockup-badge">` en cada HTML).
- Definir el "Cómo llegar": imagen estática de mapa o mapa embebido.
- Completar enlaces del footer (sitio oficial, reclamos, contacto) y el canal de
  reporte de desperfectos en la sección Conceptos.
- Revisión de accesibilidad sobre la versión con contenido real (`/ui-review`).
- Definir dónde se aloja y si se integra al portal municipal (la navbar hoy es autónoma).

---

## Estado

| Parte | Estado |
|---|---|
| Estructura y diseño de las 3 secciones | ✅ Listo |
| Grilla de plazas + búsqueda + animación hover | ✅ Listo (contenido de ejemplo) |
| Plantilla de ficha de plaza + estado "no encontrada" | ✅ Listo (contenido de ejemplo) |
| 4 juegos didácticos | ✅ Listo (preguntas de ejemplo) |
| Contenido real (conceptos, plazas, preguntas) | ⬜ A la espera de los MD |
| Imágenes | ⬜ A cargar |
