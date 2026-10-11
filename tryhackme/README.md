# TryHackMe

Índice de las salas, retos y máquinas de [TryHackMe](https://tryhackme.com/p/alexalcivarm7) que he documentado en este repositorio.

← [Volver al README principal](../README.md)

---

## Cómo está organizado

Cada sala vive en su propia carpeta, con su `README.md` y sus capturas:

```
tryhackme/
├── README.md                ← este índice
└── nombre-de-la-sala/
    ├── README.md            ← el writeup (usa una plantilla de /templates)
    └── screenshots/
```

El nombre de la carpeta va en minúsculas y con guiones, igual que el slug de la sala (por ejemplo `detecting-web-ddos`).

## Índice por fecha

| Fecha | Sala | Tipo | Categoría | Dificultad | Técnicas (MITRE) | Estado |
|---|---|---|---|---|---|---|
| 2026-10-11 | W1seGuy | challenge | crypto | easy | N/A | completado |

<!-- > Reemplaza la fila de ejemplo por tus salas reales y añade una fila nueva por cada writeup, la más reciente arriba. -->

## Índice por categoría

Cuando haya varios writeups, agrúpalos aquí para encontrarlos rápido.

**Crypto y decodificación**

* *[W1seGuy](w1seguy/README.md)*

**Web y red**

* *(aún sin writeups)*

**Escalada de privilegios y máquinas completas**

* *(aún sin writeups)*

**Blue team (detección y respuesta)**

* *(aún sin writeups)*

---

## Plantillas

| Tipo de ejercicio | Plantilla |
|---|---|
| Máquina completa | [`full-chain`](../templates/full-chain.md) |
| Cripto, decodificación, técnica puntual | [`single-skill`](../templates/single-skill.md) |
| Detección y respuesta | [`blue-team`](../templates/blue-team.md) |

<!--
## Cómo añadir una sala nueva

1. Crea la carpeta `tryhackme/<slug-de-la-sala>/` con una subcarpeta `screenshots/`.
2. Copia la plantilla que corresponda desde `templates/` como `README.md` de esa carpeta.
3. Rellena los metadatos del inicio y elimina las secciones que no apliquen.
4. Censura flags, contraseñas y hashes, y repasa la lista de revisión de [`docs/ethics-scope.md`](../docs/ethics-scope.md).
5. Añade la fila en la tabla de este índice y, si es de las mejores, en "Writeups destacados" del README principal.
-->
