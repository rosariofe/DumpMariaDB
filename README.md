# DumpMariaDB
Dump BD for other server CentOS

<h3>Migrando base de dados MariaDB entre servidores<h3>


<h2>- Primeiro iremos criar um dump da base de dados que deseja migrar.</h2>

- Acesse a base de dados.

<kbd>mysqldump -u root -p --opt [NOME DO BANCO DE DADOS] > [NOME DO BANCO DE DADOS].sql </kbd>

<h2>- Segundo passo, migrar para o servidor desejado</h2>

- Você tem duas opções fazer via FTP ou SCP(Recomendável e mais rápido).

- Utilize o comando abaixo:

<kbd> scp [NOME DO BANCO DE DADOS].sql [USUARIO DO BANCO DE DADOS]@[IP DO BANCO DE DADOS]:caminho/para/ </kbd>

Exemplo: scp wordpress.sql wordpressuser@192.168.33.25:/var/www/sql/

<h2>Terceiro passo acessar o servidor para onde deseja realizar a migração</h2>

- Após acessar o servidor onde está o novo banco, rode o seguinte comando:

<kbd>mysql -u root -p wordpress < /var/www/sql/wordpress.sql </kbd>

