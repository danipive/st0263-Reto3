- Estudiante: Daniel Pineda Vélez dpinedav@eafit.edu.co
- Estudiante: Andres leonardo Rojas alrojasp@eafit.edu.co

## Profesor
Edwin Nelson Montoya Munera emontoya@eafit.edu.co

# 1.Breve descripción de la actividad:
Desplegar un CMS wordpress, empleando la tecnología de contenedores, con su propio dominio y certificado SSL. El sitio lo llamará: reto3.sudominio.tld.

En este reto3 utilizará un nginx COMO BALANCEADOR DE CARGAS (LB) de la capa de aplicación del wordpress o aplicación monolítica elegida.

Además de lo anterior, se utilizarán 2 servidores adicionales, uno para BASE DE DATOS (DBServer) y otro para ARCHIVOS(FileServer). El DBServer podrá utilizar la BD en docker (recomendado) o nativa. Y el FileServer implementará un NFSServer.

## 1.1 Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
- Se implementó un balanceador de cargas basado en nginx que recibe el tráfico web https de Internet con múltiples instancias de procesamiento.
- Aplicación wordpress dockerizada monolítica en varios nodos que mejora la disponibilidad de esta.
- Se tiene 2 instancias de procesamiento wordpress detrás del balanceador de cargas.
- Se tiene 1 instancia de bases de datos mysql
- Se tiene 1 instancia de archivos distribuidos en NFS.
## 1.2  Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)

# 2. Información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.
Arquitectura:

![image](https://github.com/danipive/st0263-Reto3/assets/92877092/e0aef017-cea4-40e4-bc56-dde017cd785e)


# 3. Descripción del ambiente de ejecución (en producción) lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.
- Dominio utilizado: https://reto3.playlistingpro.store/
- Load Balancer: 107.23.215.188 (ip publica)
- Wordpress1: 10.0.0.135 (ip privada)
- Wordpress2:  10.0.0.132 (ip privada)
- Base de datos: 10.0.0.141 (ip privada)
- NFS Server: 10.0.0.137 (ip privada)
- Bastion:  44.211.136.38 (ip publica)

  ## Descripción y configuración del proyecto
  Para hacer correr el proyecto se tiene que realizar las siguientes configuraciones en las instancias de AWS

```
*Primero se hacen los mount en los 2 wordpress
sudo mount 10.0.0.137:/var/nfs/wordpress /home/ubuntu/wordpress

*Segundo usando bastion acceder a Database con su ssh y luego ponerla a correr
sudo docker compose up

*Tercerlo y final
* Hacer sudo docker compose up a los 2 wordpress
* Hacer sudo docker compose up al LoadBalancer

```
  
  ### Instancia del Bastion
  
  ### Instancia de Load Balancer
- Del proyecto copiar los archivos docker-compose.yl y nginx.conf en la instancia del load balancer
- Configurar ngnix.conf con esta información:

  
  ### Instancia de Wordpress
  - Del proyecto copiar el archivo docker-compose.yl en la instancia del Wordpress
  - Configurar docker-compose.yl con esta información: 
  

  ### Instancia de base de datos

  ### Instancia de NFS Server

  ### Configuración del Cliente NFS en Instancias de WordPress

# 4. Video
