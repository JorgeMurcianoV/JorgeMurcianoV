# RAID 10 y LVM
## Introducción
>En esta práctica hemos creado un RAID 10 
## Desarrollo
> ### RAID 10
> Despues de instalar los discos para montar el RAID 10 crearemos un RAID 1 con dos de los discos.
> Para montar el RAID 1 usaremos el siguiente comando: <p> ```mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/sdb /dev/sdc``` <p> Despues de crear el **RAID 1** montaremos otro RAID 1 con otros dos discos. Una vez creados ambos RAID 1 podemos añadir a cada RAID otro disco como **spare**(de repuesto) para cuando falle un disco de los del RAID entre el disco de repuesto y no falle el funcionamiento del RAID. Esto lo haremos con el siguiente comando: <p>```mdadm --add /dev/md0 /dev/sdf```<p> Una vez añadidos los discos de repuesto montaremos un **RAID 0** con los dos **RAID 1** para acabar de montar el **RAID 10**. Para ello usaremos el siguiente comando: <p>``` mdadm --create /dev/md10 --level=0 --raid-devices=2 /dev/md0 /dev/md1``` <p>Una vez hecho esto ya tendriamos el **RAID 10** montado.
>
> ### PVM Y LVM 
> Primero creamos un volumen físico de la RAID 10 con el comando: <p> ```pvcreate /dev/md125``` <p> Una vez creado el volumen físico y hemos comprobado que esta activo con el comando ```pvs``` o  ```pvscan``` crearemos un grupo de volumenes con el siguiente comando: <p>```vgcreate VGData000 /dev/md125``` <p> Una vez creado

## Comprobación