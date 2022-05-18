# Tarea_Redes



# Servidor
1. Entrar en la carpeta "Servidor".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del servidor de Postgres.  
4. *sudo docker build -t server_postgres .*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del servidor de Postgres.
6. *sudo docker run -it --name server_postgres -p 5432:5432 server_postgres*    

7. *mkdir /usr/local/pgsql/data*
8. *chown postgres /usr/local/pgsql/data*
9. *su - postgres*
10. */usr/local/pgsql/bin/initdb -D /usr/local/pgsql/data*
11. *cd /usr/local/pgsql/data/*
12. *vim postgresql.conf*
13. Cambiar: "listen_addresses='localhost'" -> "listen_addresses='*'" (salir del editor)
14. *vim pg_hba.conf*
15. Cambiar: "host all  all    127.0.0.1/32  trust" -> "host all  all    0.0.0.0/0  md5" (salir del editor)
16. */usr/local/pgsql/bin/pg_ctl -D /usr/local/pgsql/data -l logfile start*
17. */usr/local/pgsql/bin/createdb test*
18. */usr/local/pgsql/bin/psql test*
19. Crear contraseña para la base de datos
20. *# \password*
21. Ingresar contraseña...




# Cliente
1. Entrar en la carpeta "Cliente".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del cliente de Postgres.
4. *sudo docker build -t cliente_postgres*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del cliente de Postgres al mismo tiene que se inicia la conexión al servidor.
6. *sudo docker run -it cliente_postgres*





