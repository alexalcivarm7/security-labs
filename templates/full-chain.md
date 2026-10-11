---
titulo: Nombre de la sala
plataforma: TryHackMe
tipo: box              # guided-room | challenge | box
categoria: full-chain
dificultad: easy       # easy | medium | hard
fecha: YYYY-MM-DD
herramientas: [nmap, gobuster, burpsuite]
mitre: [T1595, T1190, T1068]
estado: completado
---

# Título del laboratorio

> Máquina completa: del reconocimiento al control total. Elimina las secciones que no apliquen.

## Resumen ejecutivo

<!-- 1 a 3 líneas: objetivo del lab, cadena de ataque y resultado. -->

## Objetivos de aprendizaje

* Objetivo 1
* Objetivo 2

## Entorno

* Máquina atacante: (ej. Kali Linux, AttackBox)
* Objetivo: (SO, servicios principales)
* Requisitos previos: (credenciales iniciales, VPN, puertos accesibles)

---

## Enumeración

### Puertos y servicios

```bash
nmap -sC -sV -p- <IP>
```

<!-- Pega solo la salida relevante. -->

### Enumeración de servicios

<!-- Versiones, endpoints, banners, usuarios, recursos compartidos. -->

### Hallazgos clave

* Hallazgo 1 y por qué importa

---

## Explotación (acceso inicial)

1. **Paso 1:** comando o herramienta, y por qué lo elegí
2. **Paso 2:** comando o herramienta, y por qué lo elegí

```bash
# comando exacto
```

**Evidencia:** `screenshots/01-acceso-inicial.png`

---

## Post-explotación

### Escalada de privilegios

* Vector identificado:
* Cómo lo detecté:
* Explotación:

```bash
# comando exacto
```

### Movimiento lateral (si aplica)

<!-- Herramientas y vectores usados (SMB, WMI, RDP, SSH, etc.). -->

### Recolección de información (si aplica)

<!-- Hashes, tokens, archivos relevantes. Censura todo dato sensible. -->

---

## Persistencia y evasión (si aplica)

<!-- Elimina esta sección si no la usaste. -->

## Exfiltración (si aplica)

<!-- Elimina esta sección si no la usaste. -->

---

## Qué intenté y no funcionó

* Intento 1: qué probé, por qué falló y qué aprendí
* Intento 2:

## Detección

¿Cómo se habría visto este ataque desde el lado defensivo?

* **Logs / eventos que lo delatan:**
* **Indicadores (IOCs):**
* **Regla o consulta de detección:** (Sigma, Wazuh, SIEM)

## Mapeo a MITRE ATT&CK

| ID | Técnica | Cómo se aplicó |
|---|---|---|
| T1190 | Exploit Public-Facing Application | Descripción corta |

## Mitigaciones y recomendaciones

| Mitigación | Prioridad |
|---|---|
| Cambio de configuración o control | Alta / Media / Baja |

## Lecciones aprendidas y próximos pasos

* Qué funcionó:
* Qué mejoraría en mi proceso:
* Siguientes salas recomendadas:

## Artefactos

* Capturas: `screenshots/`
* Scripts propios: `../../scripts/` (si aplica)
* Flags: `THM{REDACTED}`
