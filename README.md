# Maquinavirtualcode

Code para acessar o servidor pela minha maquina local 
# ssh ndembuza@192.168.1.101
criar chave ssh
# ssh-keygen
copiar a chave
# ssh-copy-id ndembuza@192.168.1.101
acessar banco de mysql
# mysql -u root 

atualizar senha
# USE mysql;
# UPDATE user SET authentication_string=PASSWORD('nova_senha') WHERE User='root';
# FLUSH PRIVILEGES;


PARA DAR PREVILEGIO PRIMEIRO PRECISAMOS CRIAR O USARIO E SENHA 
# CREATE USER 'ndembuza'@'192.168.1.101' IDENTIFIED BY 'minhavida@04';

// AQUI DEPOIS DE CRIAR O USUARIO DANDO PREVILEGIOS 
# GRANT ALL PRIVILEGES ON biblioteca.* TO 'ndembuza'@'192.168.1.101' IDENTIFIED BY 'minhavida@04';
# FLUSH PRIVILEGES;

AQUI RESUMO DO COMANDO 

# CREATE USER 'ndembuza'@'192.168.1.101' IDENTIFIED BY 'minhavida@04';
# GRANT ALL PRIVILEGES ON biblioteca.* TO 'ndembuza'@'192.168.1.101';
# FLUSH PRIVILEGES;


verificar as permissões existentes para o usuário com o seguinte comando:
# SHOW GRANTS FOR 'ndembuza'@'192.168.1.101';
