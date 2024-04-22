- Estudiante: Daniel Pineda Vélez dpinedav@eafit.edu.co
- Estudiante: Andres leonardo Rojas alrojasp@eafit.edu.co

# 1.Breve descripción de la actividad:
Desplegar un CMS wordpress, empleando la tecnología de contenedores, con su propio dominio y certificado SSL. El sitio lo llamará: reto3.sudominio.tld.

En este reto3 utilizará un nginx COMO BALANCEADOR DE CARGAS (LB) de la capa de aplicación del wordpress o aplicación monolítica elegida.

Además de lo anterior, se utilizarán 2 servidores adicionales, uno para BASE DE DATOS (DBServer) y otro para ARCHIVOS(FileServer). El DBServer podrá utilizar la BD en docker (recomendado) o nativa. Y el FileServer implementará un NFSServer.

## 1.1 Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)

## 1.2  Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)

# 2. Información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.
Arquitectura:

![image](https://github.com/danipive/st0263-Reto3/assets/92877092/e0aef017-cea4-40e4-bc56-dde017cd785e)


# 3. Descripción del ambiente de ejecución (en producción) lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.
Dominio utilizado:
https://reto3.playlistingpro.store/

# 4. Video
