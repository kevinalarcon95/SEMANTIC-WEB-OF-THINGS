
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

3.Es necesario identificar la dirección IP de la máquina, para esto se puede ejecutar el comando:

**hostname -I**
Nota: En este caso se utilizó el comando ifconfig para conocer la ip de la maquina.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/ip%20de%20la%20maquina.jpg)

4.Node utiliza el archivo package.json para definir los scripts que se ejecutan con el comando npm run o yarn run. 

**
cd practica_02
npm run start:dev
**

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/package.jpg)

Para verificar los scripts disponibles, se puede ejecutar el comando:

**cat package.json**

~~~
{
  "name": "practica_02",
  "version": "0.0.1",
  "description": "",
  "author": "",
  "private": true,
  "license": "UNLICENSED",
  "scripts": {
    "prebuild": "rimraf dist",
    "build": "nest build",
    "format": "prettier --write \"src/**/*.ts\" \"test/**/*.ts\"",
    "start": "nest start",
    "start:dev": "nest start --watch",
    "start:debug": "nest start --debug --watch",
    "start:prod": "node dist/main",
    "lint": "eslint \"{src,apps,libs,test}/**/*.ts\" --fix",
    "test": "jest",
    "test:watch": "jest --watch",
    "test:cov": "jest --coverage",
    "test:debug": "node --inspect-brk -r tsconfig-paths/register -r ts-node/register node_modules/.bin/jest --runInBand",
    "test:e2e": "jest --config ./test/jest-e2e.json"
  },
  "dependencies": {
    "@nestjs/common": "^9.0.0",
    "@nestjs/core": "^9.0.0",
    "@nestjs/platform-express": "^9.0.0",
    "reflect-metadata": "^0.1.13",
    "rimraf": "^3.0.2",
    "rxjs": "^7.2.0"
  },
  "devDependencies": {
    "@nestjs/cli": "^9.0.0",
    "@nestjs/schematics": "^9.0.0",
    "@nestjs/testing": "^9.0.0",
    "@types/express": "^4.17.13",
    "@types/jest": "28.1.8",
    "@types/node": "^16.0.0",
    "@types/supertest": "^2.0.11",
    "@typescript-eslint/eslint-plugin": "^5.0.0",
    "@typescript-eslint/parser": "^5.0.0",
    "eslint": "^8.0.1",
    "eslint-config-prettier": "^8.3.0",
    "eslint-plugin-prettier": "^4.0.0",
    "jest": "28.1.3",
    "prettier": "^2.3.2",
    "source-map-support": "^0.5.20",
    "supertest": "^6.1.3",
    "ts-jest": "28.0.8",
    "ts-loader": "^9.2.3",
    "ts-node": "^10.0.0",
    "tsconfig-paths": "4.1.0",
    "typescript": "^4.7.4"
  },
  "jest": {
    "moduleFileExtensions": [
      "js",
      "json",
      "ts"
    ],
    "rootDir": "src",
    "testRegex": ".*\\.spec\\.ts$",
    "transform": {
      "^.+\\.(t|j)s$": "ts-jest"
    },
    "collectCoverageFrom": [
      "**/*.(t|j)s"
    ],
    "coverageDirectory": "../coverage",
    "testEnvironment": "node"
  }
}
~~~

5.Con lo anterior el servidor nos indica que está listo para recibir peticiones con el metodo GET en la ruta raíz. Por defecto el servidor escucha en el puerto 3000, para verificar esto se puede ejecutar el comando en otra terminal:

**netstat -tulpn | grep node**

La terminal responderá con la siguiente información:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/respuesta%20servidor.jpg)

Luego ya se puede probar el servidor con el comando en otra terminal:

curl http://localhost:3000

La terminal responderá con la siguiente información:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/Hello.jpg)

## **III. Publicando el código en GitHub**

Link del repositorio:

https://github.com/kevinalarcon95/UC_Practicas_IoT_Servidor.git

## **IV. Los verbos HTTP**

1. Conecte VSCode a la máquina virtual, para esto se debe seleccionar el botón Remote-SSH: Connect to Host... en la sección Remote Explorer.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/remote.jpg)

2. Comprobando funcionamiento del servidor

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/funcionamiento%20Servidor.jpg)

3. Prueba desde el navegador

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/prueba%20navegador.jpg)

4. Creando un modificador

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/mensaje%20modificado.jpg)

5. Prueba navegador (Modificador)

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%202/Practica%202/Imagenes/picacku.jpg)


