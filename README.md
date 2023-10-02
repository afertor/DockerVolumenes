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
 
|CONTAINER ID NAMES|IMAGE|COMMAND|CREATED|STATUS|PORTS|
|------|------|------|------|------|------|
|911e50d1f453 dam_web1|httpd:2.4|"httpd-foreground"| About a minute ago|Up About a minute |



<br>