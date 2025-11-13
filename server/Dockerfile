#Servir la imagen del backend co maven 
 FROM maven:3.9.9-eclipse-termuri-21

 #Establecer el directoprio de trabajo
  WORKDIR  /app

  #Copia todos los archivos del proyecto  en el directorio del trabajo 
   COPY . .

   #Ejecutar 2 comandos 
   #1.-Limpiar y controlar el jar del backend
   #2.-Copiar el jar resultante al directorio de trabajo
   RUN mvn clan package -DskipTests && cp target/*.jar app.jar

   #Exponer la imagen en el puerto
   EXPOSE 8081

   #Ejecutar el comando par servir el jar
   ENTRYPOINT [ "java","-jar","app.jar" ]