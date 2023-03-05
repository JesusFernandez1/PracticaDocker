# Despliegue de aplicaciones web

```shdocker network create red_guestbook
```

Para ejecutar los contenedores:

```sh
docker run -d --name redis --network red_guestbook -v /opt/redis:/data redis redis-server --appendonly yes


docker run -d -p 80:5000 --name guestbook --network red_guestbook iesgn/guestbook
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(214).png)

### Ejecutamos un contenedor hello-world y le damos el nombre “myhello1”, repetimos lo mismo con myhello2” y “myhello3”

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(215).png)

### Mostramos los contenedores que se están ejecutando

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(216).png)

### Tendriamos que parar los contenedores 1 y 2, pero al haberlos creado ya estan parados(el comando para pararlo seria docker stop "myhello1")

### Borramos el contenedor "myhello1”

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(217).png)

