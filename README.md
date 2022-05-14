# Tarea_Redes

Servidor

1. Entrar en la carpeta "Servidor".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del servidor de Postgres.  
4. *sudo docker build -t server_ postgres .*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del servidor de Postgres.
6. *sudo docker run -it --name server_postgres -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=root -e POSTGRES_DB=my_store -p 5432:5432 server_postgres*

Cliente
1. Entrar en la carpeta "Cliente".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del cliente de Postgres.
4  *sudo docker build -t cliente_postgres*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del cliente de Postgres al mismo tiene que se inicia la conexión al servidor.
6. *sudo docker run -it --link server_postgres:server_postgres cliente_postgres*



1. *mkdir /usr/local/pgsql/data*
2. *   chown postgres /usr/local/pgsql/data*
3. *   su - postgres*
4. */usr/local/pgsql/bin/initdb -D /usr/local/pgsql/data*
5. *cd /usr/local/pgsql/data/*
6. *vim postgresql.conf*
7. Cambiar: "listen_addresses='localhost'" -> "listen_addresses='*'" (salir del editor)
8. Cambiar: "host all  all    127.0.0.1/32  trust" -> "host all  all    0.0.0.0/0  md5" (salir del editor)
6. */usr/local/pgsql/bin/pg_ctl -D /usr/local/pgsql/data -l logfile start*
7. */usr/local/pgsql/bin/createdb test*
8. */usr/local/pgsql/bin/psql test*

