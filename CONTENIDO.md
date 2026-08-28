# Mapa de contenidos: MD → dónde va en el código

Este archivo registra **qué archivo MD llena qué parte del mockup**. A medida que
pasás cada MD, se reemplaza el contenido de ejemplo (marcado en el código con
`═══ EJEMPLO — reemplazar … ═══`) y se tilda acá.

| # | MD que aportás | Archivo a editar | Qué reemplaza | Estado |
|---|---|---|---|---|
| 1 | Conceptos de espacios verdes | `index.html` | Bloque HTML dentro de `<section id="conceptos">` (entre `Contenido: MD "Conceptos..."` y `FIN CONTENIDO`) | ✅ Hecho (`conceptos_espacios_verdes.md`, Mayo 2026) |
| 2 | Listado oficial de plazas (nombre, barrio, resumen) | `index.html` | Array `const PLAZAS = [...]` | ⬜ Pendiente |
| 3 | Ficha de cada plaza (historia, año, superficie, equipamiento, arbolado, cómo llegar) | `plaza.html` | Objeto `const PLAZAS_DETALLE = {...}` y el array `const PLAZAS = [...]` (orden = anterior/siguiente) | ⬜ Pendiente |
| 4 | Banco de preguntas de los juegos | `index.html` | Objeto `const JUEGOS = { quiz, vf, pares }` | ⬜ Pendiente |
| 5 | Imágenes | (sin código) | Ver `IMAGENES.md` | ⬜ Pendiente |

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

### 4. Banco de preguntas
Cualquier formato claro sirve. El ideal:
```
[QUIZ]
Pregunta:
a) opción   b) opción   c) opción   d) opción
Correcta: b
Explicación: ...

[VERDADERO/FALSO]
Afirmación:
Respuesta: Verdadero | Falso
Explicación: ...

[UNIR]
Término = Definición
```
Con eso se arman los 4 juegos (el de "¿Reconocés la plaza?" se genera solo con
las fotos de las plazas).
