# Security Labs

> Laboratorios y writeups de seguridad ofensiva y defensiva.

Repositorio donde documento los laboratorios, retos y ejercicios que realizo para practicar y crecer en ciberseguridad. Cada writeup explica **qué hice, por qué lo hice y cómo se habría detectado o evitado**, no solo los comandos.

---

## Objetivo del repositorio

* Documentar mi progreso en **Red Team, pentesting y detección**.
* Demostrar habilidades prácticas con **laboratorios reproducibles**.
* Practicar la **redacción técnica profesional** en inglés y español.
* Mostrar cómo cada ataque se mapea a **MITRE ATT&CK** y cómo se detecta o se mitiga.
* Construir un portafolio sólido que respalde mi perfil profesional.

---

## Enfoque

* **Razonamiento antes que comandos:** cada writeup incluye lo que intenté y no funcionó.
* **Doble mirada:** los ejercicios ofensivos incluyen detección y mitigación (mentalidad blue team).
* **Honestidad sobre el tipo de reto:** distingo entre salas guiadas, retos tipo CTF, máquinas y ejercicios de blue team.
* **Reproducible:** comandos exactos, scripts propios en `scripts/` y evidencias dentro de cada carpeta.

---

## └─ Estructura del repositorio

```
security-labs/
│
├── README.md                → Índice principal (este documento)
├── LICENSE
│
├── docs/
│   ├── ethics-scope.md      → Alcance y ética (una sola vez)
│   ├── methodology.md       → Cómo abordo un laboratorio
│   └── cheatsheets/
│
├── templates/               → Plantillas de writeup
│   ├── full-chain.md        → Máquinas completas
│   ├── single-skill.md      → Cripto, decodificación, una técnica puntual
│   └── blue-team.md         → Detección y respuesta
│
├── tryhackme/               → Writeups de TryHackMe
│   ├── README.md            → Índice de salas completadas
│   └── nombre-de-la-sala/
│       ├── README.md
│       └── screenshots/
│
├── ctf-events/              → Eventos CTF
│
└── scripts/                 → Herramientas propias
 
```

> La categoría de cada reto (crypto, web, privesc, blue-team…) va en los metadatos del writeup y en los índices, no en subcarpetas.

---

## Qué plantilla uso

| Plantilla | Cuándo la uso | Incluye |
|---|---|---|
| [`full-chain`](templates/full-chain.md) | Máquinas completas | Enumeración, explotación, post-explotación, detección, MITRE, mitigaciones |
| [`single-skill`](templates/single-skill.md) | Cripto, decodificación, forensics, una técnica puntual | Datos conocidos, análisis, solución, script, técnica aprendida |
| [`blue-team`](templates/blue-team.md) | Detección, logs, respuesta a incidentes | Línea de tiempo, IOCs, regla de detección, contención |

---

## Tipos de reto y categorías

| Tipo | Significado |
|---|---|
| `guided-room` | Sala guiada con tareas y pistas paso a paso |
| `challenge` | Reto tipo CTF con objetivo abierto |
| `box` | Máquina completa, desde el reconocimiento hasta el control |
| `blue-team` | Ejercicio de detección, análisis de logs o respuesta a incidentes |

**Categorías:** `crypto` · `encoding` · `web` · `network` · `privesc` · `forensics` · `blue-team` · `full-chain`

<!--
---

## Writeups destacados

Los que mejor muestran mi proceso, de principio a fin.

| Writeup | Plataforma | Tipo | Categoría | Qué demuestra |
|---|---|---|---|---|
| [Nombre de la sala](tryhackme/nombre-de-la-sala/README.md) | TryHackMe | box | full-chain | Descripción breve de la habilidad demostrada |
| [Nombre de la sala](tryhackme/nombre-de-la-sala/README.md) | TryHackMe | challenge | crypto | Descripción breve de la habilidad demostrada |
| [Nombre de la sala](tryhackme/nombre-de-la-sala/README.md) | TryHackMe | blue-team | blue-team | Descripción breve de la habilidad demostrada |

## Índice completo

El listado detallado de cada plataforma está en su propio índice, por ejemplo [`tryhackme/README.md`](tryhackme/README.md).

| Fecha | Plataforma | Writeup | Tipo | Categoría | Dificultad | Técnicas (MITRE) |
|---|---|---|---|---|---|---|
| YYYY-MM-DD | TryHackMe | [Nombre](tryhackme/nombre-de-la-sala/README.md) | guided-room | web | easy | T1190 |

## Herramientas propias

| Herramienta | Descripción |
|---|---|
| [`scripts/xor-solver`](scripts/xor-solver/) | Recupera la clave de un XOR de clave repetida a partir de texto conocido (prefijo y sufijo de la flag) |
-->
---

## Notas importantes

* Nunca publico flags literales ni credenciales sensibles (uso `THM{REDACTED}`).
* Todo se hace en entornos controlados y éticos. Detalles en [`docs/ethics-scope.md`](docs/ethics-scope.md).
* Se documentan también medidas defensivas (blue team mindset).

---

## Recursos de referencia

* [MITRE ATT&CK](https://attack.mitre.org/)
* [MITRE D3FEND](https://d3fend.mitre.org/)
* [OWASP Top 10](https://owasp.org/www-project-top-ten/)
* [GTFOBins](https://gtfobins.github.io/)
* [LOLBAS](https://lolbas-project.github.io/)
* [HackTricks](https://book.hacktricks.xyz/)
* [Sigma Rules](https://github.com/SigmaHQ/sigma)
* [CyberChef](https://gchq.github.io/CyberChef/)

---

## Redes Sociales

[![LinkedIn](https://img.shields.io/badge/Linkedin-000000?style=for-the-badge&logo=linkedin&logoColor=00ff41)](https://www.linkedin.com/in/alexalcivarm7)
[![GitHub](https://img.shields.io/badge/GitHub-000000?style=for-the-badge&logo=github&logoColor=00ff41)](https://github.com/alexalcivarm7)
[![TryHackMe](https://img.shields.io/badge/Tryhackme-000000?style=for-the-badge&logo=tryhackme&logoColor=00ff41)](https://tryhackme.com/p/alexalcivarm7)

---

>  *Este portafolio es parte de mi desarrollo profesional en ciberseguridad ofensiva y defensiva.*
