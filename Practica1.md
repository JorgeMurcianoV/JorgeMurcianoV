# Logs Centralizados 
## Introducción
>El trabajo del administrador de sistemas puede verse simplificado entralizando los logs (registros del sistema)
## Desarrollo
>La práctica consta de dos partes: la parte de servidor y la parte de cliente.

#### Servidor

>>Para la parte de servidor necesitamos ubicarnos dentro del directorio **etc**. Esto lo haremos con el comando ```cd /etc``` para entrar al directorio. <p> Dentro del directorio **etc** editaremos el fichero **rsyslog.conf** añadiendo la siguiente linea: <p>```$template Remotelogs, "/var/logg/%HOSTNAME%/RemoteLog.log" *.* ?```

#### Cliente

>>Para la parte de cliente tenemos que editar el archivo **rsyslog.conf** que se encuentra dentro de la carpeta **etc**. <p>Esto lo haremos con el comando ```cd /etc``` para entrar a la carpeta **etc**. Dentro ya de la carpeta **etc** editamos el archivo **rsyslog.conf** con el editor que deseemos. <p>Dentro del archivo **rsyslog.conf** añadiremos esta linea:  <p>```*.* @@192.168.82.153:154``` <p> Al añadir esta línea en el archivo **rsyslog.conf** podremos comprobar que todo funciona con la herramienta **logger**  <p> Para usar la herramienta **logger** simplemente usaremos este comando despues de editar el archivo **rsyslog.conf**: <p>```logger "Hola Servidor"``` 


