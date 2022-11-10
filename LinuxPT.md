# Diretórios (Debian)

      / - Diretório root

      /bin - importante aplicativos binários

      /boot - arquivos de configuração do boot , kernels, e outros arquivos necessários durante o período do boot.

      /dev - os arquivos do dispositivo

      /etc - arquivos de configuração, scripts de inicialização, etc.

      /home - diretórios home para diferentes usuários

      /initrd - usado quando está criando um processo de boot initrd personalizado

      /lib - bibliotecas de sistema

      /lost+found - fornece um sistema perdido+achado para arquivos que existem sob o diretório root (/).

      /media - monta ( carrega ) automaticamente partições em seu disco rigido ou mídia removivel como CDs, câmeras digitais, etc.

      /mnt - sistema de arquivos montado manualmente em seu disco rigido.

      /opt - fornece um local opcional para aplica

      /proc - diretório dinâmico especial que mantem informação sobre o estado do sistema, incluindo os processos atualmente executados.

      /root - diretório home do usuário root, pronuciado "eslash-ruut"

      /sbin - binários de sistema importantes.

      /srv - pode conter arquivos que são servidos para outros sistemas

      /sys - arquivos de sistema

      /tmp - arquivos temporários

      /usr - aplicativos e arquivos que são na maioria das vezes disponíveis ao acesso de todos usuários

      /var - arquivos variáveis tal como logs e bancos de dados


# Comandos Globais

      Ctrl+C -> Cancela o comando atual em funcionamento.

      Ctrl+Z -> Pausa o comando atual, retorna com "fg" em primeiro plano Linux ou "bg" em segundo plano.
      
      Ctrl+D -> Faz o logout da sessão atual.

      Ctrl+W -> Apaga uma palavra na linha atual.

      Ctrl+U -> Apaga a linha inteira.

      Ctrl+R -> Tecle para Exiber um comando recente.
      
      !! -> Repete o último comando.

      exit -> Faz o logout da sessão atual.


# Informações de sistema

      arch: mostrar a arquitectura da máquina.
      uname -m: mostrar a arquitectura da máquina .
      uname -r: mostrar versão do kernel usado.
      dmidecode -q: mostrar o hardware do sistema.
      hdparm -i /dev/hda: mostrar as características de um disco rigido.
      hdparm -tT /dev/sda: Fazer testes de leitura em um disco rigido.
      cat /proc/cpuinfo: mostrar informacão do CPU.
      cat /proc/interrupts: mostrar as interrupções.
      cat /proc/meminfo: verificar o uso da memória.
      cat /proc/swaps: mostrar ficheros swap.
      cat /proc/version: mostrar a versão do kernel.
      cat /proc/net/dev: mostrar adaptadores de rede e estatísticas.
      cat /proc/mounts: mostrar o sistema de ficheros montado.
      lspci -tv: mostrar dispositivos PCI.
      lsusb -tv: mostrar dispositivos USB.
      date: mostrar la fecha del sistema.
      cal 2021: mostrar o almanaque de 2021.
      cal 07 2011: mostrar o almanaque para o mes julio de 2021.
      date 041217002011.00: colocar (declarar, ajustar) data e hora.
      clock -w: guarda as modificações de data na bios.

# Apagar (Reiniciar Sistema ou Fechar Seção)

      shutdown -h now: apagar o sistema (1).
      init 0: apagar o sistema (2).
      telinit 0: apagar o sistema (3).
      halt: apagar o sistema (4).
      shutdown -h hours:minutes &: apagar de modo planificado o sistema.
      shutdown -c: cancelar o shutdown planificado do sistema.
      shutdown -r now: reiniciar (1).
      reboot: reiniciar (2).
      logout: fechar a seção.

