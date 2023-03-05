# Despliegue de aplicaciones web

```sh
docker network create red_guestbook
```

Para ejecutar los contenedores:

```sh
docker run -d --name redis --network red_guestbook -v /opt/redis:/data redis redis-server --appendonly yes


docker run -d -p 80:5000 --name guestbook --network red_guestbook iesgn/guestbook
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(214).png)

```sh
docker network create red_temperaturas
```

Para ejecutar los contenedores:

```sh
docker run -d --name temperaturas-backend --network red_temperaturas iesgn/temperaturas_backend

docker run -d -p 80:3000 --name temperaturas-frontend --network red_temperaturas iesgn/temperaturas_frontend
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(215).png)



#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(216).png)



#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(217).png)

