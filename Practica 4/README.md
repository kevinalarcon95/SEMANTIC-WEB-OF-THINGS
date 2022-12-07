# Práctica 4: Desplegando en la nube

* Por Kevin Alarcón:

## Desarrollo de la práctica

## I. Desplegar una aplicación en la nube

1. Descargar deta ejecutando en la terminal:

~~~
 curl -fsSL https://get.deta.dev/cli.sh | sh
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen1.jpg)

2. Agregando la variable de entorno:

~~~
  echo "export PATH=~/.deta/bin:$PATH" >> ~/.bashrc
  
  source ~/.bashrc
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen2.jpg)

3. Iniciar sesión en Deta ejecutando en la terminal:

~~~
  deta login
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen3.jpg)

4. Crear un punto de entrada de la aplicación. El archivo src/index.ts debe quedar de la siguiente forma:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen4.jpg)

5. En la raíz del proyecto crear un nuevo archivo index.js con el siguiente contenido:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen6.jpg)

6. Antes de publicar debemos compilar el proyecto. Para ello ejecutamos en la terminal:

~~~
  cd ~/Documents/Servidores/practica_02
  nest build
~~~

7. Publicar la aplicación ejecutando en la terminal:

~~~
deta new --node 
~~~

![]()

8. Para actualizar la aplicación ejecutamos en la terminal:

~~~
  deta update
~~~


![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen7.jpg)

9. Para desplegar la aplicación ejecutamos en la terminal:

~~~
deta deploy 
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen8.jpg)

10. Para activar los logs de la aplicación ejecutamos en la terminal:

~~~
deta visor enable
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen9.jpg)

11. Para obtener la url del servicio visite el panel de control de Deta en la sección de micros. https://web.deta.sh/micros. Ahí encontrará en micros una opción con el nombre del proyecto, al abrirlo encontrará la url del servicio.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen10.jpg)

Para el ejemplo se obtuvo la url https://saae0q.deta.dev/, al visitarla debería obtener la respuesta implementada en el método get de su servicio:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen11.jpg)

link del repositorio: https://github.com/kevinalarcon95/UC_Practicas_IoT_Servidor/tree/DETA

## 2. Conectado a una base de datos

1. Instalar las dependencias de TypeORM y MongoDB.

~~~
  npm install --save @nestjs/typeorm typeorm mongodb
~~~

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen12.jpg)

2. URL mongo.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen13.jpg)

3. Modifique el archivo src/app.module.ts.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/573737a23e8276424977e2ed7f4066576078464d/Practica%204/Imagenes/imagen15.jpg)

4. Cree un archivo para modelar la entidad.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen16.jpg)

5. Es necesario modificar los métodos para que utilicen el repositorio.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen17.jpg)

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen18.jpg)

Nota: También fue necesario modificar los archivos de tablets.controller.ts y tabletsImpl.controller.ts para que usaran la entidad creada anteriormente.

7. Finalmente, si se ejecuta el proyecto localmente con npm run start:dev, ejecute un POST para crear un nuevo elemento. Si la respuesta es satisfactoria y si al ejecutar el GET se recupera el elemento creado, entonces la conexión con la base de datos fue exitosa.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%204/Imagenes/imagen19.jpg)

NOTA: Como se puede observar a la hora de ejecutar el servidor aparece un error para conectarse con Mongo, intente solucionar este error revisando que la URL de conexión estuviera correctamente el usuario y el pass. También validé la conexión a internet de la máquina. Comprobé la URL de la base de datos conectando con mongo compass. A mi criterio todo esta funcionando bien pero no logré solucionar dicho error.

Link del repositorio: https://github.com/kevinalarcon95/UC_Practicas_IoT_Servidor/tree/MongoDB


