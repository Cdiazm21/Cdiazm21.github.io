---
title: Practica 14
layout: post
post-image: ../imagenes/practica14/Fotos/logo.png
description: La practica 14 trata de crear una instancia con terraform y instalarle wordpress a traves de docker.
tags:
- how to
- setup
- theme
---

# Practica 14-1

Voy a hacer una especie de introduccion de que va la practica. Estamos creandonos una instancia en la que en esa misma instancia vamos a usar docker para poder usar los contenedores y poder tener en una misma maquina instalado mysql, wordpress, phpmyadmin y el certificado.
Esto se dividira en redes y volumenes.

Para explicar practica vamos a dividirla en varios pasos:

**Paso 1:**
<br>Vamos a crearnos una instancia con terraform, a esta maquina le vamos a añadir el grupo de seguridad y una ip elastica(esto esta explicado en las anteriores practicas). 

Muestro el grupo de seguridad:

![](../imagenes/practica14/Fotos/4.PNG)

Muestro la creacion de la instancia y de la ip elastica:

![](../imagenes/practica14/Fotos/5.PNG)

**Paso 2**
<br>Hay que instalarnos docker y docker compose, para esto vamos a utilizar ansible:

![](../imagenes/practica14/Fotos/6.PNG)

Ahora vamos a añadir los paquetes de python para docker y movemos el directorio a la instancia:

![](../imagenes/practica14/Fotos/7.PNG)

**Paso 3**

<br>Ahora tenemos que crearnos los contenedores, los volumenes y las redes en nuestra instancia.
Para esto vamos a usar la pagina docker hub para usar las imagines oficiales de las que vamos a usar.
En nuestro caso nos pide la practica usar las imagenes de phpmyadmin, wordpress, mysql y https-service.

<br>Para wordpress:

![](../imagenes/practica14/Fotos/8.PNG)

<br>Para mysql:

![](../imagenes/practica14/Fotos/9.PNG)

<br>Para phpmyadmin:

![](../imagenes/practica14/Fotos/10.PNG)

<br>Para https-portal(este seria el certificado como certbot):

![](../imagenes/practica14/Fotos/11.PNG)

<br>Ahora muestro los volumenes y las redes:

![](../imagenes/practica14/Fotos/12.PNG)

<br>Recordatorio= Para poder ejecutar docker compose hay que instalarse en nuestra maquina:

![](../imagenes/practica14/Fotos/1.PNG)

<br>Las variables usadas son:

![](../imagenes/practica14/Fotos/13.PNG)

**Paso 4** 

<br>Hay que asignar a nuestra ip un dominio, en mi caso he usado la pagina de noip.com:

![](../imagenes/practica14/Fotos/15.PNG)

<br>Esto hay que añadirlo en nuestro https-portal.

**Paso 5**

<br>Comprobamos que funciona, para esto vamos a poner nuestro dominio en nuestro navegador:

![](../imagenes/practica14/Fotos/2.PNG)

<br>Y seguimos los pasos hasta llegar a nuestro wordpress:

![](../imagenes/practica14/Fotos/3.PNG)