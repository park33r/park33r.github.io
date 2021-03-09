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
En esta seccion encontraras cheat sheet o hojas de trucos con los comandos mas basicos sin profundisar mucho,para tener los comandos mas usados a la mano

<strong>Scanners:</strong><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<em>[Nmap](https://github.com/park33r/park33r.github.io/blob/master/pdf/nmap.pdf)<br>

<strong>Fuzzing:</strong><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<em>Wfuzz<br>
  -c salida en color<br>
  -hc (hidden code) ocultar codigo y el numero de codigo [404, 403, etc]<br>
  -u direccion del dominio<br>
  -w ruta del diccionario a utilizar<br>
```js
  wfuzz -c --hc 404 -u http://url.com/FUZZ -w usr/share/wordlist/rockyou.txt 
    
  ```
    
  
  
  


