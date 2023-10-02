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