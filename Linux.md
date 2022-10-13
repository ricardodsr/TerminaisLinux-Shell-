# Información del sistema
arch: mostrar la arquitectura de la máquina (1).
uname -m: mostrar la arquitectura de la máquina (2).
uname -r: mostrar la versión del kernel usado.
dmidecode -q: mostrar los componentes (hardware) del sistema.
hdparm -i /dev/hda: mostrar las características de un disco duro.
hdparm -tT /dev/sda: realizar prueba de lectura en un disco duro.
cat /proc/cpuinfo: mostrar información de la CPU.
cat /proc/interrupts: mostrar las interrupciones.
cat /proc/meminfo: verificar el uso de memoria.
cat /proc/swaps: mostrar ficheros swap.
cat /proc/version: mostrar la versión del kernel.
cat /proc/net/dev: mostrar adaptadores de red y estadísticas.
cat /proc/mounts: mostrar el sistema de ficheros montado.
lspci -tv: mostrar los dispositivos PCI.
lsusb -tv: mostrar los dispositivos USB.
date: mostrar la fecha del sistema.
cal 2011: mostrar el almanaque de 2011.
cal 07 2011: mostrar el almanaque para el mes julio de 2011.
date 041217002011.00: colocar (declarar, ajustar) fecha y hora.
clock -w: guardar los cambios de fecha en la BIOS.

# Apagar (Reiniciar Sistema o Cerrar Sesión)

shutdown -h now: apagar el sistema (1).
init 0: apagar el sistema (2).
telinit 0: apagar el sistema (3).
halt: apagar el sistema (4).
shutdown -h hours:minutes &: apagado planificado del sistema.
shutdown -c: cancelar un apagado planificado del sistema.
shutdown -r now: reiniciar (1).
reboot: reiniciar (2).
logout: cerrar sesión.

# Archivos y Directorios

