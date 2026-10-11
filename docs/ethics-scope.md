# Alcance y ética

Este documento define qué contenido hay en este repositorio, qué queda fuera y qué reglas sigo al publicar. Se aplica a todos los writeups, scripts y notas.

## Alcance

**Dentro del alcance**

* Salas, retos y máquinas de plataformas de práctica (TryHackMe y similares), usadas según sus términos.
* Eventos CTF en los que participo con autorización de los organizadores.
* Laboratorios propios en entornos aislados que yo controlo (máquinas virtuales, redes simuladas).
* Ejercicios de detección y respuesta (blue team) sobre datos de laboratorio.

**Fuera del alcance**

* Cualquier sistema, red o cuenta que no sea mía y para la que no tenga autorización expresa.
* Sistemas de mi empleador o de clientes. Nada de ese trabajo se documenta aquí.
* Ataques contra servicios reales, aunque sean públicos.

## Reglas de publicación

**No publico:**

* Flags literales. Uso `THM{REDACTED}` o el formato equivalente de cada plataforma.
* Contraseñas, hashes, tokens, claves privadas ni cookies de sesión, aunque pertenezcan a un laboratorio.
* Datos personales, IPs o dominios reales ajenos al laboratorio.
* Soluciones completas de contenido que la plataforma prohíba compartir. Antes de publicar reviso los términos y la política de writeups de cada plataforma, sobre todo en retos y salas de pago.

**Sí publico:**

* Mi razonamiento, la metodología y los comandos necesarios para reproducir el ejercicio en el mismo entorno.
* Lo que intenté y no funcionó.
* La mirada defensiva: detección, indicadores y mitigaciones.
* Scripts propios con una explicación clara de su propósito y sus límites.

## Uso responsable

* El contenido es educativo. Las técnicas descritas solo se prueban en entornos autorizados.
* No publico código malicioso listo para desplegar. Si un laboratorio exige una herramienta ofensiva, enlazo a la herramienta pública en lugar de reescribirla.
* Si durante un ejercicio encuentro una vulnerabilidad en un sistema real y no en el laboratorio, no la exploto ni la documento. La comunico al responsable del sistema por un canal de divulgación responsable.

## Marco legal

Probar sistemas sin autorización puede ser delito en la mayoría de los países. Ningún documento de este repositorio sustituye la autorización por escrito del dueño del sistema ni constituye asesoría legal.

## Lista de revisión antes de publicar un writeup

- [ ] Las flags están censuradas.
- [ ] No hay contraseñas, hashes, tokens ni claves reales en el texto ni en las capturas.
- [ ] Las capturas no muestran datos personales ni de terceros.
- [ ] Revisé los términos de la plataforma sobre publicar soluciones.
- [ ] Incluí detección o mitigación cuando aplica.
- [ ] Los metadatos del inicio están completos.
