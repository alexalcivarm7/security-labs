---
Title: W1seGuy
Platform: TryHackMe
Type: challenge        # guided-room | challenge
Category: crypto      # crypto | encoding | forensics | web | network | privesc
Difficulty: easy       # easy | medium | hard
Date: 2026-10-11
Tools: [python]
Status: completado
---

# W1seGuy

> Reto centrado en la criptografía.

## Resumen

<!-- 1 a 3 líneas: qué pide el reto y cómo se resolvió. -->
El desafío consistía en recuperar dos flags de un servicio que utilizaba cifrado XOR con una clave repetitiva. Mediante el análisis del código fuente y la automatización de un ataque Known Plaintext Attack, fue posible recuperar la clave de cifrado y descifrar la información necesaria para obtener ambas flags.

## Objetivo

* Descubrir la clave encriptada
* Recuperar flags

## Datos conocidos

<!-- Todo lo que el enunciado o el análisis inicial te da. -->

* Dato 1: Existen 2 flags
* Dato 2: Las flags empieza por "THM{" y terminan en "}"
* Dato 3: Puerto 1337 TCP en escucha
* Dato 4: La clave se repite cada 5 caracteres

---

## Análisis

<!-- Explica tu razonamiento: qué hipótesis planteaste y por qué. -->

**1. Qué observé:** Al inspeccionar el codigo vemos que la flag está cifrada mediante XOR usando una clave de 5 caracteres que se repetia durante todo el proceso.
**2. Qué hipótesis formulé:** Si conozco que la flag inicia con "THM{" y finaliza con "}", podemos recuperar byte a byte con la propieda CLAVE = Ciphertext XOR PlainText
**3. Cómo la validé:** Mediante un script en Python para recuperar automaticamante los caracteres de la clave a mpartir del texto conocido y posterior descifrar el mensaje completo. La salida obtenida produjo una flag valida, confirmando la hipotesis.

## Solución paso a paso

1. **Paso 1:** Establecí la conexion a la IP de la maquina por el puerto que estaba en escucha
2. **Paso 2:** Analizar el archivo.py para encontrar pistas
3. **Paso 3:** Generé un xor_decrypt.py para decifrar la clave que me entregó la conexion netcat
4. **Paso 4:** Ingresar la clave encriptada
5. **Paso 5:** Entregar las flags encontradas

```bash
# nc 10.65.133.53 1337
```

```bash
# nano xor_descrypt.py
# chmod -x xor_descrypt.py
# python xor_descrypt.py
```

**Evidencia:** `screenshots/01-solucion.png`

---

## Técnica aprendida

<!-- Explica la idea general para que sirva en otros retos, no solo en este. -->
Cifrado XOR

## Contexto defensivo (si aplica)

<!-- Por qué esta debilidad importa en un entorno real y cómo se evita. Elimina la sección si no aplica. -->
Esta vulnerabilidad demostró que usar claves XOR cortas no es seguro, porque si el atacante conoce parte del texto original, puede recuperar segmentos de la clave mediante un ataque llamado Known Plaintext Attack y posterior a eso descifrar el mensaje
Se recomienda usar algortimos critograficos modernos como por ejemplo AES


## Lecciones aprendidas y próximos pasos

* Qué funcionó: Buscar pistas dentro del código, aprovechar el formato conocido de la flag y elaborar el script.
* Qué mejoraría en mi proceso: Potenciar mi script para que no dependa de conocer el tamaño de la clave.

## Artefactos

* Capturas: `screenshots/`
* Flag: `THM{REDACTED}`
