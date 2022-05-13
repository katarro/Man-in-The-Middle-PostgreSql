# Tarea_Redes

Servidor

1. Entrar en la carpeta "Servidor".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del servidor de Postgres.
4. sudo docker build -t server_ postgres .
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del servidor de Postgres.
6. docker run -it --name server_postgres -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=root -e POSTGRES_DB=my_store -p 5432:5432 server_postgres

Cliente
1. Entrar en la carpeta "Cliente".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del cliente de Postgres.
4  sudo docker build -t cliente_postgres
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del cliente de Postgres al mismo tiene que se inicia la conexión al servidor.
6. sudo docker run -it --link server_postgres:server_postgres cliente_postgres

--name: Nos permite asignarle un nombre a nuestro contenedor.
-e:     Es para pasarle al contenedor variables de entorno.
-p:     Seleccionamos un puerto.


1. mkdir /usr/local/pgsql/data
2.    chown postgres /usr/local/pgsql/data
3.    su - postgres
4. /usr/local/pgsql/bin/initdb -D /usr/local/pgsql/data
5. /usr/local/pgsql/bin/pg_ctl -D /usr/local/pgsql/data -l logfile start
6. /usr/local/pgsql/bin/createdb test
7. /usr/local/pgsql/bin/psql test

. /usr/local/pgsql/data/   :  Editar el archivo postgresql.conf, cambiar liten adressess="localhost" por "*"

