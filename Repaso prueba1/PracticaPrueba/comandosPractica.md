### GENERAL
### Eliminar imagen o contendor

    docker rm -f "nombre-imagen"
    docker rm -f "nombre-contendor"
    docker rm -f "nombre-red"

### Para iniciar un contenedor o imagen

    docker start "name-contenedor"

### Inspeccionar elementos

    docker inspect "nombre-elemento"

### Detener ejecucion de imagen o contenedor

    docker stop "nombre-imagen"
    docker stop "nombre-contenedor"

### Buscar imagen o contenedor de forma especifica

    docker ps | grep "nombre-imagen"
    docker ps | grep "nombre-contenedor"




### IMAGENES
### Descargar imagen

    docker pull "nombre-imagen"

### Crear contenedor con imagen

    docker create --name "nombre-contenedor" "nombre-imagen"




### CONTENEDORES
### Crear contenedor con imagen sin enlazarse al mismo 

    docker run --name "nombre-contenedor" "nombre-imagen":version

### Crear contenedor con imagen enlazandose al mismo 

    docker run -d --name "nombre-contenedor" "nombre-imagen":version

### Visualizar los contenedores que se estan ejecutando

    docker ps

### Visualizar todos los contenedores ejecutandose o no

    docker ps -a



### COMPUESTOS
### Crear contenedor con mapeo de puertos

    docker run -d --name "nombre-contenedor" --publish published= "puerto-HOST", target="puerto-contenedor" "nombre-imagen":tag

    docker run -d --name "nombre-contenedor" -p 9090:80 "nombre-imagen":tag





### INTERACTUANDO CON EL ENTORNO
### Iniciar un shell dentro del contendor

    docker exec -it "nombre-contenedor" sh

### Revisar los LOGS del contenedor

    docker logs "nombre-contenedor"

### Crear contenedor con variables de entorno

    docker run -d --name "nombre-contenedor" -e nombreVariable=valor -e nombreVariable=valor "nombre-imagen":tag

### Crear contenedor con variables de entorno (Sin seguridad)

    docker run -d --name "nombre-contenedor" -e nombreVariable=valor -e nombreVariable=valor "nombre-imagen":tag

### Crear contenedor con variables de entorno (Mas seguridad) con ruta absoluta

    docker run -d --name "nombre-contenedor" --env-file= /escritorio/7moSemestre/construccion/fileName.txt "nombre-imagen":tag

### Crear contenedor con variables de entorno (Mas seguridad) con ruta relativa

    docker run -d --name "nombre-contenedor" --env-file= "fileName".txt "nombre-imagen":tag
