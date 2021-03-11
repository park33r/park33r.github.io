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

<em>Scanners:<em>
* <em>[Nmap](https://github.com/park33r/park33r.github.io/blob/master/pdf/nmap.pdf)<br>

<em>Fuzzing:<em>
* Wfuzz<br>
<strongs>       wfuzz -c --hc 404 -u http://url.com/FUZZ -w usr/share/wordlist/rockyou.txt </strongs>
 <ul>
   <li -c salida en color</li><br>
  <li --hc (hidden code) ocultar paginas con codigo de estado dado [404, 403, etc]</li><br>
  <li -u direccion del dominio</li><br>
  <li FUZZ ubicacion donde se aplicara el fuzzing</li><br>
  <li -w ruta del diccionario a utilizar.</li><br><br>
En vez de ocultar paginas con un codigo, flag --hc podemos cambiar por:<br>
<li --hl <numero> el cual oculta paginas que tengas X numero de lineas</li><br>
<li --hh <numero> con esta opcion ocultamos paginas que tengan X numero de caracteres</li><br>
<li --hw <numero> ocultamos paginas que contengan X numero de palabras</li><br><br>
  Doble fuzzing:<br>
<li <strongs>     wfuzz -c --sc 200 -u https://url.com/FUZZ.FUZ2Z -w usr/share/worlists/rockyou -w ./extenciones.txt </li></strongs><br>
  <li -c salida en color</li><br>
  <li --sc (show code) mostrar paginas con codigo de estado dado [200, 403, etc]</li><br>
  <li -u direccion del dominio</li><br>
  <li FUZZ ubicacion donde se aplicara el fuzzing</li><br>
  <li FUZ2Z ubicacion donde se aplicara el segundo fuzzing y asi con FUZ3Z, FUZ4Z </li><br>
  <li -w ruta del diccionario a utilizar</li><br>
  <li -w segunda ruta del segundo fuzzer la cual es un archivo con extenciones php txt html y mas<br><br>
  En vez de mostrar solo paginas con un codigo, flag --sc podemos cambiar por:</li><br>
<li --sl <numero> el cual muestra solo paginas que tengas X numero de lineas</li><br>
<li --sh <numero> con esta opcion muestra solo paginas que tengan X numero de caracteres</li><br>
<li --sw <numero> mostramos solo paginas con X numero de palabras<br><br>
 cookie<br>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 <em>Inyeccion SQL:</em>    
* <em>bypass</em><br>
Esto es una consulta a una base de datos para iniciar sesion:<br>
 ```js
  GET * from database WHERE username='$username' and password='$password'
  ```
Aqui podemos ver la parte del front-end de como seria la consulta si inyectamos el payload admin ' or 1=1 -- -<br>
![](/assets/img/sqli/panel_bypass.png)<br>
Explicacion del payload:<br>
en el username colocaremos una comilla simple para hacer que el username se cierre y despues colocamos un or 1=1 que esto dara verdadero y comentaremos la parte
del password con - - (dos guiones separados)el cual indica que lo siguiente que viene no se tome en cuenta, quedando la consulta de esta manera.<br>
```js
  GET * from database WHERE username='' or 1=1 -- and password=''
 ```
vemos que en username se abre con la comilla y se cierra inmediatamente gracias a la comilla que hemos puesto,es decir que queda vacio,agregandole un o en ingles OR y sabiendo que 1=1 siempre es verdadero,comentando el and password con (- -), si es vulnerable tendremos un bypass ya que 1=1 es verdadero ingresando sin necesidad de tener credenciales validas.<br>
*<em>Burp Suite & sqlmap</em><br>



