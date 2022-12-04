#Práctica 1: Configuración de entorno y red

##Desarrollo de la práctica

Para dar inicio a la práctica 1, se utilizó la maquina virtual ENDEAVOUROS basada en Arch Linux debido a su flexibilidad a la hora de gestionar paquetes. A continuación se comparte una prueba del escritorio de la maquina virtual montada en el Virtual Box (v7.0.4).

#####Imagen 1.Entorno de trabajo.

![Imagen1.Entorno](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/Entorno%20de%20trabajo.jpeg)

------------
Para realizar la instalación de docker se utilizarón los siguientes comandos:

**paru -Sy docker**
**paru -Sy docker-compose**

#####Imagen 2. Instalación de docker.
![Imagen2.Instalacion docker](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/Instalaci%C3%B3n%20docker.jpeg)

------------
Comando **ip**: es una herramienta de red de Linux para administradores de sistemas y redes. IP significa Protocolo de Internet y, como su nombre indica, la herramienta se utiliza para configurar interfaces de red..

#####Imagen 3. Comando ip.
![Imagen3.ComandoIP](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/comando%20ip.jpg)

El comando **ifconfig** sirve para: 
- Mostrar información sobre la configuración de red del sistema.
- Habilitar o deshabilitar una interfaz de red.
- Cambiar la dirección MAC.
- Crear alias de interfaz de red.
- Activar o desactivar el modo promiscuo.

En este caso, solo se utilizó para poder mostrar la información de la configuración de red del sistema, en caso de realizar aplicarlo para otra funcionalidad se puede visitar el siguiente enlace [Instalar y configurar ifconfig](http://https://phoenixnap.com/kb/centos-ifconfig "Isstalar y configurar ifconfig").
#####Imagen 4. Comando ifconfig.
![Imagen4.ComandoIfconfig](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/comando%20ifconfig.jpg)

Comando **ss**: es un comando de CLI que se utiliza para mostrar las estadicticas de red. Este comando junto con el comando **ip** son escenciales para recopilar información de red y solucionar problemas de red. En la siguiente imagen se puede observar las estadisticas del servidor X11 (servidor de la interfaz grafica).

#####Imagen 5. Comando ss.
![Imagen5.ComandoSs](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/comando%20ss.jpg)

Comando **netstat**: muestra las conexiones de red (entrantes y salientes), tablas de enrutamiento y una serie de estadisticas de interfaz de red.

En la captura se puede ver los puertos que se están usando, que servicio está ocupando, el usuario y que tipo de formato. 

#####Imagen 6. Comando netstat.
![Imagen6.Comandonetstat](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/comando%20ss.jpg)

Comando **lsoft**: recupera detalladamente  varios tipos de archivos abiertos por diferentes procesos de ejecución. Estos archivos pueden ser archivos normales, directorios, archivos de bloque, sockets de red, canalizaciones con nombre, etc.

#####Imagen 7. Comando lsoft.
![Imagen7.Comandolsoft](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/comando%20lsof.jpg)

#####Imagen 7. Ejemplo comando **lsoft**
![Imagen8.Comandolsoft](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%201/Imagenes/lsof%20servicio%20web.jpg)

TCP: Es un protocolo de internet estándar para la transmisión de datos el cual utiliza validaciones es decir que cuando se envía un mensaje, es necesario que se reciba otro mensaje de confirmación.

UDP: Es un protocolo para streams, este protocolo no usa validaciones, simplemente alguien puede estar recibiendo el stream de datos o no.

El uso de estos protocolos depende del contexto en el cual se vayan a usar.
