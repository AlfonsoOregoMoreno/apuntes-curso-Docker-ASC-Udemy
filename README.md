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

### **Asignar nombres y hacerlos interactivos** 
`docker run -it debian bash`  

**NOTA:** los SSOO de los containers no son completos. Podemos comprobar que le faltarán muchos comandos/paquetes.  

`docker run -it --name miconten debian bash`  

### **Dejar en 2º plan, obtener info; ayuda y stop** 
`docker run -d httpd` (Apache)  
`docker inspect <hash>` (info en JSON) 
`docker inspect <nombre>`  

`docker stop <hash | nombre>`  

`docker --help`  

`docker <comando> --help` 
> Ej.: `docker run --help` 



