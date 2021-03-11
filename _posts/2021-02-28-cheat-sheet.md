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
<strongs>       wfuzz -c --hc 404 -u http://url.com/FUZZ -w usr/share/wordlist/rockyou.txt </strongs><br>
  -c salida en color<br>
  --hc (hidden code) ocultar paginas con codigo de estado dado [404, 403, etc]<br>
  -u direccion del dominio<br>
  FUZZ ubicacion donde se aplicara el fuzzing<br>
  -w ruta del diccionario a utilizar.<br><br>
En vez de ocultar paginas con un codigo, flag --hc podemos cambiar por:<br>
--hl <numero> el cual oculta paginas que tengas X numero de lineas<br>
--hh <numero> con esta opcion ocultamos paginas que tengan X numero de caracteres<br><br>
  Doble fuzzing:<br>
  <strongs>     wfuzz -c --sc 200 -u https://url.com/FUZZ.FUZ2Z -w usr/share/worlists/rockyou -w ./extenciones.txt </strongs><br>
  -c salida en color<br>
  --sc (show code) mostrar paginas con codigo de estado dado [404, 403, etc]<br>
  -u direccion del dominio<br>
  FUZZ ubicacion donde se aplicara el fuzzing<br>
  FUZ2Z ubicacion donde se aplicara el segundo fuzzing y asi con FUZ3Z, FUZ4Z <br>
  -w ruta del diccionario a utilizar.<br><br>
  -w segunda ruta del segundo fuzzer la cual es un archivo con extenciones php txt html y mas<br><br>
  En vez de mostrar solo paginas con un codigo, flag --sc podemos cambiar por:<br>
--sl <numero> el cual muestra solo paginas que tengas X numero de lineas<br>
--sh <numero> con esta opcion muestra solo paginas que tengan X numero de caracteres<br><br>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
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



