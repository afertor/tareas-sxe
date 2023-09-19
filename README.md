# Practica Docker


### 1. Instalar ubuntu.
Para instalar la imagen de ubuntu utilizaremos el comando `docker run -it ubuntu`` al ejecutar este comando se buscara si tenemos la imagen descargada y si no lo esta se descargará automaticamente.

Para comprobar que lo tenemos descargado utilizaremos el comando `docker images ls -a` y ahi se nos mostrara todas las imagenes que hay descargadas y nos tendría que salir algo similar a lo siguiente:
|REPOSITORY|TAG|IMAGE ID|CREATED|SIZE|
|------|------|------|------|------|
|ubuntu|latest|c6b84b685f35|4 weeks ago|77.8MB|

