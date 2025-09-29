# CURSO "Maneja Docker en 5 días"
### (Udemy - Antonio Sánchez Corbalán)

## DIA 1 de 5
`docker info`  
(en el cliente muestra cosas como: plugins, ...)  
(en el server muestra cosas como: containers, imágenes, URL del Registry, ...)  

`docker run debian:bullseye`  

**NOTA:** versiones --> "contenedor:tag"  
**NOTA:** ver en la Doc el caso de (slim) "Image Variant". p.e.: debian:<suite>-slim  

`docker ps` (y "docker ps -a") 
Containers en ejecución y (-a) los ya terminados tb. 

`docker images` 
Imágenes descargadas. 

**NOTA / DUDA:** ¿cómo elegir una versión concreta de debian (p.e.)? Es decir, con más detalle que solo "debian:buster".
**DUDA:** cómo cambiar el Registry al que se apunta. 


### Asignar nombres y hacerlos interactivos 
`docker run -it debian bash`  

**NOTA:** los SSOO de los containers no son completos. Podemos comprobar que le faltarán muchos comandos/paquetes.  

`docker run -it --name miconten debian bash`  


### Dejar en 2º plan, obtener info; ayuda y stop 
`docker run -d httpd` (Apache)  
`docker inspect <hash>` (info en JSON)  
`docker inspect <nombre>`  
`docker stop <hash | nombre>`  
`docker --help`  
`docker <comando> --help`  
> Ej.: `docker run --help`

**NOTA:** revisar las opciones que brindan los comandos. 


### Docker ps en más detalle 
`docker ps -l` (ver los últimos)  
`docker ps -n3` (ver los últimos 3)  
`docker ps -q` (los hashes)  
`docker ps -s` (sizes)  
`docker ps -f` (filtro; ¡¡Ver la Doc!!) 
> Ej.: `docker ps -f "name=a"` (contiene una "a" en el nombre) 

`docker ps -f "image=http"` (¡¡OJO!! esto dio error)  
`docker ps --format "{{.ID}}:{{.Command}}"` (formateo; ID y Command son campos/columnas; Ojo con la doble llave; Ver la Doc)  
(podemos poner "table" antes de las 2 primeras llaves para que salgan las cabeceras)  


### Borrar contenedores
`docker rm <hash | nombre>` (solo puede eliminar los terminados)  
`docker stop $(docker ps -q)` (detiene los arrancados ya que el comando entre paréntesis devuelve todos los IDs de los arrancados)  
`docker rm $(docker ps -aq)` (Elimina todos, absolutamente todos)  


### Ejecutar programas en el contenedor 
`docker exec <ID> bash` (OJO, requiere que se esté ejecutando)  
`docker run -di debian` (detached e intractivo)  
`docker exec <ID> uname -a` (ejecuta el comando "uname -a")  
`docker exec -it <ID> bash` (ejecuta bash en el container y entra al terminal)  


### Copiar datos al container y viceversa 

