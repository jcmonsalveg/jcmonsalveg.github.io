---
layout: post
title: Introduccion a Django
tags: Django, Python
---

Django es un Framework de Python para el desarrollo web. Permite la construcción de sitios web potentes, robustos y seguros. Según como se indica en el sitio web [Developer Mozilla](https://developer.mozilla.org/es/docs/Learn/Server-side/Django/Introduction) Django permite la construcción de Software: Completo, versátil, seguro, escalable, mantenible y portable (tomado de la web). Dejemos a un lado la teoría y vamos con la instalación.

## Instalación de Django

Al tratarse de un Framework de Python, sobra aclarar, entonces, que es necesario tener **Python** instalado en nuestro PC antes de instalar Django, además del gestor de paquetes **PIP**, cuando se instala Python desde el sitio **www.python.org** se deben marcar dos opciones: 1) Agregar al PATH y 2) Instalar PIP.  Es muy importante, una vez instalado Python verificar que las variables de Entorno estén bien configuradas.

Para verificar las variables de entorno se buscan en el CMD las variables de entorno, Opciones avanzadas / varibles de entorno / Path / editar, aparecen tanto python como las variables de entorno:

![Variables](/images/variables-de-entorno.png)

Para verificar la versión de Python, en el CMD escribir:

~~~ 
python --version
~~~ 

Luego de tener Python instalado y las variables de entorno configuradas adecuadamente, se instala **DJANGO**, es importante mirar: [El sitio oficial Django](https://www.djangoproject.com/download/) para conocer la última versión, en el momento de la Instalación de este tutorial es la 4.1.  Para instalar Python se puede ejecutar el siguiente comando en una terminal, indicando la versión que en su momento sea la más actualizada y estable. 

~~~ 
python -m pip install Django==4.1
~~~ 

Para verificar si efectivamente Django fue instalado, en la misma terminal vamos a escribir: 

~~~ 
django-admin --version
~~~ 


En la próxima entrada empezaremos a crear nuestro proyecto. 