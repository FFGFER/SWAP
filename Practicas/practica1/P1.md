# Práctica 1 - Fernando Flores Garrido
## Paso 1: Instalación de Ubuntu Server
Instalamos Ubuntu Server en dos máquinas virtuales a la vez, instalando a su vez los servicios de SSH y LAMP en la instalación del SO.

![Máquinas funcionando](img/Screenshot_1.jpg)


## Paso 2: Configuración de red
Simulamos que nuestras máquinas se encuentran en una misma red NAT que nosotros creamos con virtualbox, adicionalmente también añadimos una tarjeta de red host-only para facilitar posibles tareas futuras, para poder acceder desde nuestro navegador en el sistema anfitrión al servidor web virtualizado.

![Creando red NAT](img/Screenshot_2.jpg)

![Asignando red NAT a las máquinas](img/Screenshot_4.jpg)

![Asignando tarjeta host-only a las máquinas](img/Screenshot_5.jpg)


## Paso 3:  Comprobando que el servidor web funciona correctamente
Seguimos el consejo que se indica en el guión y comprobamos tanto la versión de apache como si está funcionando:
> apache2 -v
> ps aux | grep apache

![Comprobación del funcionamiento del servidor web](img/Screenshot_6.jpg)


## Paso 4: Instalación de curl
Como se muestra en la siguiente imagen, curl ya está instalado por defecto en la distribución de Ubuntu Server que hemos utilizado:
> sudo apt-get install curl

![Instalando curl](img/Screenshot_7.jpg)


## Paso 5: Configuración de la tarjeta de red host-only
Configuramos la tarjeta que como hemos comentado antes, nos facilitará el acceso a nuestro servidor web desde el sistema anfitrión de las máquinas virtuales, aunque no es necesario para conseguir la conexión SSH y mediante curl como veremos más adelante dado que con la conexión por la propia red NAT esto ya es posible:
> sudo nano /etc/network/interfaces

![Configurando archivo interfaces](img/Screenshot_8.jpg)

> sudo /etc/init,d/networking restart

![Aplicando la nueva configuración](img/Screenshot_10.jpg)


## Paso 6: Creamos archivo hola.html en ambas máquinas:
> sudo nano /var/www/html/hola.html

![Creación de hola.html](img/Screenshot_11.jpg)


# Resultados:
## 1. Conexión mediante SSH:
> ssh usuario@IP

![Conexión SSH](img/Screenshot_13.jpg)

## 2. Conexión al servidor web de la otra máquina mediante curl:
> curl IP/rutaalarchivo

![Conexión mediante curl](img/Screenshot_12.jpg)









