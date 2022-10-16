---
layout: post
title: Mi primer proyecto en Django
tags: ["Django"]
---


Una vez hemos instalado Django en nuestro computador, podemos empezar a utilizarlo. Para crear nuestro primer proyecto, primero vamos a crear una carpeta para este proyecto, puedes ubicarla donde desees, luego de crear la carpeta la abres con el Visual Studio Code, y posteriormente basta escribir en nuestra terminal: 

<p class="code">django-admin startproject holamundo</p>

A mi, en lo personal, me resulta bastante práctico trabajar con el términal integrado de Visual Studio Code. Antes de continuar con el trabajo práctico, detengámonos por unos minutos en el patrón de arquitectura de Django:


## Patrón de arquitectura

Django utiliza el patrón de arquitectura **modelo MTV: Model Template View**, este parte del MVC o Model View Controller o Modelo Vista Controlador en español, veamos: El patrón de arquitectura Modelo Vista Controlador, funciona de la siguiente manera: cuando el usuario genera una petición al navegador, el sistema asocia las URL a un controlador, ese controlador se conecta con el Modelo (el cual es una abstracción de la base de datos, conectado a la BBDD a través de un ORM) y retorna la información que es presentada a través de la vista. En Django funciona de la siguiente manera: 

1) **Modelo:** abstracción de la base de datos, a través del ORM de Django se conecta con la base de datos. 

1) **Template:** son las plantillas, permiten presentar en pantalla la información procesada por las vistas (views).

1) **View:** reciben las peticiones del usuario en el navegador, a través de las URL, procesa la información y la retorna a los templates. 

## Hola mundo en Django

Continuemos, ya hemos creado nuestro primer proyecto, un proyecto en Django puede estar conformado por diferentes aplicaciones. Cada aplicación puede contener una funcionalidad completa dentro del proyecto, con sus propias vistas, urls, modelos, etc.  Al interior del proyecto es posible crear entonces aplicaciones, cada aplicación se gestiona como paquete y es un directorio dentro de nuestro proyecto. 

Un nuevo proyecto de Django presenta la siguiente estructura en el directorio principal:

![Principal](/images/principalDjango.png)

Luego, al abrir la carpeta blog en este caso, se encuentran los siguientes archivos:

![ArchivosAplicacion](/images/DjangoArchivos.png)

**Archivos de un proyecto**

El archivo **manage . py** es el que permite el control general del proyecto, así, por ejemplo permite ejecutar el proyecto, crear nuevas aplicaciones al interior del mismo, etc. 

**Init:** le permite a Python interpretar esta carpeta como un paquete. 

**Asgi:** estándar de Python que sirve para el posterior despliegue de la aplicación a servidor de producción. 

**Settings:** En este archivo se registran las aplicaciones del proyecto, directorio de templates, conexión del ORM de Django a la base de datos: MySQL, Oracle, PostgreSQL, MongoDB, etc. URL de archivos estáticos, media, etc.  De manera predeterminada el Framework ya tiene aplicaciones para gestionar las sesiones, panel de control de administración, autenticación y usuarios, mensajes, archivos estáticos, etc. 

**Urls:** permite configurar todas las rutas (URL) del proyecto, generalmente cada URL está asociada con una vista, además en el proyecto general se incluye la rula raíz para cada una de las aplicaciones del proyecto, por ejemplo si se tienen aplicaciones para gestionar información de docentes, estudiantes, etc, se definen así las rutas /docentes /estudiantes. Todas las URL del proyecto o de la aplicación, se incluyen dentro de un array [] llamado **urlpatterns** 

**Wsgi:** estándar de Python que sirve para el posterior despliegue de la aplicación a servidor de producción. 

**Para crear una aplicación dentro de un proyecto:**

<p class="code">
python manage.py startapp una_app
</p>

El interior de la aplicación sería el siguiente:

![ArchivosAplicacion](/images/archivosAplicacion.png)

**Archivos de una aplicación**

**__init__**: permite a Python interpretar la carpeta actual como un paquete. 

**admin**: permite registrar los modelos que serán reflejados en la url /admin del proyecto. Por ejemplo cuando se tiene una aplicación para registrar estudiantes, al agregar aqui el modelo estudiante, se podrán agregar nuevos estudiantes desde la url proyecto/admin

**apps**: 

**models**: Define el modelo de datos para cada una de las entidades de la aplicación, podría entenderse en términos, por ejemplo, de las tablas de una base de datos, un modelo por cada tabla. 

**test**: este archivo permite el registro de pruebas unitarias para realizar el testing sobre nuestra aplicación. 

**views**: las vistas son las que permiten renderizar las plantillas que serán presentadas al usuario a través del navegador web, además desde las vistas se realizan todas las consultas a la base de datos por ejemplo. 

 Para comprobar el proyecto se usa el servidor de pruebas así:

<p class ="code"> 
python manage.py runserver
</p>

Luego se abre en el navegador web así:

<p class ="code"> 
localhost:8000
</p>

Dejemos esta clase hasta este punto, en este momento ya debes ser capaz de crear el primer proyecto en Django, en próximas clases veremos paso a paso como empezar a personalizarlo...