---
date: 28/02/2021
layout: post
title: Cheat-Sheet
subtitle: Apuntes de comandos
description: En este apartado encontraras cheat-sheet de varias herramientas
image: /assets/img/cheatG.jpg
optimized_image: /assets/img/cheatP.jpg
category: herramientas
tags:
  - cheat-sheet
  - hacking-etico
  - ciberseguridad
author: park33r
---
Un especialista debera saber utilizar un abanico de herramientas bastante completo,debido a la gran cantidad de herramientas existentes, mas de 600 en kali linux y una suma parecida en otras distribucion como puede ser parrot.<br>
un buen hacker etico tendra que tener una pequeña guia para orientarse con las mejores herramientas del mercado<br>

<strong>Scanners:</strong>
* <em>[Nmap](https://github.com/park33r/park33r.github.io/blob/master/pdf/nmap.pdf)<br>

<strong>Fuzzing:</strong>
* <em>Wfuzz<br>
  -c salida en color<br>
  -hc (hidden code) ocultar codigo y el numero de codigo [404, 403, etc]<br>
  -u direccion del dominio<br>
  FUZZ ubicacion donde se aplicara el fuzzing<br>
  -w ruta del diccionario a utilizar<br>
```js
  wfuzz -c --hc 404 -u http://url.com/FUZZ -w usr/share/wordlist/rockyou.txt 
 ```
    
  
  
  


