---
layout: post
title: Entornos virtuales en Python
tags: ["python", "entornos virtuales"]
---

Python es un lenguaje de programación de alto nivel, ampliamente empleado para el desarrollo web a través de frameworks como Django y Flask (este último conocido como microframework), además en ciencia de datos y machine learning. Python se caracteriza por la legibilidad de su código y rapidez en su curva de aprendizaje. Este lenguaje permite diferentes maneras de manejar entornos virtuales. 
![Entornos](/images/entornos.png)

## ¿Qué es un entorno virtual?

Empecemos por el principio. Cuando instalas paquetes en Python, estos se instalan de forma global en todo el sistema, al comienzo parece ser una situación que no genera mayores complicaciones, pero cuando empezamos a practicar y vamos creando cada vez más y más proyectos, más y más paquetes, es posible llegar a un momento en el cual se generen conflictos, pues es posible que para un proyecto empleamos un paquete o versión específica...pero tiempo después nuestros nuevos proyectos pueden requerir nuevas versiones y al actualizar las existentes, es posible que los proyectos anteriores, tal vez un poco más viejos, tengan dificultades para funcionar. 

Los entornos virtuales nos permiten crear espacios aislados en el sistema, donde podremos tener versiones y paquetes / módulos / librerías distintos para cada proyecto. Entonces, si tenemos por ejemplo en la carpeta **proyecto A** nuestros paquetes A versión 1.0, B, versión 1.3 y C, versión 1.4, en la carpeta **protecto B** podremos tener una versión distinta del paquete A, del paquete B y del paquete C, además podremos tener un paquete D solo para ese proyecto.

## ¿Qué opciones tenemos en Python?

en Python existen varias herramientas que nos permiten la creación de ambientes virtuales, estos espacios aislados y controlados donde podremos desarrollar nuestros proyectos de software, sin afectar las demás instalaciones que tengamos en nuestro sistema o en otros entornos. 


### Pyvenv

Si se revisa la documentación oficial de Python, la herramienta recomendada para la creación de entornos virtuales es Pyenv, el comando que permite la creación de un entorno bajo esta herramienta, en Windows es: 

~~~ 
python -m venv nombreDelEntorno
~~~ 

Por convención los entornos son denominados casi siempre como venv. Una vez creado el entorno este debe ser activado, así: 

~~~ 
nombreDelEntorno\Scripts\Activate
~~~ 

Para ampliar la información sobre esta herramienta, revisar la [Documentación oficial](https://docs.python.org/es/3/tutorial/venv.html)

Esta herramienta la comparto solo a manera de información general, pero la herramienta **más recomendada** es la que viene a continuación... aún así, una vez que explores el uso de estas y otras herramientas existentes, tu decides con cuál te quedas. :)

### Pipenv

Esta es la herramienta más recomendadas y fácil de usar para la creación de estos entornos: **pipenv**, veamos como funciona:

**Paso 1: Instalar** instalar pipenv en nuestro sistema operativo, en este caso particular vamos a trabajar sobre Windows con el gestor de paquetes PIP, procedemos entonces:

~~~ 
pip install pipenv
~~~ 

**Paso 2: Crear un entorno** Una vez instalado ya se pueden crear los entornos, para eso se ingresa a la carpeta donde se desea activar y simplemente se escribe: 

~~~ 
pipenv shell
~~~ 

Recuerda, si estás iniciando en el mundo del desarrollo de software, que cada proyecto, es decir, cada aplicación que vamos a desarrollar, tiene su propia carpeta. Al ejecutar el comando indicado el entorno se creará y se activará, si se ejecuta nuevamente el mismo comando, el sistema indicará que el entorno ya se encuentra activo. 

**Paso 3: Instalar paquetes** El comando anterior automaticamente creará y activará un entorno virtual, ahora, si deseamos instalar un paquete como flask por ejemplo, en este proyecto, basta con escribir:

~~~ 
pipenv install flask
~~~ 

Cuando se instala pipenv se genera el archivo pipfile al interior del directorio, ahora, al abrir este archivo con nuestro editor de código, podremos ver que allí se van registrando los paquetes instalados, en nuestro caso particular ya podremos ver flask debajo de [packages].

Si se desea instalar un paquete en una versión específica, entonces esta se debe indicar en la línea, así:

~~~ 
pipenv install Django==4.1.2
~~~ 

Si se desea conocer la lista de aplicaciones instalas en un entorno virtual se puede utilizar el comando:

~~~ 
pip list
~~~ 

Esta es tan solo una introducción, un primer vistazo a los entornos con Python, hay mucha más información en la web, la recomendación siempre es acudir a la fuente oficial de cada una de estas tecnologías, revisando su documentación. 

Toda la información sobre pipenv puede encontrarse en su [Sitio oficial](https://pipenv-es.readthedocs.io/es/latest/)
