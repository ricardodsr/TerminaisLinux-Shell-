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

# Apagar (Reiniciar Sistema ou Fechar Seção)

shutdown -h now: apagar o sistema (1).<br>
init 0: apagar o sistema (2).<br>
telinit 0: apagar o sistema (3).<br>
halt: apagar o sistema (4).<br>
shutdown -h hours:minutes &: apagar de modo planificado o sistema.<br>
shutdown -c: cancelar o shutdown planificado do sistema.<br>
shutdown -r now: reiniciar (1).<br>
reboot: reiniciar (2).<br>
logout: fechar a seção.<br>

# Arquivos y Diretórios

cd /home: entrar no diretório “home”.<br>
cd ..: voltar um nivel.<br>
cd ../..: voltar 2 niveis.<br>
cd: ir para o diretório root(raiz).<br>
cd ~user1: ir para o diretório user1.<br>
cd –: voltar ao diretório anterior.<br>
pwd: mostrar o camino do directorio de trabalho.<br>
ls: mostar ficheiros do directorio atual.<br>
ls -F:mostar ficheiros do directorio atual.<br>
ls -l: mostar ficheiros e pastas do directorio atual.<br>
ls -a: mostrar ficheiros ocultos.<br>
ls *[0-9]*: mostrar os ficheiros y pastas que contem números.<br>
tree: mostrar ficheros e pastas em forma de arvore.<br>
lstree:mostrar ficheros e pastas em forma de arvore.<br>
mkdir dir1:  criar uma pasta do diretório com nome dir1.<br>
mkdir dir1 dir2: criar duas pastas ou diretorios simultaneamente.<br>
mkdir -p /tmp/dir1/dir2: criar uma arvore de diretórios.<br>
rm -f file1: apagar o ficheiro ‘file1’.<br>
rmdir dir1: apagar a pasta ‘dir1’.<br>
rm -rf dir1: eliminar uma pasta e todo o ser conteudo de forma recursiva ‘dir1’.<br>
rm -rf dir1 dir2: eliminar duas pastas e todos os seus conteudos de forma recursiva ‘dir1’ ‘dir2’.<br>
mv dir1 new_dir: renomear ou mver um ficheiro ou pasta par outro directorio.<br>
cp file1: copiar um fichero.<br>
cp file1 file2: copiar dois ficheros ao mesmo tempo.<br>
cp dir /* .: copiar todos os ficheiros de um diretorio dentro do diretório de trabalho actual.<br>
cp -a /tmp/dir1 .: copiar um diretorio dentro do diretorio atual de trabalho.<br>
cp -a dir1: copiar un diretorio.<br>
cp -a dir1 dir2: copiar dois diretorios ao mesmo tempo.<br>
ln -s file1 lnk1: criar um link simbólico para o ficheiro ou diretorio.<br>
ln file1 lnk1: criar um link fisico para o ficheiro ou diretorio.<br>
touch -t 0712250000 file1: modificar o tempo real (decriação) de um ficheiro ou diretorio.<br>
iconv -l: listas de crifras conhecidas.<br>


# Procurar arquivos
find / -name file1: procurar ficheiro ou diretório a partir da raiz.<br>
find / -user user1: procurar ficheiro ou diretório pertencentes a um utilizador.<br>
find /home/user1 -name *.bin: procurar ficheiros com extensão‘. bin’ dentro do diretório ‘/ home/user1’.<br>
find /usr/bin -type f -atime +100:  procurar ficheiros binarios não usados nos ultimos 100 dias.<br>
find /usr/bin -type f -mtime -10: procura ficheiros criados ou modificados nos ultimos 10 dias.<br>
find / -name *.rpm -exec chmod 755 ‘{}’ ;: procurar ficheiros com extensão ‘.rpm’ e modificar suas permissões.<br>
find / -xdev -name *.rpm: Procurar ficheiros com extensão ‘.rpm’ ignorando os dispositivos removiveis.<br>
whereis halt: mostrar a localização de um ficheiro binario de ajuda ou fonte. neste caso o comando ‘halt’.<br>
which halt: mostar o caminho completo para o binario executavel / .<br>
