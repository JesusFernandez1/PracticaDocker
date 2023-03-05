# Despliegue de aplicaciones web

### Descargamos la imagen de ubuntu, hello-world y nginx ademas de mostrar un listado de todas la imágenes

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(208).png)

### Ejecutamos un contenedor hello-world y le damos el nombre “myhello1”, repetimos lo mismo con myhello2” y “myhello3”

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(209).png)

### Clonamos el getting-started
```sh 
git clone https://github.com/docker/getting-started.git

```

### En el directorio app, la misma ubicación que el archivo package.json, creamos un archivo que se llame Dockerfile poniendo dentro lo siguiente.

```sh
# syntax=docker/dockerfile:1
   
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```
#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(210).png)

```sh 
docker build -t getting-started
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(211).png)
```sh 
docker run -dp 3000:3000 getting-started
```

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(212).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad3/Captura%20de%20pantalla%20(213).png)
