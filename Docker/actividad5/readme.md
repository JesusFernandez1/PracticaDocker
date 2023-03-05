# Despliegue de aplicaciones web

En el fichero `docker-compose.yml` vamos a definir el escenario. El programa `docker-compose` se debe ejecutar en el directorio donde este ese fichero. 

```sh
version: '3.1'
services:
  app:
    container_name: guestbook
    image: iesgn/guestbook
    restart: always
    ports:
      - 80:5000
  db:
    container_name: redis
    image: redis
    restart: always
```

Para crear el escenario:

```sh
docker-compose up -d
```

### Para listar los contenedores:

```sh
docker-compose ps
          
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(218).png)

### Ejecutamos un contenedor hello-world y le damos el nombre “myhello1”, repetimos lo mismo con myhello2” y “myhello3”

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(219).png)

### Mostramos los contenedores que se están ejecutando

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(220).png)

### Tendriamos que parar los contenedores 1 y 2, pero al haberlos creado ya estan parados(el comando para pararlo seria docker stop "myhello1")

### Borramos el contenedor "myhello1”

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(221).png)

### Mostramos los contenedores que se están ejecutando

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(222).png)
