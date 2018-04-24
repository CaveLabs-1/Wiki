# Manual Arquitectura General
Versión 1.1

El propósito de esta guía es que cualquier miembro de CaveLabs sea capaz de diseñar, realizar y ejecutar pruebas de unidad, además de configurar, montar y actualizar el servidor de producción de manera automática. También se pretende que puedan integrar herramientas de Continious Integration como lo es TravisCI o Jenkins.

## Index

* [Estrategia Inicial Pruebas](#estrategia)

* [Pruebas de unidad e integración](#unidad)

* [Configración Django](#Django)

* [Configuración servidor](#servidor)

* [Configuración del dominio](#dominio)

* [Habilitar HTTPS: certificado SSL](#seguridad)

* [Actualización Servidor](#act)

* [Pruebas de sistema](#sistema)

* [Pruebas de usabilidad](#usabilidad)

* [Integración Continua](#CI)

<a id="estrategia"></a>
## Estrategia Inicial Pruebas

La estrategia inicial de pruebas con todas las estrategias a seguir. [(Link al documento)](https://docs.google.com/document/d/1PgdUA8xFewguZ60CxT8zHAL99JwXaaWbaGj_wZo3az0/edit)

<a id="unidad"></a>
## Pruebas de Unidad e Integración

Se utilizará la suite de testing de Django de Unit Testing.
En el análisis de cada historia de usuario, se deberá especificar el criterio de aceptación.
A partir del criterio de aceptación, se diseñarán, realizarán y ejecutarán las pruebas siguiendo todos los casos que se presentaron en los criterios de aceptación.

<a id="Django"></a>
## Configuración Django

Para poder aplicar práticas como Continious Integration y Automated Deployment, es necesario que nuestro proyecto de django esté listo todo el tiempo para poder estár en producción por lo que se deberá hacer lo siguiente:

  1. Cambiar la estructura actual del proyecto, una estructura común es tener el archivo *settings.py* adentro de la carpeta de tu proyecto, se deberá de crear una carpeta llamada settings en la cuál tendrás 3 archivos, un archivo base, uno para producción y uno para deployment. Una estructura ejemplo suponiendo que el proyecto se llama sustena quedaría así:

  ```
  sustenta/
  |-- sustenta/
  |    |-- __init__.py
  |    |-- settings/         <--
  |    |    |-- __init__.py  <--
  |    |    +-- base.py      <--
  |    |    +-- production.py      <--
  |    |    +-- development.py      <--
  |    |-- urls.py
  |    +-- wsgi.py
  +-- manage.py
  |-- app1/
  ```

  3. Poner los settings en común en el archivo *base.py*.

  4. Importar todo lo que irá en el archivo *base.py* en los archivos de producción y desarrollo, en nuestro caso *development.py* y *production.py*

  ```
  from base.settings.common import *
  ```

  5. Poner los ajustes en sus respectivos archivos.

  *production.py*

  ```  
  from CADHU.settings.common import *

  # SECURITY WARNING: keep the secret key used in production secret!
  with open('/etc/secret_key.txt') as f:
      SECRET_KEY = f.read().strip()

  # SECURITY WARNING: don't run with debug turned on in production!
  DEBUG = False

  ALLOWED_HOSTS = ['la liga de tu sistema.com','123.567.891']

  # Database
  # https://docs.djangoproject.com/en/1.11/ref/settings/#databases

  DATABASES = {
      'default': {
          'ENGINE': 'django.db.backends.postgresql',
          'NAME': '(nombre base de datos)',
          'USER': '(usuario)',
          'PASSWORD': '(password)',
          'HOST': '127.0.0.1',
          'PORT': '5432',
      }
  }
  ```

  Nota: La secret key se recomienda poner en un archivo dentro del servidor de producción, por lo que en este caso se puso en el archivo *secret_key.txt*

  *development.py*

  ```
  from CADHU.settings.common import *

  # SECURITY WARNING: keep the secret key used in production secret!
  SECRET_KEY = (Llave de tu proyecto)

  # SECURITY WARNING: don't run with debug turned on in production!
  DEBUG = True

  ALLOWED_HOSTS = ['*']

  # Database
  # https://docs.djangoproject.com/en/1.11/ref/settings/#databases

  DATABASES = {
      'default': {
          'ENGINE': 'django.db.backends.postgresql',
          'NAME': '(nombre base de datos)',
          'USER': '(usuario)',
          'PASSWORD': '(password)',
          'HOST': '127.0.0.1',
          'PORT': '5432',
      }
  }
  ```

  6. Cambiar los settings por default en el archivo *wsgi.py* y en el *manage.py*.

  ```
  #Lo que está
  os.environ.setdefault("DJANGO_SETTINGS_MODULE", "sustenta.settings")

  #Lo que se va a poner
  os.environ.setdefault("DJANGO_SETTINGS_MODULE", "sustenta.settings.development")
  ```

  7. Crear una variable de entorno en el servidor.

  ```
  #Comando para mostrar variables de entorno
  set

  #Se debe de agregar en el archivo .baschrc
  export DJANGO_SETTINGS_MODULE="sustenta.settings.production"
  ```
  
<a id="servidor"></a>
## Configuración servidor

  Liga configuración servidor Digital Ocean, utilizando Django, Nginx, Gunicorn y PostgreSQL. [(link)](https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-16-04)

  Comandos útiles:

  ```
    #Checar estatus gunicorn
    sudo systemctl status gunicorn

    #Checar estatus postgres
    sudo systemctl status postgresql

    #Si se cambia el archivo gunicorn (.sock)
    sudo systemctl daemon-reload
    sudo systemctl restart gunicorn

    #Si se cambia el archivo de configuración de Nginx
    sudo nginx -t && sudo systemctl restart nginx

    #Checar logs de procesos de Nginx
    sudo journalctl -u nginx

    #Checar logs de accesos de Nginx
    sudo less /var/log/nginx/access.log

    #Checar logs de errores de Nginx
    sudo less /var/log/nginx/error.log

    #Checar logs de aplicacioón de Gunicorn
    sudo journalctl -u gunicorn
  ```

Tip: Si se llega a encontrar con un error 500 y no se encontró el error usando los comandos mencionados, puede recurrir a cambiar el DEBUG=True del archivo de configuración del proyecto de django.

<a id="dominio"></a>
## Configuración del dominio

> Requisitos: Dominio y cuenta de Digital Ocean.

Entrar a la configuración de DNS en la cuenta donde se adquirió el dominio.

<img src="https://github.com/CaveLabs-1/Wiki/blob/master/Arquitectura/Manuales/dns.png" width="350"/>

Agregar los nameservers de Digital Ocean:

* ns1.digitalocean.com
* ns2.digitalocean.com
* ns3.digitalocean.com

Abrir Digital Ocean y agregar el dominio a la cuenta:

<img src="https://assets.digitalocean.com/articles/pdocs/site/control-panel/networking/domains/digitalocean.love-listed.png" width="700px"/>

Entrar a los registros del DNS: 

<img src="https://assets.digitalocean.com/articles/pdocs/site/control-panel/networking/domains/digitalocean-love-records.png" width="700px"/>

Agregar registros de:

* **A**: Un registro A asigna una dirección IPv4 a un nombre de dominio. Esto determina dónde dirigir las solicitudes de un nombre de dominio.
* **MX**: Un registro MX especifica los servidores de correo responsables de aceptar el correo electrónico en nombre de su dominio.
* **CNAME**: Un registro CNAME define un alias para un registro A; apunta un dominio a otro dominio en lugar de a una dirección IP. Cuando la dirección IP del registro A asociado cambia, el CNAME seguirá a la nueva dirección.

### Redirigir subdominio www al dominio raíz con Nginx

Ingresar al servidor.

Abrir el documento default de sites-available:

```sh
nano /etc/nginx/sites-available/default
```

Agregar lo siguiente hasta arriba del documento:

```sh
server {
    server_name  www.dominio.com;
    rewrite ^(.*) https://dominio.com$1 permanent;
}
```

Cerrar y guardar el documento:

```sh
Ctrl + X
Y
```

Reiniciar Nginx:

```sh
service nginx restart
```


<a id="seguridad"></a>
## Habilitar HTTPS: certificado SSL

> Requisitos: Dominio configurado en Digital Ocean, Nginx y Ubuntu (14.4 o posterior).

Ingresar al servidor y ejecutar los siguientes comandos:

```sh
#Actualizar paquetes y programas
$ sudo apt-get update

#Instalar el paquete software-properties-common
$ sudo apt-get install software-properties-common

#Agregar el repositorio de Certbot
$ sudo add-apt-repository ppa:certbot/certbot

#Actualizar paquetes y programas
$ sudo apt-get update

#Instalar Certbot para Nginx
$ sudo apt-get install python-certbot-nginx 
```

Instalar certificado a Nginx:

```sh
$ sudo certbot --nginx
```

Configuración de Certbot:

* Ingresar correo electrónico (para avisos urgentes de renovación y seguridad).

* Aceptar términos y condiciones.

* Seleccionar los dominos para habilitar HTTPS.

* Seleccionar la opción para redirigir todo el tráfico HTTP a HTTPS y quitar acceso a HTTP.

Los certificados tienen una vigencia de 90 días, para automatizar la renovación ejecutar el siguiente comando:

```sh
$ sudo certbot renew --dry-run
```

<a id="act"></a>
## Actualización servidor
En la raíz del proyecto deberá de crearse un script que sirva para poder activar el virtual environment, bajar las actualizaciones del repositorio, realizar las migraciones necesarias y actualizar el servidor en caso de que haya algún cambio en el proyecto.

 * Ejemplo:

```
  #!/bin/bash
  source my_env/bin/activate
  cd CADHU
  git pull origin master
  pip install -r requirements.txt
  for linea in `cat apps.txt`
  do
    python manage.py makemigrations $linea
    python manage.py migrate
  done
  sudo systemctl restart gunicorn
  deactivate
  cd ~
```

* Para poder ejecutar el script anterior, es necesario que se cuente con el archivo *apps.txt* el cúal se debe de poner el nombre de las apps de su proyecto en nivel de dependencia, la más independiente en la parte superior.

* Debido a que se necesita de la variable de entorno DJANGO_SETTINGS_MODULE con el respectivo archivo de configuración a ejecutar en producción, necesitamos hacer uso del ambiente actuál por lo que deberás de ejecutar el script de la siguiente manera desde la raíz de tu servidor:

  ```
    source ./deploy.sh

    #Nota: poner contraseña de super usuario lista en caso de que la pida el script.
  ```

<a id="sistema"></a>
## Pruebas de sistema y ambiente
[Link al proceso de pruebas de sistema](https://github.com/CaveLabs-1/Wiki/blob/master/SWAT/PruebasSWAT.md)

<a id="sistema"></a>
## Pruebas de usabilidad
[Link al proceso de reporte de usabilidad.](https://github.com/CaveLabs-1/Wiki/blob/master/Usabilidad/Proceso%20Usabilidad.md)

<a id="CI"></a>
## Integración Continua

El proposito de *Integración Continua* es poder integrar el trabajo de todos los integrantes una manera segura continuamente para poder detectar errores de una manera más rápida, por lo que existen herramientas como Jenkins, TravisCI, CircleCI y otras. En este caso se utilizará TravisCI, debido a que nos permite verificar el código que se quiere integrar de una manera segura y efectivo, ejecutando los tests con el código a integrar.

### Travis CI
Para poder integrar TravisCI se deben de seguir de seguir varios pasos:

  1. Registrarte con tu cuenta de estudiante al programa de GitHub student y meterte al link que provee TravisCI en este [link](https://education.github.com/pack).
  2. Una vez que se entró a la liga, para poder hacer uso de TravisCI, se tienen que seguir 3 sencillos pasos.

  ![pasos](https://cdn-images-1.medium.com/max/715/1*FWFbHIZBQiJ5o4v010tGTg.png)

  3. Si tu repositorio es privado, accede a este [link](https://travis-ci.com), en caso de que sea público accede a este [link](https://travis-ci.org) e inicia sesión en caso de que te lo pida.

  4. Activa Travis en tu repositorio haciendo click en el cuadro a lado del repositorio en el que quieres activar Travis. Posteriormente entra en la parte de settings dandole click en el engrane a lado del botón.

  ![activa](https://i2.wp.com/www.marcobeltempo.com/wp-content/uploads/2017/11/travisCI_capture1.gif?resize=456%2C189&ssl=1)

  5. Como se puede ver la pantalla contiene diversas cosas, del lado izquierdo puedes ver tus repositorios y el resultado del útlimo build, settings, el historial y otras cosas.

  6. Se recomienda que solo pruebes el código que se integrará en pull requests, por lo que le daremos click en **Build pushed pull requests**, esto hará que cada vez que hagas un pull request, travis empezará un build. Checa que solo esté activado el botón que se mencionó anteriormente.

  7. Crea un archivo que se llame *.travis.yml* en la carpeta raíz de tu repositorio que contenga lo que se define [aquí](https://docs.travis-ci.com/user/customizing-the-build/), ejemplo:

  ```
    language: python
    python:
      - "3.6"
      - "3.5"
    script:
      - python manage.py test
    notifications:
      email: false
    branches:
    only:
      - "master"
  ```

  8. Para finalizar crea una pull request para que travis corra el script que especificaste. (Recuerda hacerlo a la rama que especifiques en el script)

  9. Si no lograste integrar travis con estos pasos, checa este [tutorial](https://www.youtube.com/watch?v=Uft5KBimzyk) a partir del minuto *8:04*.
  
  ### Jenkins
  
  [Link al manual de Jenkins.](https://github.com/CaveLabs-1/Wiki/blob/master/Integración%20Continua%20Jenkins.pdf)
  
## Bitácora
No. de versión | Cambio | Autor | Aprobado | Fecha de Cambio
---------------|--------|-------|----------|-----------------
1.0 | Integrar a la wiki | Marco Mancha | Marco Luna |  23 Abril 2018
1.1 | Habilitar HTTPS: certificado SSL  | Santiago | Marco Luna |  23 Abril 2018

última edición: @agovc, 23 Abril 2018.
