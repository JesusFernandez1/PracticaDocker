# Despliegue de aplicaciones web

### Primero hacemos apt install docker.io

### Luego vamos a comprobar que todo funciona creando nuestro primer contenedor desde la imagen hello-world:

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(199).png)

### Si listamos los contenedores que se están ejecutando (docker ps) o docker ps -a para los que no se estan ejecutando:

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(200).png)

### Clonamos el getting-started
```sh git clone https://github.com/docker/getting-started.git```

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

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(201).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(202).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(203).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(204).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(205).png)

#### ![Image](https://github.com/JesusFernandez1/PracticaDocker/blob/main/Docker/actividad2/Captura%20de%20pantalla%20(206).png)
