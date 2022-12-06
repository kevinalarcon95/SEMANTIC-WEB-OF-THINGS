# Práctica 3: Seguridad y calidad

*Por Kevin Alarcón*

## Desarrollo de la práctica

## I. Arquitectura hexagonal

1. Cree una rama llamada hexagonal a partir de master partiendo del código . Es posible hacerlo con el siguiente comando:

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen1.jpg)

2. Modifique el código para que se aplique la arquitectura hexagonal.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen2.jpg)

3. Es momento de migrar la funcionalidad implementada en el controlador a un servicio.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen3.jpg)

4. Modificar el controlador player.controller.ts para que se emplee el la implementación del servicio.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen4.jpg)

## II. Implementado seguridad

1. Instalar el paquete @nestjs/passport y passport, que permitirá implementar la autenticación y autorización.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen5.jpg)

2. NestJS integra un método para generar módulos rápidamente, primero se creará un módulo para autenticación.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen6.jpg)

3. Asi mismo se creará un módulo para gestionar usuarios con los comandos:

~~~
nest g module users

nest g service users
~~~

4. Enpoint POST del servidor.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen7.jpg)

Link del repositorio: https://github.com/kevinalarcon95/UC_Practicas_IoT_Servidor/tree/seguridad

## III. Autenticación con JWT

1. Para implementar la autenticación con JWT se debe instalar el paquete @nestjs/jwt.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen8.jpg)

2. Generar Token.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen9.jpg)

3. Proteja los endpoints que tengan capacidad de modificar o eliminar registros.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen10.jpg)

4. Evidencia del funcionamiento de los endpoints protegidos.

![](https://github.com/kevinalarcon95/SEMANTIC-WEB-OF-THINGS/blob/main/Practica%203/Imagenes/imagen11.jpg)

Link del repositorio: https://github.com/kevinalarcon95/UC_Practicas_IoT_Servidor/tree/JWT

