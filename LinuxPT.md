# Informações de sistema

arch: mostrar a arquitectura da máquina.<br>
uname -m: mostrar a arquitectura da máquina .<br>
uname -r: mostrar versão do kernel usado.<br>
dmidecode -q: mostrar o hardware do sistema.<br>
hdparm -i /dev/hda: mostrar as características de um disco rigido.<br>
hdparm -tT /dev/sda: Fazer testes de leitura em um disco rigido.<br>
cat /proc/cpuinfo: mostrar informacão do CPU.<br>
cat /proc/interrupts: mostrar as interrupções.<br>
cat /proc/meminfo: verificar o uso da memória.<br>
cat /proc/swaps: mostrar ficheros swap.<br>
cat /proc/version: mostrar a versão do kernel.<br>
cat /proc/net/dev: mostrar adaptadores de rede e estatísticas.<br>
cat /proc/mounts: mostrar o sistema de ficheros montado.<br>
lspci -tv: mostrar dispositivos PCI.<br>
lsusb -tv: mostrar dispositivos USB.<br>
date: mostrar la fecha del sistema.<br>
cal 2021: mostrar o almanaque de 2021.<br>
cal 07 2011: mostrar o almanaque para o mes julio de 2021.<br>
date 041217002011.00: colocar (declarar, ajustar) data e hora.<br>
clock -w: guarda as modificações de data na bios.<br>

# Apagar (Reiniciar Sistema o Cerrar Sesión)

shutdown -h now: apagar o sistema (1).<br>
init 0: apagar o sistema (2).<br>
telinit 0: apagar o sistema (3).<br>
halt: apagar o sistema (4).<br>
shutdown -h hours:minutes &: apagar de modo planificado o sistema.<br>
shutdown -c: cancelar o shutdown planificado do sistema.<br>
shutdown -r now: reiniciar (1).<br>
reboot: reiniciar (2).<br>
logout: fechar a secção.<br>

# Archivos y Directorios

cd /home: entrar en el directorio “home”.<br>
cd ..: retroceder un nivel.<br>
cd ../..: retroceder 2 niveles.<br>
cd: ir al directorio raíz.<br>
cd ~user1: ir al directorio user1.<br>
cd –: ir (regresar) al directorio anterior.<br>
pwd: mostrar el camino del directorio de trabajo.<br>
ls: ver los ficheros de un directorio.<br>
ls -F: ver los ficheros de un directorio.<br>
ls -l: mostrar los detalles de ficheros y carpetas de un directorio.<br>
ls -a: mostrar los ficheros ocultos.<br>
ls *[0-9]*: mostrar los ficheros y carpetas que contienen números.<br>
tree: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.<br>
lstree: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.<br>
mkdir dir1: crear una carpeta o directorio con nombre ‘dir1’.<br>
mkdir dir1 dir2: crear dos carpetas o directorios simultáneamente (Crear dos directorios a la vez).<br>
mkdir -p /tmp/dir1/dir2: crear un árbol de directorios.<br>
rm -f file1: borrar el fichero llamado ‘file1’.<br>
rmdir dir1: borrar la carpeta llamada ‘dir1’.<br>
rm -rf dir1: eliminar una carpeta llamada ‘dir1’ con su contenido de forma recursiva. (Si lo borro recursivo estoy diciendo que es con su contenido).<br>
rm -rf dir1 dir2: borrar dos carpetas (directorios) con su contenido de forma recursiva.<br>
mv dir1 new_dir: renombrar o mover un fichero o carpeta (directorio).<br>
cp file1: copiar un fichero.<br>
cp file1 file2: copiar dos ficheros al unísono.<br>
cp dir /* .: copiar todos los ficheros de un directorio dentro del directorio de trabajo actual.<br>
cp -a /tmp/dir1 .: copiar un directorio dentro del directorio actual de trabajo.<br>
cp -a dir1: copiar un directorio.<br>
cp -a dir1 dir2: copiar dos directorio al unísono.<br>
ln -s file1 lnk1: crear un enlace simbólico al fichero o directorio.<br>
ln file1 lnk1: crear un enlace físico al fichero o directorio.<br>
touch -t 0712250000 file1: modificar el tiempo real (tiempo de creación) de un fichero o directorio.<br>
file file1: salida (volcado en pantalla) del tipo mime de un fichero texto.<br>
iconv -l: listas de cifrados conocidos.<br>
iconv -f fromEncoding -t toEncoding inputFile > outputFile: crea una nueva forma del fichero de entrada asumiendo que está codificado en fromEncoding y convirtiéndolo a ToEncoding.<br>
find . -maxdepth 1 -name *.jpg -print -exec convert ”{}” -resize 80×60 “thumbs/{}” \;: agrupar ficheros redimensionados en el directorio actual y enviarlos a directorios en vistas de miniaturas (requiere convertir desde ImagemagicK).<br>

