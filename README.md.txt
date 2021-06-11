##Instalaci�n
Primero, nuestra carpeta del proyecto debe estar en la siguiente ruta:
```bash
C:\xampp\htdocs\
```
El siguiente paso es configurar los siguientes archivos para poder visualzar la p�gina.
##Archivo *httpd-vhosts*
El primer archivo a editar se encuentra en la siguiente ruta:
```bash
C:\xampp\apache\conf\extra\httpd-vhosts
```
Lo abrimos con el editor de c�digo de nuestra preferencia, en mi caso VS.
Al final del documento agregamos el siguiente c�digo sustituyendo "carpeta" por el nombre de tu carpeta.
```conf
<VirtualHost *:80>
    ServerAdmin example2.com
    DocumentRoot "C:/xampp/htdocs/example2.com/public"
    ServerName example2.com
    ErrorLog "logs/example2.com-error.log"
    CustomLog "logs/example2.com-access.log" common
    <Directory "C:/xampp/htdocs/example2.com/public">
        Options All
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
##Archivo *hosts*
El segundo archivo a editar est� en la ruta:
```bash
C:\Windows\System32\drivers\etc\hosts
```
Agregamos la siguiente l�nea al final del archivo:
```config
	127.0.0.1       example2.com
``` 
##Configuraci�n de archivos internos
Para que el proyecto funcione correctamente hay que cambiar todo lo que diga example2.com de cada archivo del proyecto por el nombre de la carpeta en la que est�n tus archivos.

Guardamos los archivos y abrimos el panel de control de Xampp para encender Apache y MySQL.
Cuando estos est�n encendidos,vamos a nuestro navegador y colocamos el nombre de la carpeta donde se encuentra el proyecto y damos entrar.

Listo, ya tenemos nuestro proyecto de forma local.
