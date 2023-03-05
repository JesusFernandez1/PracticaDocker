# Despliegue de aplicaciones web

### En el fichero `docker-compose.yml` vamos a definir el escenario. El programa `docker-compose` se debe ejecutar en el directorio donde este ese fichero. 

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

### Para crear el escenario:

```sh
docker-compose up -d
```

### Para listar los contenedores:

```sh
docker-compose ps
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(218).png)

### Para parar los contenedores:

```sh
docker-compose stop        
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(219).png)

### En este caso el fichero docker-compose.yml puede tener esta forma:

```sh
version: '3.1'
services:
  frontend:
    container_name: temperaturas-frontend
    image: iesgn/temperaturas_frontend
    restart: always
    ports:
      - 80:3000
    depends_on:
      - backend
  backend:
    container_name: temperaturas-backend
    image: iesgn/temperaturas_backend
    restart: always
```

### Para crear el escenario:

```sh
docker-compose up -d
```

### Para listar los contenedores:

```sh
docker-compose ps
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(221).png)

### Para la ejecución de wordpress persistente con volúmenes docker podríamos tener un fichero docker-compose.yml con el siguiente contenido:

```sh
version: '3.1'
services:
  wordpress:
    container_name: servidor_wp
    image: wordpress
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: user_wp
      WORDPRESS_DB_PASSWORD: asdasd
      WORDPRESS_DB_NAME: bd_wp
    ports:
      - 80:80
    volumes:
      - wordpress_data:/var/www/html/wp-content
  db:
    container_name: servidor_mysql
    image: mariadb
    restart: always
    environment:
      MYSQL_DATABASE: bd_wp
      MYSQL_USER: user_wp
      MYSQL_PASSWORD: asdasd
      MYSQL_ROOT_PASSWORD: asdasd
    volumes:
      - mariadb_data:/var/lib/mysql
volumes:
    wordpress_data:
    mariadb_data:
```

### Para crear el escenario:

```sh
docker-compose up -d
```

### Para listar los contenedores:

```sh
docker-compose ps
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad5/Captura%20de%20pantalla%20(222).png)
