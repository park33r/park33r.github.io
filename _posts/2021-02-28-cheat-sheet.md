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

<em>Scanners:</em>
* <em>[Nmap](https://github.com/park33r/park33r.github.io/blob/master/pdf/nmap.pdf)<br>

<em>Fuzzing:</em>
* <em>Wfuzz</em><br>
  -c salida en color<br>
  -hc (hidden code) ocultar codigo y el numero de codigo [404, 403, etc]<br>
  -u direccion del dominio<br>
  FUZZ ubicacion donde se aplicara el fuzzing<br>
  -w ruta del diccionario a utilizar<br>
```js
  wfuzz -c --hc 404 -u http://url.com/FUZZ -w usr/share/wordlist/rockyou.txt 
 ```
 <em>Inyeccion SQL:</em>    
* <em>bypass</em><br>
Aqui podemos ver la parte del front-end de como seria la consulta inyectando el payload admin' or 1=1 -- -<br>
image: https://github.com/park33r/park33r.github.io/blob/master/assets/img/sqli/panel_bypass.png
y la back-end de la consulta:<br>
  ```js
  GET * from database WHERE username='$username' and password='$password'
  ```
  Podemos alterar la consulta con el siguiente strings:<br>
  en el username colocaremos una comilla simple para hacer que el username se cierre y despues colocamos un or 1=1 que esto dara verdadero y comentaremos la parte
  del password con -- - el cual indica que lo siguiente que viene no se tome en cuenta, quedando la consulta de esta manera.<br>
  ```js
  GET * from database WHERE username='' or 1=1 -- - and password=''
  ```
vemos que en username se abre el con la comilla y se cierra inmediatamente gracias a la comilla que hemos puesto,es decir que queda vacio,agregandole un o en ingles OR y sabiendo que 1=1 siempre es verdadero,comentando el and password si es vulnerable tendremos un bypass ya que 1=1 es verdadero.<br>

