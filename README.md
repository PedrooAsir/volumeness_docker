# volumeness_docker

# P2 - Volúmenes en Docker

1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.
“docker pull httpd” y para ver si se descargó: “docker image list”

2. / 3. Crea un contenedor con el nombre 'asir_httpd' y mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.
Para crearlo con dicho nombre “docker run -dit --name asir_httpd -p 8000:80 httpd”.

Una vez creado el contenedor nuevo, lo comprobamos con “docker ps”, que es donde se listan los contenedores creados

El “-p 8000:80” es para mapear los puertos


4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas

Utilizar -v "$PWD"/htdocs:/usr/local/apache2/htdocs/

Es el mismo comando que los anteriores pasos pero esta vez le añadimos un parámetro más: “docker run -dit --name asir_httpd -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd”


5. Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.
Yo usé el puerto 8080. En la carpeta que se crea automáticamente una vez hecho el paso anterior, dentro de ella creamos el fichero html. 
Para acceder → http://localhost:85r6080/prueba.html


6. Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000.

Ponemos el siguiente comando: “docker run -dit --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd:2.4”

Para comprobarlo → http://localhost:8000/pruebaej6.html


7. Utiliza Code para hacer un hola mundo en html.

Mismo comando anterior.


8 .Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.

Mismo comando anterior pero esta vez con el puerto 9080: “docker run -dit --name asir_web1 -p 9080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd:2.4”


→ http://localhost:9080/ → Al ser del mismo directorio, te aparecerá el de otro puerto también junto al que se puso ahora. 


9. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:

http://localhost:9080 
http://localhost:8000
Da igual cual pongamos pero ambos servidores sirven. Es decir, pongas el puerto que pongas de estos 2, te aparecerán los 2 en la misma página:





10. Tienen que salir la misma página web.
Es el ejercicio anterior.


# volumenes_docker
