# Metodología

Cómo abordo un laboratorio, desde que lo abro hasta que publico el writeup. El objetivo es que cada ejercicio sea **reproducible**, que mi razonamiento quede documentado y que siempre cierre con la mirada defensiva.

← [Volver al README principal](../README.md)

---

## Flujo general

```
Preparar → Reconocer → Plantear hipótesis → Probar → Escalar / profundizar → Documentar → Cerrar (detección y mitigación)
```

No es una línea recta: es normal volver a reconocer cuando una hipótesis falla. Lo importante es dejar constancia de ese ir y venir.

## 1. Preparación

* Leo el enunciado completo y anoto el objetivo, las pistas y las restricciones.
* Identifico el tipo de ejercicio (`guided-room`, `challenge`, `box`, `blue-team`) y elijo la [plantilla](../templates/) que corresponde.
* Creo la carpeta de la sala con su `screenshots/` antes de empezar.
* Abro un archivo de notas y registro **mientras trabajo**, no al final: comando, resultado y por qué lo ejecuté.

## 2. Reconocimiento y enumeración

* Empiezo amplio y luego profundizo: puertos y servicios, versiones, endpoints, usuarios, recursos expuestos.
* Anoto cada hallazgo con una línea de por qué importa.
* Reviso lo que ya tengo antes de lanzar más herramientas: muchas veces la pista está en una salida que pasé por alto.

## 3. Hipótesis

Antes de probar algo, lo escribo en una frase:

> *Si el servicio X está en la versión Y, entonces podría ser vulnerable a Z. Lo valido con…*

Esto me obliga a razonar en vez de lanzar herramientas a ciegas, y es la base de la sección **"Qué intenté y no funcionó"** de cada writeup.

## 4. Pruebas y explotación

* Pruebo una cosa a la vez y registro el resultado, funcione o no.
* Guardo el comando exacto que funcionó para que el ejercicio sea reproducible.
* Capturo evidencia en el momento (`screenshots/01-…png`, `02-…png`), nombrada por orden.
* Si hay que automatizar algo, lo escribo como script propio y lo guardo en [`scripts/`](../scripts/).

## 5. Escalada y post-explotación (si aplica)

* Enumero el contexto local antes de intentar nada: usuario, permisos, procesos, tareas programadas, servicios, archivos de configuración.
* Documento por qué elegí un vector y no otro.
* Registro qué datos sensibles aparecieron, pero los censuro en el writeup.

## 6. Enfoque según el tipo de reto

| Tipo | Cómo lo abordo |
|---|---|
| **Cripto y decodificación** | Identifico el formato y la codificación, anoto lo que conozco del texto original (formato de la flag, palabras esperadas) y pruebo hipótesis simples antes de escribir código. Ver [`scripts/xor-solver`](../scripts/xor-solver/) como ejemplo. |
| **Web** | Mapeo la aplicación, parámetros y flujos; pruebo una clase de vulnerabilidad cada vez; reviso respuestas, cabeceras y comportamiento ante entradas inesperadas. |
| **Red y servicios** | Enumero servicios y versiones, busco configuraciones débiles y credenciales por defecto, y valido cada hallazgo antes de explotarlo. |
| **Escalada de privilegios** | Enumeración local ordenada, vector identificado con evidencia, explotación mínima. |
| **Blue team** | Construyo primero la línea de tiempo, extraigo indicadores, valido con una segunda fuente de datos y termino escribiendo la regla de detección. |
| **Full-chain** | Combino las anteriores y dejo claro en qué punto de la cadena estoy en cada paso. |

## 7. Cuando me atasco

Me pongo un límite de tiempo y subo escalón a escalón. Cada salto lo registro:

| Escalón | Acción |
|---|---|
| 1 | Releer el enunciado y mis notas. Volver a enumerar. |
| 2 | Buscar la técnica o el servicio en documentación oficial y referencias. |
| 3 | Usar una pista de la propia plataforma. |
| 4 | Consultar un walkthrough, solo para desbloquear un paso concreto. |

> **Regla de honestidad:** si usé pistas o un walkthrough, lo indico en el writeup y ajusto el campo `tipo` (por ejemplo `guided-room`). Es parte del aprendizaje y suma credibilidad.

## 8. Documentación

* Redacto el writeup con la plantilla correspondiente, a partir de las notas tomadas durante el ejercicio.
* Cada paso explica **qué hice y por qué**, no solo el comando.
* Incluyo lo que intenté y no funcionó, con lo aprendido.
* Elimino las secciones de la plantilla que no apliquen y los comentarios guía.
* Mapeo las técnicas a [MITRE ATT&CK](https://attack.mitre.org/) cuando corresponde.

## 9. Cierre defensivo

Cada ejercicio termina respondiendo tres preguntas:

1. **¿Cómo se habría detectado?** Logs, eventos e indicadores relevantes.
2. **¿Qué regla o consulta lo detectaría?** Sigma, Wazuh, SIEM u otra.
3. **¿Cómo se evita?** Mitigaciones con prioridad (alta, media o baja).

## 10. Revisión antes de publicar

Antes de subir el writeup repaso la lista de [`ethics-scope.md`](ethics-scope.md):

- [ ] Flags, contraseñas, hashes y tokens censurados, también en las capturas.
- [ ] Revisados los términos de la plataforma sobre publicar soluciones.
- [ ] Metadatos del inicio completos.
- [ ] Fila añadida en el índice de la plataforma (por ejemplo [`tryhackme/README.md`](../tryhackme/README.md)).

## Herramientas habituales

Lista orientativa; cada writeup indica las que realmente usó.

| Área | Herramientas |
|---|---|
| Reconocimiento | Nmap, Gobuster, Nikto, Shodan |
| Web | Burp Suite |
| Cripto y decodificación | CyberChef, Python |
| Red y análisis | Wireshark |
| Blue team | Cortex XDR, Splunk, Wazuh, Sophos, VirusTotal |
