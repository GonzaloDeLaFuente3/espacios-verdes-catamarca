# Mapa de contenidos: MD → dónde va en el código

Este archivo registra **qué archivo MD llena qué parte del mockup**. A medida que
pasás cada MD, se reemplaza el contenido de ejemplo (marcado en el código con
`═══ EJEMPLO — reemplazar … ═══`) y se tilda acá.

| # | MD que aportás | Archivo a editar | Qué reemplaza | Estado |
|---|---|---|---|---|
| 1 | Conceptos de espacios verdes | `index.html` | Bloque HTML dentro de `<section id="conceptos">` (entre `Contenido: MD "Conceptos..."` y `FIN CONTENIDO`) | ✅ Hecho (`conceptos_espacios_verdes.md`, Mayo 2026) |
| 2 | Listado oficial de plazas (nombre, barrio, resumen) | `index.html` | Array `const PLAZAS = [...]` | ⬜ Pendiente |
| 3 | Ficha de cada plaza (historia, año, superficie, equipamiento, arbolado, cómo llegar) | `plaza.html` | Objeto `const PLAZAS_DETALLE = {...}` y el array `const PLAZAS = [...]` (orden = anterior/siguiente) | ⬜ Pendiente |
| 4 | Preguntas del quiz | `index.html` | Array `const JUEGOS = { quiz: [...] }` | 🟡 Parcial (nivel `grandes` cargado, BLOQUES 1-3; falta nivel `chicos`) |
| 5 | Imágenes | (sin código) | Ver `IMAGENES.md` | ⬜ Pendiente |
| 6 | Clasificación de calidad (★ a ★★★★★) + advertencias + impulsos | `index.html` | `<section id="calidad">` (contenido estático, sin marca de EJEMPLO) | ✅ Hecho (texto "Individualización / Regla de asignación", Ago 2026) |

---

## Formato sugerido para cada MD

### 1. Conceptos
Texto libre con títulos. Si respetás esta estructura, la integración es directa:
- Introducción (1 párrafo)
- Tipos de espacio verde (nombre + 1-2 líneas cada uno)
- Beneficios: Ambientales / Sociales / Salud (viñetas)
- Rol de la ciudadanía (viñetas)
- Glosario (término + definición)
- Dato destacado (una cifra + fuente)

### 2. Listado de plazas
Una fila por plaza:
```
nombre | barrio | resumen corto (1 oración)
```
El `slug` (para URL y nombre de imagen) se genera del nombre: minúsculas, sin
tildes, con guiones. Ej.: "Plaza 25 de Mayo" → `25-de-mayo`.

### 3. Ficha por plaza
Por cada plaza:
```
nombre:
barrio:
año:
superficie:
introducción: (1 párrafo)
historia: (1-3 párrafos)
equipamiento: (lista)
arbolado: (lista de especies)
accesibilidad: (1 oración)
dirección / cómo llegar:
cantidad de fotos de galería: (por defecto 3)
```

### 4. Preguntas del quiz
La Sección 3 es **un solo quiz** de opción múltiple, con dos niveles (`chicos` y
`grandes`). Formato por pregunta:
```
Nivel: chicos | grandes
Pregunta:
a) opción   b) opción   c) opción   d) opción
Correcta: b
Explicación: ...
```
El motor mezcla al azar, en cada partida, el orden de las preguntas y el de las
opciones (la respuesta correcta no queda fija en una letra). Se juegan 5
preguntas por partida tomadas al azar del nivel elegido.

Ya está cargado el nivel `grandes` (16 preguntas, BLOQUES 1-3). Falta el nivel
`chicos` (hoy hay 5 de ejemplo marcadas `═══ EJEMPLO ═══`).
