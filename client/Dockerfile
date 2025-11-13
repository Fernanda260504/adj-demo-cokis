#Etapa 1 (build) : Compilacion de los recursos
FROM node:20 AS build

#establecer el directorio de trabajo 
WORKDIR /app

#package-lock.json ,packge.json
COPY package*.json ./

#Funciona paragnerar el node_modules
RUN npm install 
#/client/*-> /app/*
COPY . . 

#Funciona para generar la carpeta /dist
RUN npm run build

#Etapa 2 :Construccion de la imagen 
FROM nginx:alpine 
#Servir todos los recursos generados en la etapa anterior en la imagen 

COPY --from=build /app/dist /usr/share/nginx/html

#Exponer la imagen en el puerto
EXPOSE 80

#Levantar el nginx

CMD ["nginx","-g","demon off;"]