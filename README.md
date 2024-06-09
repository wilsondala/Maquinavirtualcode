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


-- Crie o usuário se ele não existir
# CREATE USER IF NOT EXISTS 'ndembuza'@'192.168.1.102' IDENTIFIED BY 'minhavida@04';

-- Conceda todas as permissões no banco de dados biblioteca ao usuário
# GRANT ALL PRIVILEGES ON biblioteca.* TO 'ndembuza'@'192.168.1.102';

-- Aplique as alterações
# FLUSH PRIVILEGES;

Consultar previlegios

 # SHOW GRANTS FOR 'ndembuza'@'192.168.1.102';

Inserindo os Dados

 # INSERT INTO livros (titulo, autor, ano_publicacao) VALUES
# ('Dom Casmurro', 'Machado de Assis', 1899),
# ('O Alquimista', 'Paulo Coelho', 1988),
# ('Grande Sertão: Veredas', 'João Guimarães Rosa', 1956);

Agora, execute o comando SELECT para visualizar os dados na tabela livros:

# SELECT * FROM livros;

+------------------------+---------------------+----------------+
| titulo                 | autor               | ano_publicacao |
+------------------------+---------------------+----------------+
| Dom Casmurro          | Machado de Assis    |           1899 |
| O Alquimista           | Paulo Coelho        |           1988 |
| Grande Sertão: Veredas | João Guimarães Rosa |           1956 |
+------------------------+---------------------+----------------+




verificar as permissões existentes para o usuário com o seguinte comando:
# SHOW GRANTS FOR 'ndembuza'@'192.168.1.101';


Para corrigir erro de acesso 
# mysql -u ndembuza -p --host=192.168.15.16 
--allowPublicKeyRetrieval=true

Fazendo backup.sql

mysqldump -u ndembuza -p --host=192.168.1.102 biblioteca > wilson_backup.sql




























#
# The MySQL database server configuration file.
#
# One can use all long options that the program supports.
# Run program with --help to get a list of available options and with
# --print-defaults to see which it would actually understand and use.
#
# For explanations see
# http://dev.mysql.com/doc/mysql/en/server-system-variables.html

# Here is entries for some specific programs
# The following values assume you have at least 32M ram

[mysqld]
#
# * Basic Settings
#
user            = mysql
# pid-file      = /var/run/mysqld/mysqld.pid
# socket        = /var/run/mysqld/mysqld.sock
# port          = 3306
# datadir       = /var/lib/mysql


# If MySQL is running as a replication slave, this should be
# changed. Ref https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_tmpdir
# tmpdir                = /tmp
#
# Instead of skip-networking the default is now to listen only on
# localhost which is more compatible and is not less secure.
bind-address            = 127.0.0.1
mysqlx-bind-address     = 127.0.0.1


O erro "Access denied; you need (at least one of) the PROCESS privilege(s) for this operation" indica que o usuário ndembuza não tem as permissões necessárias para executar o mysqldump. Para resolver isso, você precisará conceder os privilégios necessários ao usuário.



# GRANT PROCESS, SELECT, SHOW VIEW, EVENT, TRIGGER ON *.* TO 'ndembuza'@'192.168.1.101';
# FLUSH PRIVILEGES;


# GRANT ALL PRIVILEGES ON biblioteca.* TO 'ndembuza'@'192.168.1.101';
# FLUSH PRIVILEGES;

Apois corrigir esse erro fazer o backup
mysqldump -u ndembuza -p --host=192.168.1.101 biblioteca > wilson_backup.sql



Fazendo backup na maquina Local tirando dados do servidor erro:
mysqldump: Got error: 1045: Access denied for user 'ndembuza'@'192.168.1.102' (using password: YES) when trying to connect


mysql -u wilsondala -p biblioteca < /wilson_backup.sql

Resertar senha
# SET PASSWORD FOR 'wilsondala'@'localhost' = PASSWORD('minhavida@04');
# FLUSH PRIVILEGES;

scp ndembuza@192.168.1.101:/wilson_backup.sql/ wilsondala@192.168.1.102:/Maquinavirtualcode

scp ndembuza@192.168.1.101:/wilson_backup.sql wilsondala@192.168.1.102:/teste_wilson.sql


wilson_backup.sql
ndembuza@dala:~$ 


CREATE USER 'wilsondala'@'192.168.1.101' IDENTIFIED BY '123@mudar';
GRANT ALL PRIVILEGES ON biblioteca.* TO 'wilsondala'@'192.168.1.101';
FLUSH PRIVILEGES;