# Arquivos y Diretórios

      cd /home: entrar no diretório “home”.
      cd ..: voltar um nivel.
      cd ../..: voltar 2 niveis.
      cd: ir para o diretório root(raiz).
      cd ~user1: ir para o diretório user1.
      cd –: voltar ao diretório anterior.
      pwd: mostrar o camino do directorio de trabalho.
      ls: mostar ficheiros do directorio atual.
      ls -F:mostar ficheiros do directorio atual.
      ls -l: mostar ficheiros e pastas do directorio atual.
      ls -a: mostrar ficheiros ocultos.
      ls *[0-9]*: mostrar os ficheiros y pastas que contem números.
      tree: mostrar ficheros e pastas em forma de arvore.
      lstree:mostrar ficheros e pastas em forma de arvore.
      mkdir dir1:  criar uma pasta do diretório com nome dir1.
      mkdir dir1 dir2: criar duas pastas ou diretorios simultaneamente.
      mkdir -p /tmp/dir1/dir2: criar uma arvore de diretórios.
      rm -f file1: apagar o ficheiro ‘file1’.
      rmdir dir1: apagar a pasta ‘dir1’.
      rm -rf dir1: eliminar uma pasta e todo o ser conteudo de forma recursiva ‘dir1’.
      rm -rf dir1 dir2: eliminar duas pastas e todos os seus conteudos de forma recursiva ‘dir1’ ‘dir2’.
      mv dir1 new_dir: renomear ou mver um ficheiro ou pasta par outro directorio.
      cp file1: copiar um fichero.
      cp file1 file2: copiar dois ficheros ao mesmo tempo.
      cp dir /* .: copiar todos os ficheiros de um diretorio dentro do diretório de trabalho actual.
      cp -a /tmp/dir1 .: copiar um diretorio dentro do diretorio atual de trabalho.
      cp -a dir1: copiar un diretorio.
      cp -a dir1 dir2: copiar dois diretorios ao mesmo tempo.
      ln -s file1 lnk1: criar um link simbólico para o ficheiro ou diretorio.
      ln file1 lnk1: criar um link fisico para o ficheiro ou diretorio.
      touch -t 0712250000 file1: modificar o tempo real (decriação) de um ficheiro ou diretorio.
      iconv -l: listas de crifras conhecidas.


# Procurar arquivos

      find / -name file1: procurar ficheiro ou diretório a partir da raiz.
      find / -user user1: procurar ficheiro ou diretório pertencentes a um utilizador.
      find /home/user1 -name *.bin: procurar ficheiros com extensão‘. bin’ dentro do diretório ‘/ home/user1’.
      find /usr/bin -type f -atime +100:  procurar ficheiros binarios não usados nos ultimos 100 dias.
      find /usr/bin -type f -mtime -10: procura ficheiros criados ou modificados nos ultimos 10 dias.
      find / -name *.rpm -exec chmod 755 ‘{}’ ;: procurar ficheiros com extensão ‘.rpm’ e modificar suas permissões.
      find / -xdev -name *.rpm: Procurar ficheiros com extensão ‘.rpm’ ignorando os dispositivos removiveis.
      whereis halt: mostrar a localização de um ficheiro binario de ajuda ou fonte. neste caso o comando ‘halt’.
      which halt: mostar o caminho completo para o binario executavel / .

# Sistema de fichetros
      mount /dev/hda2 /mnt/hda2: montar o disco com label hda2.
      umount /dev/hda2: desmontar o disco com label hda2.
      fuser -km /mnt/hda2: forçar o desmontar do dispositivo montado (hda2).
      umount -n /mnt/hda2: descomtar sem ler o mtab.
      mount /dev/fd0 /mnt/floppy: montar uma disquete (floppy).
      mount /dev/cdrom /mnt/cdrom: montar um cdrom / dvdrom.
      mount -o loop file.iso /mnt/cdrom: montar um ficheiro ou uma imagem iso.
      mount -t vfat /dev/hda5 /mnt/hda5: montar um sistema de ficheiros FAT32.
      mount /dev/sda1 /mnt/usbdisk: montar uma usb pen-drive ou uma memoria.

# Espaço de Disco

      df -h: mostrar lista de partições montadas.
      ls -lSr |more: mostrar o tamanha dos ficheiros e diretórios ordenados por tamanho.
      du -sh dir1:  Fazer estimativa do espaço usado pelo diretório ‘dir1’.
      du -sk * | sort -rn: mostar o tamanho dos ficheiros e diretórios ordenados por tamanho.


# Usuarios e Grupos

      groupadd nome_do_grupo: criar um grupo novo.
      groupdel nome_do_grupo: apagar um grupo.
      groupmod -n novo_nome_do_grupo velho_nome_do_grupo: renomear o grupo.
      useradd -c “Name Surname ” -g admin -d /home/user1 -s /bin/bash user1: cria um novo utilizador no grupo admin.
      useradd user1: criar um novo utilizador.
      userdel -r user1: apaga o utilizador (‘-r’ elimina  diretorio Home).
      usermod -c “User FTP” -g system -d /ftp/user1 -s /bin/nologin user1: modifica os atributos do utilizador.
      passwd: muda a password.
      passwd user1: modifica a password de um utilizador.
      chage -E 2011-12-31 user1: adiciona uma data limite para a password do utilizador. exemplo, acaba em 2011-12-31 

# Permisões em Ficheiros (Usar ”+” para colocar permissoes e ”-” para eliminar)

      ls -lh: mostrar permissoes.
      ls /tmp | pr -T5 -W$COLUMNS: dividir o terminal em 5 colunas.
      chmod ugo+rwx directory1: adicionar permissoes de leitura, escrita (w) y execução (x) ao proprietario (u), grupo (g) e otros (o) para o diretorio ‘directory1’.
      chmod go-rwx directory1: retira permissoes de leitura, escrita (w) y execução (x) ao proprietario (u), grupo (g) e otros (o) para o diretorio ‘directory1’.
      chown user1 file1: modifica o proprietario do ficheiro.
      chown -R user1 directory1: modificar o proprietario de uma pasta de forma recursiva
      chgrp group1 file1: modificacr grupo de ficheiros.
      chown user1:group1 file1: modificar o utilizador e grupo de um determinado ficheiro.

      find / -perm -u+s: visualizar todos os ficheiros do sistema com SUID configurado.
      chmod u+s /bin/file1: colocar o bit SUID num ficheiro binario.
      chmod u-s /bin/file1: desativar o bit SUID de um ficheiro binario.
      chmod g+s /home/public: adicionar o bit SGID num diretorio.
      chmod g-s /home/public: desativar o bit SGID num diretorio.

 # Atributos especiais em ficheiros

      chattr +a file1: permite escrever abrindo um ficheiro somente em modo append.
      chattr +c file1: permite que um ficheiro seja compactado/descompactado automaticamente.
      chattr +d file1: assegura que o programa ignore apagar os ficheiros durante a copia de segurança.
      chattr +i file1: converte o ficheiro em inariavel, pelo que nao pode ser eliminado, alterado,renomeado.
      chattr +s file1: permite que um ficheiro seja apagado de forma segura.
      chattr +S file1: assegura que um ficheiro seja modificado, as modificações são escritas em mode synchronous.
      chattr +u file1: permite recuperar o conteudo de um ficheiro, mesmo que este esteja cancelado.
      lsattr: mostrar atibutos especiais.

# Arquivose Ficheiros compactados

      bunzip2 file1.bz2: descompacta o ficheiro chamado "file1.bz2".
      bzip2 file1: compacta um ficheiro com o nome "file1".
      gunzip file1.gz: descompacta um ficheiro chamado "file1.gz".
      gzip file1: compacta um ficheiro chamado "file1".
      gzip -9 file1: compacta com compressão maxima.
      rar a file1.rar test_file: cria um ficheiro rar chamado "file1.rar".
      rar a file1.rar file1 file2 dir1: compacta "file1", "file2" e "dir1" simultaneamente.
      rar x file1.rar: descompactar o arquivo rar.
      unrar x file1.rar: descompactar o arquivo rar.
      tar -cvf archive.tar file1: criar um tarball descompactado.
      tar -cvf archive.tar file1 file2 dir1: cria um arquivo contendo "file1","file2" e "dir1".
      tar -tf archive.tar: mostra os conteudos de um arquivo.
      tar -xvf archive.tar: extrair um tarball.
      tar -xvf archive.tar -C /tmp: extrair uma tarball no /tmp.
      tar -cvfj archive.tar.bz2 dir1: criar um tarball compactado dentro de bzip2.
      tar -xvfj archive.tar.bz2: descompactar um arquivo tar compactado em bzip2.
      tar -cvfz archive.tar.gz dir1: criar um tarball compactado em gzip.
      tar -xvfz archive.tar.gz:descompactar um arquivo tar compactado em gzip.
      zip file1.zip file1: criar um arquivo compactado em zip.
      zip -r file1.zip file1 file2 dir1:compactar, em zip, varos arquivos e diretorios de forma simultanea.
      unzip file1.zip: descompactar um arquivo zip.
<<<<<<< HEAD

# Pacotes Deb (Debian, Ubuntu e derivados)

      dpkg -i package.deb: instalar / actualizar um pacote deb.
      dpkg -r package_name: eliminar um pacote deb do sistema.
      dpkg -l: mostrar todos os pacotes deb instalados no sistema.
      dpkg -l | grep httpd: mostrar todos os pacotes deb com o nome "HTTPD".
      dpkg -s package_name: obter informação em um pacote especifico instalado no sistema.
      dpkg -L package_name:mostrar a lista de ficheiros dados por um pacote instalado no sistema.
      dpkg –contents package.deb: mostrar lista de ficheiros de um pacote ainda não instalado.
      dpkg -S /bin/ping:verificar qual pacote pertence a un ficheiro.

# Actualização de pacotes por APT (Debian, Ubuntu e derivados)

apt-get install package_name: instalar / actualizar um pacote deb.
apt-cdrom install package_name: instalar / actualizar um pacote deb a partir de um cdrom.
apt-get update: actualizar a lista de pacotes.
apt-get upgrade: actualizar todos os pacotes instalados.
apt-get remove package_name: eliminar um pacote deb do sistema.
apt-get check: verificar se as dependencias esrtao correctas.
apt-get clean:limpar a cache dos pacotes descarregados.

# Ver o conteudo de um ficheiro

cat file1: ver os conteudos iniciais de um ficheiro.
tac file1: ver os conteudos finais de um ficheiro.
more file1: ver mais conteudo do ficheiro.
head -2 file1: ver as duas primeiras linhas de um ficheiro.
tail -2 file1: ver as duas ultimas linhas de um ficheiro.
tail -f /var/log/messages: ver em tempo real o que foi adicionado no ficheiro.
=======
>>>>>>> 50748dec726ae6d8250e814357424795b9e94f8a
