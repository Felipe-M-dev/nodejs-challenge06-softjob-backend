# Desafío - Soft Jobs

Para realizar este desafío debes haber estudiado previamente todo el material disponible correspondiente a la unidad.</br>
Lee todo el documento antes de comenzar el desarrollo __individual__, para asegurarte de tener el máximo puntaje y enfocar bien los esfuerzos.

- Desarrollo desafío:
    - Para la realización del desafío necesitarás apoyarte del archivo _Apoyo Desafío - Soft Jobs_
    
## Descripción

La empresa _Soft Jobs_ ha iniciado el desarrollo de una plataforma que busca apoyar a la comunidad de desarrolladores juniors a conseguir trabajos cortos y sencillos para acumular experiencia laboral y mejorar sus oportunidades.

En este desafío serás backend developer de la empresa y deberás crear un servidor para la autenticación y autorización de usuarios usando JWT.

Deberás descargar el material de apoyo en el que encontrarás una aplicación cliente desarrollada con React preparada para consumir las rutas de tu servidor.

A continuación te mostramos imágenes de la aplicación cliente disponible en el material de apoyo.

<p align="center">
  <img src="https://github.com/Felipe-M-dev/nodejs-challenge06-softjob-front/blob/main/public/softjobs01.png?raw=true" alt="challenge 06 - image 01"><br>
Imagen 1. Página de Inicio</br>
Fuente: Desafío Latam
</p>

<p align="center">
  <img src="https://github.com/Felipe-M-dev/nodejs-challenge06-softjob-front/blob/main/public/softjobs02.png?raw=true" alt="challenge 06 - image 02"><br>
Imagen 2. Registro de Usuario</br>
Fuente: Desafío Latam
</p>

<p align="center">
  <img src="https://github.com/Felipe-M-dev/nodejs-challenge06-softjob-front/blob/main/public/03.png?raw=true" alt="challenge 06 - image 03"><br>
Imagen 3. Inicio de sesión</br>
Fuente: Desafío Latam
</p>

<p align="center">
  <img src="https://github.com/Felipe-M-dev/nodejs-challenge06-softjob-front/blob/main/public/04.png?raw=true" alt="challenge 06 - image 04"><br>
Imagen 4. Mi Perfil</br>
Fuente: Desafío Latam
</p>

Para realizar este desafío necesitarás ejecutar el siguiente script sql en tu terminal ___psql___ para crear la base de datos y la tabla que utilizaremos:

```SQL
CREATE DATABASE softjobs;
\c softjobs;

CREATE TABLE usuarios ( id SERIAL, email VARCHAR(50) NOT NULL, password
VARCHAR(60) NOT NULL, rol VARCHAR(25), lenguage VARCHAR(20) );

SELECT * FROM usuarios;
```

Tu servidor debe:

- Permitir el registro de nuevos usuarios a través de una ruta __POST /usuarios__

- Ofrecer la ruta __POST /login__ que reciba las credenciales de un usuario y devuelva un __token__ generado con JWT. Se debe incluir el ___payload___ del token el ___email___ del usuario registrado.

- Disponibilizar una ruta __GET /usuarios__ para devolver los datos de un usuario en caso de que esté autenticado, para esto:
  - Extraiga un ___token___ disponible en la propiedad _Authorization_ de las cabeceras
  - Verifique la validez del token usando la misma llave secreta usada en su firma
  - Decodifique el token para obtener el ___email___ del usuario a buscar en su ___payload___
  - Obtenga y devuelva el registro del usuario

## Requerimientos

1. Registrar y obtener usuarios de la base de datos __(1.5 puntos)__
2. Usar middlewares para __(2 puntos):__</br>
a. Verificar la existencia de credenciales en la ruta que corresponda</br>
b. Validar el token recibido en las cabeceras en la ruta que corresponda</br>
c. Reportar por la terminal las consultas recibidas en el servidor</br>
3. Firmar, verificar y decodificar tokens ___JWT___ __(3 puntos)__
4. Capturar y devolver los posibles errores que ocurran en el servidor __(0.5 puntos)__
5. Encriptar las contraseñas al momento de registrar nuevos usuarios __(3 puntos)__

😊 ¡Mucho éxito!
