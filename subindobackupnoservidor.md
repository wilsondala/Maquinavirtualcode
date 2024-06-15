# 1º Instalar a Maquina virtual na virtual box
# 2º instalar o servidor linux
# 3ª configurar ssh do servirdor linux já instalado
# 4º Criar o banco de dados Mysql 

Criando a Maquina virtual
# nome: ndembuza
# nome do servidor - ndembuza
# nome do utilizador - dala
# senha: 123@mudar

Configurando a Maquina virtual
1 - Passo 
# 1º sudo apt update

# 2º sudo apt install openssh-server

# 3º sudo systemctl status ssh

# 4º sudo systemctl start ssh

# 5º sudo systemctl enable ssh

2 Passo 
# ssh username@your_server_ip   ssh dala@192.168.1.101

# 3º ssh-keygen -f "/home/wilsondala/.ssh/known_hosts" -R "192.168.1.101"


# sudo apt update

# sudo apt install mysql-server
 
# CREATE DATABASE biblioteca;

# USE biblioteca;

subindo arquivo sql na maquina virtual

# scp wilson_backup.sql dala@192.168.1.101:/home/dala/

# mysql -u dala -p wilson_backup.sql < /home/dala/wilson_backup.sql

comando para arquivo
# cat "+ o nome do arquivo" wilson_backup.sql

dalawilson1244

Minhavida@33


ns05.domaincontrol.com


 ns06.domaincontrol.com




 kvLqDdpMrG4rpjnazneo4*a%