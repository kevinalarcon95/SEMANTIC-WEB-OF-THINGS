
# Práctica 2: Creando un servidor REST

***Por: Kevin Alarcón***

## **I. Instalar NodeJS y NestJS.**

1.En debian, ubuntu, raspbian, etc. Abrir la terminal y ejecutar el comando:

  ** paru -S nodejs **
  
  ![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/INstalaci%C3%B3n%20nodejs.jpg)

2.Actualizar Nodejs:

 ** 
 sudo npm cache clean -f
 sudo npm install -g n
 sudo n stable**
 
 ![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/Actualizacion%20nodejs.jpg)
 
 3.Validar las versiones instaladas, ejecute:

**sudo n stable**

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/verificar%20version.jpg)

4.Creando un espacio para los recursos globales en nodejs:
**
cd
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo "export PATH=~/.npm-global/bin:$PATH" >> ~/.bashrc
source ~/.bashrc
**
![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/Creando%20directorio.jpg)

5.Finalmente, para instalar NestJS se deben ejecutar los comandos:
**
npm i -g @nestjs/cli
source ~/.bashrc
**
![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/instalacion%20NetJs.jpg)

## **II. Ejecutando el ejemplo Hello World**
 
1. Para iniciar seleccione o cree una carpeta donde se alojará el proyecto, por ejemplo:
**
cd ~/Documents
mkdir Servidores
cd Servidores
**
![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/directorio.jpg)

2.Crear un proyecto NestJS ejecutando el comando nest new, para el nombre del proyecto no usar espacios ni caracteres especiales:

**nest new *nombre-proyecto***

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/creacion%20del%20proyecto.jpg)


