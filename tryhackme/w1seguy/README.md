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

<img src="screenshots/icono_w1seguy.png" alt="Icono de la sala W1seGuy" width="300">

> Reto centrado en la criptografía.

## Resumen

<!-- 1 a 3 líneas: qué pide el reto y cómo se resolvió. -->
El desafío consistía en recuperar dos flags de un servicio que utilizaba cifrado XOR con una clave repetitiva. Mediante el análisis del código fuente y la automatización de un ataque Known Plaintext Attack, fue posible recuperar la clave de cifrado y descifrar la información necesaria para obtener ambas flags.

## Objetivo

* Descubrir la clave encriptada
* Recuperar flags

## Datos conocidos

<!-- Todo lo que el enunciado o el análisis inicial te da. -->

* Existen 2 flags
* Las flags empiezan por "THM{" y terminan en "}"
* Puerto 1337 TCP en escucha
* La clave se repite cada 5 caracteres

---

## Análisis

<!-- Explica tu razonamiento: qué hipótesis planteaste y por qué. -->

**Qué observé:** Al inspeccionar el codigo vemos que la flag está cifrada mediante XOR usando una clave de 5 caracteres que se repetía durante todo el proceso.<br>

**Qué hipótesis formulé:** Si conozco que la flag inicia con "THM{" y finaliza con "}", podemos recuperar byte a byte con la propiedad 
CLAVE = Ciphertext XOR PlainText. <br>

**Cómo la validé:** Mediante un script en Python para recuperar automáticamante los caracteres de la clave a partir del texto conocido y posteriormente descifrar el mensaje completo. La salida obtenida produjo una flag valida, confirmando la hipotesis.

## Solución paso a paso

**1.** Establecí la conexion a la IP de la maquina por el puerto que estaba en escucha.<br>
**2.** Analizar el archivo.py para encontrar pistas.<br>
**3.** Generé un xor_decrypt.py para descifrar la clave que me entregó la conexion netcat.<br>
**4.** Ingresar la clave recuperada.<br>
**5.** Entregar las flags encontradas.<br>

```bash
# nc 10.65.133.53 1337
```

```bash
# nano xor_decrypt.py
# chmod +x xor_decrypt.py
# python xor_decrypt.py
```

**Evidencia:** 

<img src="screenshots/w1seguy.png" alt="Icono de la sala W1seGuy">

---

## Técnica aprendida

<!-- Explica la idea general para que sirva en otros retos, no solo en este. -->
Con XOR de clave repetida, conocer parte del texto original permite recuperar la clave (clave = cifrado ⊕ original), así que un formato de flag conocido ya es suficiente para romperlo.

## Contexto defensivo

<!-- Por qué esta debilidad importa en un entorno real y cómo se evita. Elimina la sección si no aplica. -->
Esta vulnerabilidad demostró que usar claves XOR cortas no es seguro, porque si el atacante conoce parte del texto original, puede recuperar segmentos de la clave mediante Known Plaintext Attack y despues descifrar el mensaje. Se recomienda usar algoritmos critográficos modernos como por ejemplo AES.


## Lecciones aprendidas y próximos pasos

**Qué funcionó:** Buscar pistas dentro del código, aprovechar el formato conocido de la flag y elaborar el script.<br>
**Qué mejoraría en mi proceso:** Potenciar mi script para que no dependa de conocer el tamaño de la clave.

