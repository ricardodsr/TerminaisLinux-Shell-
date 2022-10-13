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

#Archivos y Ficheros comprimidos

bunzip2 file1.bz2: descomprime in fichero llamado ‘file1.bz2’.
bzip2 file1: comprime un fichero llamado ‘file1’.
gunzip file1.gz: descomprime un fichero llamado ‘file1.gz’.
gzip file1: comprime un fichero llamado ‘file1’.
gzip -9 file1: comprime con compresión máxima.
rar a file1.rar test_file: crear un fichero rar llamado ‘file1.rar’.
rar a file1.rar file1 file2 dir1: comprimir ‘file1’, ‘file2’ y ‘dir1’ simultáneamente.
rar x file1.rar: descomprimir archivo rar.
unrar x file1.rar: descomprimir archivo rar.
tar -cvf archive.tar file1: crear un tarball descomprimido.
tar -cvf archive.tar file1 file2 dir1: crear un archivo conteniendo ‘file1’, ‘file2′ y’dir1’.
tar -tf archive.tar: mostrar los contenidos de un archivo.
tar -xvf archive.tar: extraer un tarball.
tar -xvf archive.tar -C /tmp: extraer un tarball en / tmp.
tar -cvfj archive.tar.bz2 dir1: crear un tarball comprimido dentro de bzip2.
tar -xvfj archive.tar.bz2: descomprimir un archivo tar comprimido en bzip2
tar -cvfz archive.tar.gz dir1: crear un tarball comprimido en gzip.
tar -xvfz archive.tar.gz: descomprimir un archive tar comprimido en gzip.
zip file1.zip file1: crear un archivo comprimido en zip.
zip -r file1.zip file1 file2 dir1: comprimir, en zip, varios archivos y directorios de forma simultánea.
unzip file1.zip: descomprimir un archivo zip.

# Paquetes Deb (Debian, Ubuntu y derivados)

dpkg -i package.deb: instalar / actualizar un paquete deb.
dpkg -r package_name: eliminar un paquete deb del sistema.
dpkg -l: mostrar todos los paquetes deb instalados en el sistema.
dpkg -l | grep httpd: mostrar todos los paquetes deb con el nombre “httpd”
dpkg -s package_name: obtener información en un paquete específico instalado en el sistema.
dpkg -L package_name: mostar lista de ficheros dados por un paquete instalado en el sistema.
dpkg –contents package.deb: mostrar lista de ficheros dados por un paquete no instalado todavía.
dpkg -S /bin/ping: verificar cuál paquete pertenece a un fichero dado.

# Actualizador de paquetes APT (Debian, Ubuntu y derivados)

apt-get install package_name: instalar / actualizar un paquete deb.
apt-cdrom install package_name: instalar / actualizar un paquete deb desde un cdrom.
apt-get update: actualizar la lista de paquetes.
apt-get upgrade: actualizar todos los paquetes instalados.
apt-get remove package_name: eliminar un paquete deb del sistema.
apt-get check: verificar la correcta resolución de las dependencias.
apt-get clean: limpiar cache desde los paquetes descargados.
apt-cache search searched-package: retorna lista de paquetes que corresponde a la serie «paquetes buscados».

#Ver el contenido de un fichero

cat file1: ver los contenidos de un fichero comenzando desde la primera hilera.
tac file1: ver los contenidos de un fichero comenzando desde la última línea.
more file1: ver el contenido a lo largo de un fichero.
less file1: parecido al commando ‘more’ pero permite salvar el movimiento en el fichero así como el movimiento hacia atrás.
head -2 file1: ver las dos primeras líneas de un fichero.
tail -2 file1: ver las dos últimas líneas de un fichero.
tail -f /var/log/messages: ver en tiempo real qué ha sido añadido al fichero.

#Manipulación de texto

