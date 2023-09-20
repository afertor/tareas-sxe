# Practica Docker


### 1. Instalar ubuntu.
Para instalar la imagen de ubuntu utilizaremos el comando `docker run -it ubuntu`` al ejecutar este comando se buscara si tenemos la imagen descargada y si no lo esta se descargará automaticamente.

Para comprobar que lo tenemos descargado utilizaremos el comando `docker images ls -a` y ahi se nos mostrara todas las imagenes que hay descargadas y nos tendría que salir algo similar a lo siguiente:
|REPOSITORY|TAG|IMAGE ID|CREATED|SIZE|
|------|------|------|------|------|
|ubuntu|latest|c6b84b685f35|4 weeks ago|77.8MB|

<br></br>
### 2. Creación de contenedor sin nombre.
Para esto escribiremos el comando `docker run -it ubuntu` y el contenedor se encenderá y generará un nombre aleatorio. Para comprobar que esta encendido pondremos el comando `docker ps -a` en otra ventana diferente y nos debería aparecer lo siguiente:

|CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES|
|------|------|------|------|------|------|------|
|3bf6b126e984|ubuntu|"/bin/bash" |8 minutes ago|Exited (0) 8 minutes ago||vibrant_robinson|

<br></br>


### 3. Crear contenedor con nombre.
Para crear un contenedor con nombre usaremos el siguiente comando `docker run -it --name dam_ubu1 ubuntu` y al crearse ya podríamos acceder a el contenedor agregandole -it. Si el contenedor se apaga utilizaremos el comando `docker start "nombre_contenedor"` y asi podremos acceder al contenedor.

Al ejecutar el comando `docker ps` nos debería aparecer lo siguiente despues de crear el contenedor y si este esta en funcionamiento:

|CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES|
|------|------|------|------|------|------|------|
|9eef3231d55f|ubuntu|"/bin/bash"|9 seconds ago|Up 8 seconds||dam_ubu2|


<br></br>

### 4. Comprobación de la ip y ping a google.
a) Lo primero que debemos hacer es estar dentro del contenedor. Una vez dentro escribiremos el comando `apt update` este comando actualiza la lista de paquetes. Despues pondremos `apt install net-tools` para descargar el paquete de net-tools y por ultimo utilizaremos `ipconfig` y ahí podremos ver la ip.

b) Para poder comprobar si podemos hacer un ping a google.com primero tendremos que instalar el paquete con el siguiente comando `apt install iputils-ping` esto descargará el paquete para poder hacer el ping. 
Ahora para hacer el ping usaremos este comando `ping google.com` y así es como se haría un ping a google.com y para pararlo usariamos Ctrl+C, al pararlo te mostrará un resumen del ping.


<br></br>


 ### 5. Creación de contenedor con nombre y ping entre contenedores.
 Para crear el contenedor usaremos el mismo comando que usamos previamente `docker run -it --name dam_ubu2 ubuntu`.
 Haremos la instalación de los paquetes con los siguientes comandos `apt update`,`apt install net-tools`, `apt install iputils-ping`. Ahora que estan instalados los paquetes en los dos contenedores usaremos el comando `ping 172.17.0.3` (la ip del comando es la ip del contenedor al cual le quieres hacer el ping)

