#Para iniciar vamos a cargaar la imagen de nuestro SO,
#ya que para usar un contenedor este debe de tener un sistema donde correra nuestra
#aplicacion...
FROM alpine:3.10

#Descargaremos en primer lugar python y despues la instalacion de modulos (pip)
#para esto usaremos los paquetes que maneje alpine, que en este caso son los apk
 RUN apk add --no-cache python3-dev \
    && pip3 install --upgrade pip 

#NOTA cuando hagas el comando build en docker al nombrar el contendor este debe ser con minusculas
#para la intalacion de imagen este se divide por los pasos a realizar, por ejemplo en este documento 
#realiza 2 pasos ya que solo ejecuta FROM Y RUN, si agregaramos mas comandos serian mas pasos, al momento
#de realiza build este muestra los pasos de forma: "[1/2]" 

#Para correr la imagen creada usaremos en la termona el comando docker run -it *nombre de la imagen* /bin/sh

#Introduciremos el proyecto hecho a nuestro contenedor
#Crearemos un directorio solamente para el proyecto
WORKDIR /app

#Realizaremos el copiado del proyecto
COPY . /app

#Instalaremos los modulos que necesita nuestro proyecto
RUN pip3 --no-cache-dir install -r requirements.txt

#La carnita de todo (o la conlcucion) ejecucion de todo
CMD [ "python3", "API/APP.py"]

#Ejecucion de nuestro proyecto, en este caso usaremos el comando "docker run -it -p 7000:4000 -d apidocker"
#expliacndo rapido el publish sirve para que en el puerto inicial es el puerto donde nosotros accederemos a nuestra aplicacion
#pero la 4000 o la segunda sera el puerto que accedera nuestro contenedor

