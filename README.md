# Pila-Lamp-en-dos-niveles-Felipe-Pe-ato-Cabecera

Practica Lamp en dos niveles

Procedemos a crear un repositorio publico en github el cual usaremos su url para la entrega del proyecto con la explicacion y toda la infraestructura y ficheros subidos mediante ese enlace

![image](https://github.com/user-attachments/assets/2f264a68-ebab-4895-a6a4-cf6ec648bd3a)




Antes de crear las maquinas virtuales deberemos de crear los ficheros de aprovisionamiento el cual crearemos 2, uno para el mysql y otro para apache

Script para instalar mysql server en la maquina de mysql, ademas actualizamos los repositorios del sistema para instalar mysql

![image](https://github.com/user-attachments/assets/7ad1d5c3-a0f0-464a-81f1-3a1d8cc816ee)



Script para instalar apache en la maquina de apache, ademas actualizamos los repositorios del sistema para instalar apache, ademas deberemos de instalar php y las librerias


![image](https://github.com/user-attachments/assets/8d8955a2-40e8-42aa-bced-14eb7c257e92)



Ahora prepararemos la configuracion de las maquinas con sus debidos scripts de aprovisionamiento ejecutando en la ruta de la carpeta un vagrant init y accedemos al fichero vagrantfile y preparamos las 2 maquinas.


![image](https://github.com/user-attachments/assets/3017ae89-54af-40a5-89f8-1111366485ce)


Aqui en la maquina de sql he puesto una red publica para que pueda acceder a internet y una red privada, ademas del fichero de aprovisionamiento.sh



![image](https://github.com/user-attachments/assets/6cdf2ad8-3188-4941-a768-747eedcd50ad)



Aqui en la maquina de apache he realizado el reenvio de puertos, tambien una red privada, ademas del fichero de aprovisionamiento.sh
![image](https://github.com/user-attachments/assets/83bb3e4b-ef6b-48f1-a634-781d48f5cc7a)



Ahora procedemos a realizar un vagrant up en la ruta de la carpeta y procedemos a arrancar las maquinas ademas te empezaran a actualizar

![image](https://github.com/user-attachments/assets/076000fc-a210-477c-915c-9add0875636b)


Comprobamos que se quedan arrancadas correctamente
![image](https://github.com/user-attachments/assets/6233d258-28ee-4df5-b23f-7c6eeb0ad82c)




## CONFIGURACION DE LA MAQUINA MYSQL


Ahora accedemos a la maquina de mysql para poner la ip de nuestra maquina de sql que hemos
establecido anteciormente en el fichero de aprovisionmiento

Accdemos al fichero mysql.cnf y cambiamos la ip del bind-address por nuestra ip.

![image](https://github.com/user-attachments/assets/617e6519-3420-4e9b-8cd1-e4efc7e81755)


Ahora accedemos a la base de datos con el root y la contraseña

![image](https://github.com/user-attachments/assets/9bfe5a23-c792-4603-9fef-636c30827994)

Ahora creamos un usuario con la ip de la maquina de apache y damos todos los permisos al usuario

![image](https://github.com/user-attachments/assets/b6412dcd-60f8-47eb-84d7-ef87a428055f)


Ahora vamos a clonar el repositorio de github para descargar la base de datos

![image](https://github.com/user-attachments/assets/91a325c7-c85d-4757-8112-7d0653306edd)


Ahora procederemos a entrar en la carpeta que hemos creado a partir de clonar el repositorio de git y a añadir la base de datos sql que contiene a nuestra base de datos y comprobamos que esta se encuentre tal y como es.


![image](https://github.com/user-attachments/assets/c22c216b-9302-41ea-94d7-3364d568bc01)



## CONFIGURACION DE LA MAQUINA APACHE

Para ello accederemos a la carpeta en la ruta /var/www y crearemos una carpeta llamada
lampdosniveles y le cambiaremos el propietario con el comando chown -R

![image](https://github.com/user-attachments/assets/7f978210-fa46-4f30-aed4-23efa2a9e23d)


Ahora clonaremos el repositorio de git hub dentro de la carpeta que hemos creado y una vez lo tengamos accedemos y nos vamos al directorio src de esa carpeta y lo copiamos en la carpeta que hemos creado

![image](https://github.com/user-attachments/assets/907f7f3f-df37-4548-85b6-cf5ad8f83fc1)
![image](https://github.com/user-attachments/assets/facb2ebf-02af-4da0-8510-f96192826bf3)
![image](https://github.com/user-attachments/assets/4446d4f7-aa49-4038-ac2f-e81f3aca44ef)
![image](https://github.com/user-attachments/assets/8447b234-2d7a-4863-8200-1c46d0dc03d3)



Ahora nos iremos a la carpeta de apache el cual se encuentran lo sitios dispinibles activos de apache, en el cual copiaremos la informacion del archivo de configuracion (default) y crearemos uno llamado lampdosniveles.conf y le ponemos la ruta en donde hemos creado nuestro directorio

![image](https://github.com/user-attachments/assets/dd22e6e4-70d2-4a41-b3a1-98b0217e0822)

![image](https://github.com/user-attachments/assets/e20b88dd-6b4c-457d-a6b0-af32823925e8)


Ahora habilitaremos el fichero de configuracion que hemos creado y seguidamente nos vamos a la ruta /etc/apache2/sites-enabled y desactivamos el fichero de configuracion (default) y le hacemos un reload a apache con systemctl reload apache

![image](https://github.com/user-attachments/assets/7d5209f8-2bf5-40ac-b8b2-84ac47487833)


Ahora configuraremos el fichero de config php que hemos copiado a la carpeta lampdosniveles en el que modificaremos los datos y pondremos la ip de la maquina de mysq, nuestro nombre de base de datos que le hemos dado y el usuario con el password que hemos creado antes

![image](https://github.com/user-attachments/assets/a1bc1795-ec88-4a10-8b21-50e7dff979a6)

![image](https://github.com/user-attachments/assets/5a52c80f-f556-4a28-a02e-1ecb9154950c)

Ahora procederemos a poner nuestra ip del server apache y comprobamos que nos funciona
correctamente

![image](https://github.com/user-attachments/assets/387ef90e-68df-4246-b6c3-c7c7d90f1c8a)