cat file1 file2 .. | command <> file1_in.txt_or_file1_out.txt: sintaxis general para la manipulación de texto utilizando PIPE, STDIN y STDOUT.
cat file1 | command( sed, grep, awk, grep, etc…) > result.txt: sintaxis general para manipular un texto de un fichero y escribir el resultado en un fichero nuevo.
cat file1 | command( sed, grep, awk, grep, etc…) » result.txt: sintaxis general para manipular un texto de un fichero y añadir resultado en un fichero existente.
grep Aug /var/log/messages: buscar palabras “Aug” en el fichero ‘/var/log/messages’.
grep ^Aug /var/log/messages: buscar palabras que comienzan con “Aug” en fichero ‘/var/log/messages’
grep [0-9] /var/log/messages: seleccionar todas las líneas del fichero ‘/var/log/messages’ que contienen números.
grep Aug -R /var/log/*: buscar la cadena “Aug” en el directorio ‘/var/log’ y debajo.
sed ‘s/stringa1/stringa2/g’ example.txt: reubicar “string1” con “string2” en ejemplo.txt
sed ‘/^$/d’ example.txt: eliminar todas las líneas en blanco desde el ejemplo.txt
sed ‘/ *#/d; /^$/d’ example.txt: eliminar comentarios y líneas en blanco de ejemplo.txt
echo ‘esempio’ | tr ‘[:lower:]’ ‘[:upper:]’: convertir minúsculas en mayúsculas.
sed -e ‘1d’ result.txt: elimina la primera línea del fichero ejemplo.txt
sed -n ‘/stringa1/p’: visualizar solamente las líneas que contienen la palabra “string1”.

# Análisis del sistema de ficheros
badblocks -v /dev/hda1: Chequear los bloques defectuosos en el disco hda1.
fsck /dev/hda1: reparar / chequear la integridad del fichero del sistema Linux en el disco hda1.
fsck.ext2 /dev/hda1: reparar / chequear la integridad del fichero del sistema ext 2 en el disco hda1.
e2fsck /dev/hda1: reparar / chequear la integridad del fichero del sistema ext 2 en el disco hda1.
e2fsck -j /dev/hda1: reparar / chequear la integridad del fichero del sistema ext 3 en el disco hda1.
fsck.ext3 /dev/hda1: reparar / chequear la integridad del fichero del sistema ext 3 en el disco hda1.
fsck.vfat /dev/hda1: reparar / chequear la integridad del fichero sistema fat en el disco hda1.
fsck.msdos /dev/hda1: reparar / chequear la integridad de un fichero del sistema dos en el disco hda1.
dosfsck /dev/hda1: reparar / chequear la integridad de un fichero del sistema dos en el disco hda1.

# Formatear un sistema de ficheros

mkfs /dev/hda1: crear un fichero de sistema tipo Linux en la partición hda1.
mke2fs /dev/hda1: crear un fichero de sistema tipo Linux ext 2 en hda1.
mke2fs -j /dev/hda1: crear un fichero de sistema tipo Linux ext3 (periódico) en la partición hda1.
mkfs -t vfat 32 -F /dev/hda1: crear un fichero de sistema FAT32 en hda1.
fdformat -n /dev/fd0: formatear un disco flooply.
mkswap /dev/hda3: crear un fichero de sistema swap.

# Trabajo con la SWAP

mkswap /dev/hda3: crear fichero de sistema swap.
swapon /dev/hda3: activando una nueva partición swap.
swapon /dev/hda2 /dev/hdb3: activar dos particiones swap.

#(Backup)
 dump -0aj -f /tmp/home0.bak /home: hacer una salva completa del directorio ‘/home’.
dump -1aj -f /tmp/home0.bak /home: hacer una salva incremental del directorio ‘/home’.
restore -if /tmp/home0.bak: restaurando una salva interactivamente.
rsync -rogpav –delete /home /tmp: sincronización entre directorios.
rsync -rogpav -e ssh –delete /home ip_address:/tmp: rsync a través del túnel SSH.
rsync -az -e ssh –delete ip_addr:/home/public /home/local: sincronizar un directorio local con un directorio remoto a través de ssh y de compresión.
rsync -az -e ssh –delete /home/local ip_addr:/home/public: sincronizar un directorio remoto con un directorio local a través de ssh y de compresión.
dd bs=1M if=/dev/hda | gzip | ssh user@ip_addr ‘dd of=hda.gz’: hacer una salva de un disco duro en un host remoto a través de ssh.
dd if=/dev/sda of=/tmp/file1: salvar el contenido de un disco duro a un fichero. (En este caso el disco duro es “sda” y el fichero “file1”).
tar -Puf backup.tar /home/user: hacer una salva incremental del directorio ‘/home/user’.
( cd /tmp/local/ && tar c . ) | ssh -C user@ip_addr ‘cd /home/share/ && tar x -p’: copiar el contenido de un directorio en un directorio remoto a través de ssh.
( tar c /home ) | ssh -C user@ip_addr ‘cd /home/backup-home && tar x -p’: copiar un directorio local en un directorio remoto a través de ssh.
tar cf – . | (cd /tmp/backup ; tar xf – ): copia local conservando las licencias y enlaces desde un directorio a otro.
find /home/user1 -name ‘*.txt’ | xargs cp -av –target-directory=/home/backup/ –parents: encontrar y copiar todos los ficheros con extensión ‘.txt’ de un directorio a otro.
find /var/log -name ‘*.log’ | tar cv –files-from=- | bzip2 > log.tar.bz2: encontrar todos los ficheros con extensión ‘.log’ y hacer un archivo bzip.
dd if=/dev/hda of=/dev/fd0 bs=512 count=1: hacer una copia del MRB (Master Boot Record) a un disco floppy.
dd if=/dev/fd0 of=/dev/hda bs=512 count=1: restaurar la copia del MBR (Master Boot Record) salvada en un floppy.

# Trabajo con la RED ( LAN y Wi-Fi)
ifconfig eth0: mostrar la configuración de una tarjeta de red Ethernet.
ifup eth0: activar una interface ‘eth0’.
ifdown eth0: deshabilitar una interface ‘eth0’.
ifconfig eth0 192.168.1.1 netmask 255.255.255.0: configurar una dirección IP.
ifconfig eth0 promisc: configurar ‘eth0’en modo común para obtener los paquetes (sniffing).
dhclient eth0: activar la interface ‘eth0’ en modo dhcp.
route -n: mostrar mesa de recorrido.
route add -net 0/0 gw IP_Gateway: configurar entrada predeterminada.
route add -net 192.168.0.0 netmask 255.255.0.0 gw 192.168.1.1: configurar ruta estática para buscar la red ‘192.168.0.0/16’.
route del 0/0 gw IP_gateway: eliminar la ruta estática.
echo “1” > /proc/sys/net/ipv4/ip_forward: activar el recorrido ip.
hostname: mostrar el nombre del host del sistema.
host www.example.com: buscar el nombre del host para resolver el nombre a una dirección ip(1).
nslookup www.example.com: buscar el nombre del host para resolver el nombre a una direccióm ip y viceversa(2).
ip link show: mostar el estado de enlace de todas las interfaces.
mii-tool eth0: mostar el estado de enlace de ‘eth0’.
ethtool eth0: mostrar las estadísticas de tarjeta de red ‘eth0’.
netstat -tup: mostrar todas las conexiones de red activas y sus PID.
netstat -tupl: mostrar todos los servicios de escucha de red en el sistema y sus PID.
tcpdump tcp port 80: mostrar todo el tráfico HTTP.
iwlist scan: mostrar las redes inalámbricas.
iwconfig eth1: mostrar la configuración de una tarjeta de red inalámbrica.
whois www.example.com: buscar en base de datos Whois.

# Redes de Microsoft Windows (SAMBA)
nbtscan ip_addr: resolución de nombre de red bios.
nmblookup -A ip_addr: resolución de nombre de red bios.
smbclient -L ip_addr/hostname: mostrar acciones remotas de un host en windows.

# Tablas IP (CORTAFUEGOS)
iptables -t filter -L: mostrar todas las cadenas de la tabla de filtro.
iptables -t nat -L: mostrar todas las cadenas de la tabla nat.
iptables -t filter -F: limpiar todas las reglas de la tabla de filtro.
iptables -t nat -F: limpiar todas las reglas de la tabla nat.
iptables -t filter -X: borrar cualquier cadena creada por el usuario.
iptables -t filter -A INPUT -p tcp –dport telnet -j ACCEPT: permitir las conexiones telnet para entar.
iptables -t filter -A OUTPUT -p tcp –dport http -j DROP: bloquear las conexiones HTTP para salir.
iptables -t filter -A FORWARD -p tcp –dport pop3 -j ACCEPT: permitir las conexiones POP a una cadena delantera.
iptables -t filter -A INPUT -j LOG –log-prefix “DROP INPUT”: registrando una cadena de entrada.
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE: configurar un PAT (Puerto de traducción de dirección) en eth0, ocultando los paquetes de salida forzada.
iptables -t nat -A PREROUTING -d 192.168.0.1 -p tcp -m tcp –dport 22 -j DNAT –to-destination 10.0.0.2:22: redireccionar los paquetes diriguidos de un host a otro.

#Monitoreando y depurando
top: mostrar las tareas de linux usando la mayoría cpu.
ps -eafw: muestra las tareas Linux.
ps -e -o pid,args –forest: muestra las tareas Linux en un modo jerárquico.
pstree: mostrar un árbol sistema de procesos.
kill -9 ID_Processo: forzar el cierre de un proceso y terminarlo.
kill -1 ID_Processo: forzar un proceso para recargar la configuración.
lsof -p $$: mostrar una lista de ficheros abiertos por procesos.
lsof /home/user1: muestra una lista de ficheros abiertos en un camino dado del sistema.
strace -c ls >/dev/null: mostrar las llamadas del sistema hechas y recibidas por un proceso.
strace -f -e open ls >/dev/null: mostrar las llamadas a la biblioteca.
watch -n1 ‘cat /proc/interrupts’: mostrar interrupciones en tiempo real.
last reboot: mostrar historial de reinicio.
lsmod: mostrar el kernel cargado.
free -m: muestra el estado de la RAM en megabytes.
smartctl -A /dev/hda: monitorear la fiabilidad de un disco duro a través de SMART.
smartctl -i /dev/hda: chequear si SMART está activado en un disco duro.
tail /var/log/dmesg: mostrar eventos inherentes al proceso de carga del kernel.
tail /var/log/messages: mostrar los eventos del sistema.
