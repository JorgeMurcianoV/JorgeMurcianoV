# Política de contraseñas

## Introducción

>La seguridad de nuestro sistema puede verse amenazada. Una buena política de contraseñas reformaría la seguridad.

>El objetivo de la práctica es entender y configurar las directrices de seguridad. Para ello utilizaremois el módulo **pam pw_password**

## Desarrollo

>* Instalación
  >>Para comprobar y modificar los archivos donde se configura la política de contraseñas debemos instalar varios archivos. Esto lo haremos con el siguiente comando: <p>```sudo apt install -y libpam-pwquality libpwquality-tools``` <p>Estos archivos son programas para comprobar el nivel de seguridad de las contraseñas que ponemos.

>* Configuración 
    >> Para configurar la política de contraseñas modificaremos el archivo **/etc/security/pwquality.conf**. <p>En este archivo podremos modificar varias opciones que deben cumplir las contraseñas como: 
    >>- **difok**: número de carácteres de la nueva contraseña que no deben aparecer en la antigua contraseña.
    >>- **minlen**: mínimo de carácteres que ha de tener la nueva contraseña.
    >>- **dcredit**: Crédito máximo por tener dígitos en la nueva contraseña.
    >>- **ucredit**: Crédito máximo por tener letras mayúsculas en la nueva contraseña.
    >>- **lcredit**: Crédito máximo por tener letras minúsculas en la nueva contraseña.
    >>- **ocredirt**: Crédito máximo por tener otros caracteres en la nueva contraseña.
    >>- **minclass**: Número mínimo de clases de caracteres requeridas para la nueva contraseña
    >>- **maxrepeat**: Número máximo de caracteres repetidos.
    >>- **maxclassrepeat**: Número máximo de caracteres consecutivos de la misma clase.
## Comprobación
>Para comprobar el nivel de seguridad de nuestra contraseña podemos usar el siguiente comando: <p>```echo contraseña | pwscore``` <p>Con este comando poniendo la contraseña que queramos nos dirá si esta no cumple los requesitos que hemos puesto modificando el archivo **/etc/security/pwquality.conf** y si cumple los requesitos que hemos puesto nos devolverá un número del 0 al 100 dependiendo de lo segura que sea nuestra contraseña. <p>Como por ejemplo:<p>
![tux]()