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

```sh
docker network create red_wp
```

Para ejecutar los contenedores:

```sh
docker run -d --name servidor_mysql \
                --network red_wp \
                -v /opt/mysql_wp:/var/lib/mysql \
                -e MYSQL_DATABASE=bd_wp \
                -e MYSQL_USER=user_wp \
                -e MYSQL_PASSWORD=asdasd \
                -e MYSQL_ROOT_PASSWORD=asdasd \
                mariadb
                
docker run -d --name servidor_wp \
                --network red_wp \
                -v /opt/wordpress:/var/www/html/wp-content \
                -e WORDPRESS_DB_HOST=servidor_mysql \
                -e WORDPRESS_DB_USER=user_wp \
                -e WORDPRESS_DB_PASSWORD=asdasd \
                -e WORDPRESS_DB_NAME=bd_wp \
                -p 80:80 \
                wordpress
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(216).png)



#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad4/Captura%20de%20pantalla%20(217).png)

