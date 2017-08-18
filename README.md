Estamos en el proceso de crear un sistema de autenticación, y necesitamos tu
ayuda para terminar de implementarlo.

El sistema funciona de la siguiente manera:

Un usuario realiza un request a nuestro servidor, dentro del cual envía el
header personalizado permiso con el valor soy-un-token-secreto.

El servidor recibe el request y revisa si contiene el header permiso con el
valor esperado.

En caso de que la condición anterior se cumpla el servidor le permite al
cliente entrar a nuestra zona privada. En caso contrario le niega el acceso.

Hasta este momento ya tenemos listo el comando mediante el cual el usuario
podrá hacer el request autenticado, el cual es el siguiente:

curl -XGET -H "permiso: soy-un-token-secreto" "http://localhost:4567/"
(Todo este comando es una linea completa no dos separadas)

Para correr este comando solo copia y pegalo en tu terminal y dale enter.
No olvides tener tu servidor de Sinatra prendido para que este pueda responder.

NOTA: Si estas en windows es necesario que instales curl en tu computador.
Para esto ve a la pagina de descarga de curl Download Curl y descarga el
Download Wizard el cual te guiara durante la instalación.

Tu mision sera implementar toda la logica que vive en el servidor.
El reto estará completó una cuando realizes un request desde la terminal
con el comando anterior y recibas un respuesta del servidor diciendo Si lo
logramos! significando que validamos correctamente el header personalizado,
en cambio si intentamos ingresar a travez del navegador a la URL
http://localhost:4567/ deberíamos recibir un mensaje que diga Sin
Permiso dado que un request a travez del navegador no contiene nuestro
header personalizado el cual nos da acceso.
