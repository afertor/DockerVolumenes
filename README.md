# Docker Volumenes

<br>

### 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Primero para descargar la imagen debemos irnos a la pagina de docker y buscar la imagen [Docker](https://hub.docker.com/search?q=). Cuando lo descarguemos podremos comprobar si se ha descargado correctamente con el siguiente comando `docker image ls -a` y nos deberia aparecer algo como esto:

|REPOSITORY|TAG|IMAGE ID|CREATED|SIZE|
|------|------|------|------|------|
|httpd|2.4|359570977af2|11 days ago|168MB|

<br> 

### 2. Crea un contenedor con el nombre 'dam_web1'.
Para crear un contenedor con el nombre dam_web1 utilizaremos el siguiente comando: `docker run -dit --name dam_web1 httpd:2.4`
Si queremos comprobar que el contenedor se ha creado correctamente utilizaremos el comando: `docker ps -a` y nos deberia mostrar algo parecido a esto:
 
|CONTAINER ID NAMES|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAME|
|------|------|------|------|------|------|------|
|911e50d1f453|httpd:2.4|"httpd-foreground"| About a minute ago|Up About a minute|80/tcp|dam_web1|


<br>

### 3. Si quieres poder acceder desde el navegador de tu equipo, ¿que debes hacer?.
Para esto debemos introducir nuestra ip en el navegador. Si no sabemos cual es podremos verla con el comando `ip a`

<br>

### 4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas. 
Primero debemos borrar el contenedor con el comando `docker rm dam_web1` (recuerda parar el contenedor antes de borrarlo) para poder montar el htdocs en el directorio que queramos.
Despues usaremos el siguiente comando `docker run -dit --name dam_web1 -p 8000:80 -v /home/dam2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs httpd:2.4` que sería el mismo que utilizamos en el ejercicio 2 solo que estariamos añadiendo -v y la ruta del directorio en el que queremos montar el htdocs.

Para comprobar que ha funcionado simplemente tendriamos que poner nustra ip en el navegador junto al puerto como por ejemplo: `localhost:8000`

<br>

### 5.Realiza un 'hola mundo' en html (usa Code) y comprueba que accedes desde el navegador.

Para realizar un hola mundo tendremos qu crear un index.html en la carpeta htdocs y escribir una estructura html como por ejemplo la siguiente: 
``` html

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>Hola mundo</h1>
    </body>
    </html>
```
<br>

### 6. Crea otro contenedor 'dam_web2' con el mismo volumen y a otro puerto, por ejemplo 9080.
Para esto utilizaremos el mismo comando que usamos en el ejercicio 4 pero cambiando el puerto es decir el comando quedaria tal que asi `docker run -dit --name dam_web2 -p 9080:80 -v /home/dam2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs httpd:2.4`

<br>

### 7. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador: 
Para comprobar que funcionan nos iremos al navegador y simplemente tendremos que escribir nuestra ip o localhost con el puerto 9080 y 8000