cd /home: entrar en el directorio “home”.
cd ..: retroceder un nivel.
cd ../..: retroceder 2 niveles.
cd: ir al directorio raíz.
cd ~user1: ir al directorio user1.
cd –: ir (regresar) al directorio anterior.
pwd: mostrar el camino del directorio de trabajo.
ls: ver los ficheros de un directorio.
ls -F: ver los ficheros de un directorio.
ls -l: mostrar los detalles de ficheros y carpetas de un directorio.
ls -a: mostrar los ficheros ocultos.
ls *[0-9]*: mostrar los ficheros y carpetas que contienen números.
tree: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.(1)
lstree: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.(2)
mkdir dir1: crear una carpeta o directorio con nombre ‘dir1’.
mkdir dir1 dir2: crear dos carpetas o directorios simultáneamente (Crear dos directorios a la vez).
mkdir -p /tmp/dir1/dir2: crear un árbol de directorios.
rm -f file1: borrar el fichero llamado ‘file1’.
rmdir dir1: borrar la carpeta llamada ‘dir1’.
rm -rf dir1: eliminar una carpeta llamada ‘dir1’ con su contenido de forma recursiva. (Si lo borro recursivo estoy diciendo que es con su contenido).
rm -rf dir1 dir2: borrar dos carpetas (directorios) con su contenido de forma recursiva.
mv dir1 new_dir: renombrar o mover un fichero o carpeta (directorio).
cp file1: copiar un fichero.
cp file1 file2: copiar dos ficheros al unísono.
cp dir /* .: copiar todos los ficheros de un directorio dentro del directorio de trabajo actual.
cp -a /tmp/dir1 .: copiar un directorio dentro del directorio actual de trabajo.
cp -a dir1: copiar un directorio.
cp -a dir1 dir2: copiar dos directorio al unísono.
ln -s file1 lnk1: crear un enlace simbólico al fichero o directorio.
ln file1 lnk1: crear un enlace físico al fichero o directorio.
touch -t 0712250000 file1: modificar el tiempo real (tiempo de creación) de un fichero o directorio.
file file1: salida (volcado en pantalla) del tipo mime de un fichero texto.
iconv -l: listas de cifrados conocidos.
iconv -f fromEncoding -t toEncoding inputFile > outputFile: crea una nueva forma del fichero de entrada asumiendo que está codificado en fromEncoding y convirtiéndolo a ToEncoding.
find . -maxdepth 1 -name *.jpg -print -exec convert ”{}” -resize 80×60 “thumbs/{}” \;: agrupar ficheros redimensionados en el directorio actual y enviarlos a directorios en vistas de miniaturas (requiere convertir desde ImagemagicK).

# Encontrar archivos

find / -name file1: buscar fichero y directorio a partir de la raíz del sistema.
find / -user user1: buscar ficheros y directorios pertenecientes al usuario ‘user1’.
find /home/user1 -name \*.bin: buscar ficheros con extensión ‘. bin’ dentro del directorio ‘/ home/user1’.
find /usr/bin -type f -atime +100: buscar ficheros binarios no usados en los últimos 100 días.
find /usr/bin -type f -mtime -10: buscar ficheros creados o cambiados dentro de los últimos 10 días.
find / -name \*.rpm -exec chmod 755 ‘{}’ \;: buscar ficheros con extensión ‘.rpm’ y modificar permisos.
find / -xdev -name \*.rpm: Buscar ficheros con extensión ‘.rpm’ ignorando los dispositivos removibles como cdrom, pen-drive, etc.…
locate \*.ps: encuentra ficheros con extensión ‘.ps’ ejecutados primeramente con el command ‘updatedb’.
whereis halt: mostrar la ubicación de un fichero binario, de ayuda o fuente. En este caso pregunta dónde está el comando ‘halt’.
which halt: mostrar la senda completa (el camino completo) a un binario / ejecutable.

# Montando un sistema de ficheros

mount /dev/hda2 /mnt/hda2: montar un disco llamado hda2. Verifique primero la existencia del directorio ‘/ mnt/hda2’; si no está, debe crearlo.
umount /dev/hda2: desmontar un disco llamado hda2. Salir primero desde el punto ‘/ mnt/hda2.
fuser -km /mnt/hda2: forzar el desmontaje cuando el dispositivo está ocupado.
umount -n /mnt/hda2: correr el desmontaje sin leer el fichero /etc/mtab. Útil cuando el fichero es de solo lectura o el disco duro está lleno.
mount /dev/fd0 /mnt/floppy: montar un disco flexible (floppy).
mount /dev/cdrom /mnt/cdrom: montar un cdrom / dvdrom.
mount /dev/hdc /mnt/cdrecorder: montar un cd regrabable o un dvdrom.
mount /dev/hdb /mnt/cdrecorder: montar un cd regrabable / dvdrom (un dvd).
mount -o loop file.iso /mnt/cdrom: montar un fichero o una imagen iso.
mount -t vfat /dev/hda5 /mnt/hda5: montar un sistema de ficheros FAT32.
mount /dev/sda1 /mnt/usbdisk: montar un usb pen-drive o una memoria (sin especificar el tipo de sistema de ficheros).

# Espacio de Disco

df -h: mostrar una lista de las particiones montadas.
ls -lSr |more: mostrar el tamaño de los ficheros y directorios ordenados por tamaño.
du -sh dir1: Estimar el espacio usado por el directorio ‘dir1’.
du -sk * | sort -rn: mostrar el tamaño de los ficheros y directorios ordenados por tamaño.
rpm -q -a –qf ‘%10{SIZE}t%{NAME}n’ | sort -k1,1n: mostrar el espacio usado por los paquetes rpm instalados organizados por tamaño (Fedora, Redhat y otros).
dpkg-query -W -f=’${Installed-Size;10}t${Package}n’ | sort -k1,1n: mostrar el espacio usado por los paquetes instalados, organizados por tamaño (Ubuntu, Debian y otros).

# Usuarios y Grupos

groupadd nombre_del_grupo: crear un nuevo grupo.
groupdel nombre_del_grupo: borrar un grupo.
groupmod -n nuevo_nombre_del_grupo viejo_nombre_del_grupo: renombrar un grupo.
useradd -c “Name Surname ” -g admin -d /home/user1 -s /bin/bash user1: Crear un nuevo usuario perteneciente al grupo “admin”.
useradd user1: crear un nuevo usuario.
userdel -r user1: borrar un usuario (‘-r’ elimina el directorio Home).
usermod -c “User FTP” -g system -d /ftp/user1 -s /bin/nologin user1: cambiar los atributos del usuario.
passwd: cambiar contraseña.
passwd user1: cambiar la contraseña de un usuario (solamente por root).
chage -E 2011-12-31 user1: colocar un plazo para la contraseña del usuario. En este caso dice que la clave expira el 31 de diciembre de 2011.
pwck: chequear la sintaxis correcta el formato de fichero de ‘/etc/passwd’ y la existencia de usuarios.
grpck: chequear la sintaxis correcta y el formato del fichero ‘/etc/group’ y la existencia de grupos.
newgrp group_name: registra a un nuevo grupo para cambiar el grupo predeterminado de los ficheros creados recientemente.

# Permisos en Ficheros (Usa ”+” para colocar permisos y ”-” para eliminar)

ls -lh: Mostrar permisos.
ls /tmp | pr -T5 -W$COLUMNS: dividir la terminal en 5 columnas.
chmod ugo+rwx directory1: colocar permisos de lectura ®, escritura (w) y ejecución(x) al propietario (u), al grupo (g) y a otros (o) sobre el directorio ‘directory1’.
chmod go-rwx directory1: quitar permiso de lectura ®, escritura (w) y (x) ejecución al grupo (g) y otros (o) sobre el directorio ‘directory1’.
chown user1 file1: cambiar el dueño de un fichero.
chown -R user1 directory1: cambiar el propietario de un directorio y de todos los ficheros y directorios contenidos dentro.
chgrp group1 file1: cambiar grupo de ficheros.
chown user1:group1 file1: cambiar usuario y el grupo propietario de un fichero.
find / -perm -u+s: visualizar todos los ficheros del sistema con SUID configurado.
chmod u+s /bin/file1: colocar el bit SUID en un fichero binario. El usuario que corriendo ese fichero adquiere los mismos privilegios como dueño.
chmod u-s /bin/file1: deshabilitar el bit SUID en un fichero binario.
chmod g+s /home/public: colocar un bit SGID en un directorio –similar al SUID pero por directorio.
chmod g-s /home/public: desabilitar un bit SGID en un directorio.
chmod o+t /home/public: colocar un bit STIKY en un directorio. Permite el borrado de ficheros solamente a los dueños legítimos.
chmod o-t /home/public: desabilitar un bit STIKY en un directorio.

 #Atributos especiales en ficheros (Usa ”+” para colocar permisos y ”-” para eliminar)

chattr +a file1: permite escribir abriendo un fichero solamente modo append.
chattr +c file1: permite que un fichero sea comprimido / descomprimido automaticamente.
chattr +d file1: asegura que el programa ignore borrar los ficheros durante la copia de seguridad.
chattr +i file1: convierte el fichero en invariable, por lo que no puede ser eliminado, alterado, renombrado, ni enlazado.
chattr +s file1: permite que un fichero sea borrado de forma segura.
chattr +S file1: asegura que un fichero sea modificado, los cambios son escritos en modo synchronous como con sync.
chattr +u file1: te permite recuperar el contenido de un fichero aún si este está cancelado.
lsattr: mostrar atributos especiales.
