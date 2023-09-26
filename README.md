# pr-ctica-2-vol-menes

Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Para ello pondremos “docker pull httpd” y ya se empezará a descargar y lo podemos comprobar con el comando “docker image list”.


Crea un contenedor con el nombre 'asir_httpd'.
Para ello pondremos el siguiente comando:
docker run -dit --name asir_httpd -p 8000:80 httpd
Y se nos creará el contenedor nuevo, para comprobarlo pondremos el siguiente comando “docker ps -a”


Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.


En el comando anterior ya quedaría mapeado 










Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.


Para ello utilizaremos este comando pero con un plus “docker run -dit --name asir_httpd -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd”
Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.
En la carpeta “htdocs” creamos un “html” y comprobamos en el navegador que está creado. En mi caso utilicé el puerto 8000 y en el navegador se verá con “localhost:8000”
















Cambia el nombre a  'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000


Para cambiar el nombre es necesario borrar el anterior contenedor ya que un contenedor creado no se le puede cambiar el nombre
docker run -dit --name asir_web1 -p 8000:80 -v /home/asir2/Apache/página:/usr/local/apache2/htdocs httpd:2.4


7,8,9.  Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.


Creamos otro contenedor con la misma ruta de la carpeta pero con el puerto 9080 con el siguiente comando
docker run -dit --name asir_web2 -p 9080:80 -v ”$PWD” :/usr/local/apache2/htdocs httpd:2.4


Si desde el buscador lo hacemos con los distintos puertos sale el mensaje de HTML.

