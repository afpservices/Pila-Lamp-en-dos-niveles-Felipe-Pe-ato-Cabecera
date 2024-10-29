# Pila-Lamp-en-dos-niveles-Felipe-Pe-ato-Cabecera

Practica Lamp en dos niveles

Procedemos a crear un repositorio publico en github el cual usaremos su url para la entrega del proyecto con la explicacion y toda la infraestructura y ficheros subidos mediante ese enlace

![image](https://github.com/user-attachments/assets/2f264a68-ebab-4895-a6a4-cf6ec648bd3a)




Antes de crear las maquinas virtuales deberemos de crear los ficheros de aprovisionamiento el cual
crearemos 2, uno para el mysql y otro para apache

Script para instalar mysql server en la maquina de mysql, ademas actualizamos los repositorios del
sistema para instalar mysql


Script para instalar apache en la maquina de apache, ademas actualizamos los repositorios del
sistema para instalar apache, ademas deberemos de instalar php y las librerias

Ahora prepararemos la configuracion de las maquinas con sus debidos scripts de aprovisionamiento
ejecutando en la ruta de la carpeta un vagrant init y accedemos al fichero vagrantfile y preparamos
las 2 maquinas.


Aqui en la maquina de sql he puesto una red publica para que pueda acceder a internet y una red
privada, ademas del fichero de aprovisionamiento.sh

Aqui en la maquina de apache he realizado el reenvio de puertos, tambien una red privada, ademas
del fichero de aprovisionamiento.sh

Ahora procedemos a realizar un vagrant up en la ruta de la carpeta y procedemos a arrancar las
maquinas ademas te empezaran a actualizar



Comprobamos que se quedan arrancadas correctamente

## CONFIGURACION DE LA MAQUINA MYSQL

Ahora accedemos a la maquina de mysql para poner la ip de nuestra maquina de sql que hemos
establecido anteciormente en el fichero de aprovisionmiento

Accdemos al fichero mysql.cnf y cambiamos la ip del bind-address por nuestra ip.


Ahora accedemos a la base de datos con el root y la contraseña

Ahora creamos un usuario con la ip de la maquina de apache y damos todos los permisos al usuario

Ahora vamos a clonar el repositorio de github para descargar la base de datos


Ahora procederemos a entrar en la carpeta que hemos creado a partir de clonar el repositorio de git
y a añadir la base de datos sql que contiene a nuestra base de datos y comprobamos que esta se
encuentre tal y como es.

## CONFIGURACION DE LA MAQUINA APACHE

Para ello accederemos a la carpeta en la ruta /var/www y crearemos una carpeta llamada
lampdosniveles y le cambiaremos el propietario con el comando chown -R


Ahora clonaremos el repositorio de git hub dentro de la carpeta que hemos creado y una vez lo
tengamos accedemos y nos vamos al directorio src de esa carpeta y lo copiamos en la carpeta que
hemos creado


Ahora nos iremos a la carpeta de apache el cual se encuentran lo sitios dispinibles activos de
apache, en el cual copiaremos la informacion del archivo de configuracion (default) y crearemos
uno llamado lampdosniveles.conf y le ponemos la ruta en donde hemos creado nuestro directorio


Ahora habilitaremos el fichero de configuracion que hemos creado y seguidamente nos vamos a la
ruta /etc/apache2/sites-enabled y desactivamos el fichero de configuracion (default) y le hacemos
un reload a apache con systemctl reload apache


Ahora configuraremos el fichero de config php que hemos copiado a la carpeta lampdosniveles en
el que modificaremos los datos y pondremos la ip de la maquina de mysq, nuestro nombre de base
de datos que le hemos dado y el usuario con el password que hemos creado antes


Ahora procederemos a poner nuestra ip del server apache y comprobamos que nos funciona
correctamente



