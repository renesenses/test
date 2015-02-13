## Setting up a cross-compilation VM for Drobo
**Pré-requis :**`VMware fusion` `Ubuntu iso 32 bits` 
%% Penser à ajouter le pb réseau au niveau fusion
%% Aborder le pb clavier
### Définition et création de la VM
Dans  fusion, créer une nouvelle VM et sélectionner le fichier iso: 
''Nouveau
''Select iso file as OS
### VM parameters
Depending on VM usage
a. For Cross-compile VM :
''Proc : 1
''RAM : 1024 Mo
''HD space : 8 Go
b. For others, keep default values.
Then tye return
''return
### Mise à jour Vmware tools
''cd /media/bertrand/VMware\ Tools/
''cp VMware … .tgz ~Downloads
''tar xf VMware … .tgz
As root :
''perl –w vmware-install.pl
''sudo apt-get update
''sudo apt-get upgrade
''sudo apt-get install openssh-server
### Test conexion from host
''ssh username@ip
### Toolchain installtion
a. For Drobo 5N
''cd ~/xtools/toolchain
''mkdir 5n
''cd 5n
''wget -O arm7-tools.gz https://copy.com/nBZXoz3NdvFX%2FDroboAppsDS%2Farm7-tools.gz?download=1 tar zxf arm7-tools.gz
b. Toolchain installation for Drobo FS
''cd ~/xtools/toolchain
''wget -O arm-2007q1-21-arm-none-linux-gnueabi-i686-pc-linux-gnu.tar.bz2 https://sourcery.mentor.com/GNUToolchain/package1490/public/arm-none-linux-gnueabi/arm-2007q1-21-arm-none-linux-gnueabi-i686-pc-linux-gnu.tar.bz2
''tar jxf arm-2007q1-21-arm-none-linux-gnueabi-i686-pc-linux-gnu.tar.bz2
''mv arm-2007q1 fs
### Updating Git
''sudo apt-get install software-properties-common
''sudo add-apt-repository ppa:git-core/ppa
''sudo apt-get update
''sudo apt-get install git