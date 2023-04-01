# Man in The Middle - PostgreSql
https://www.youtube.com/watch?v=1QgD_ZYN2mE&t=390s



# Servidor
1. Entrar en la carpeta "Servidor".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del servidor de Postgres.  
4. *sudo docker build -t server_postgres .*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del servidor de Postgres.
6. *sudo docker run -it --rm --name server_postgres -p 5432:5432 server_postgres*    

# Dentro del contenedor
7.  *# mkdir /usr/local/pgsql/data*
8.  *# chown postgres /usr/local/pgsql/data*
9.  *# su - postgres*
10. *# /usr/local/pgsql/bin/initdb -D /usr/local/pgsql/data*
11. *# cd /usr/local/pgsql/data/*
12. *# vim postgresql.conf*
13. Cambiar: "listen_addresses='localhost'" -> "listen_addresses='*'" (salir del editor)
14. *# vim pg_hba.conf*
15. Cambiar: "host all  all    127.0.0.1/32  trust" -> "host all  all    0.0.0.0/0  md5" (salir del editor)

# Creación Base de Datos
17. *# /usr/local/pgsql/bin/pg_ctl -D /usr/local/pgsql/data -l logfile start*
18. *# /usr/local/pgsql/bin/createdb test*
19. *# /usr/local/pgsql/bin/psql test*

# Crear Contraseña
20. Crear contraseña para la base de datos
21. *# \password*
22. Ingresar contraseña...

# Ingresar Datos en Servidor
24. Para ver la conexión, es necesario crear datos, y se harán mediante los siguientes códigos:
25. *# CREATE TABLE estudiantes (nombre varchar (50), edad int);*
26. *# INSERT INTO estudiantes VALUES ('Ignacio',24);*




# Cliente
1. Entrar en la carpeta "Cliente".
2. Abrir una terminal en ese directorio.
3. Ejecutar el siguiente código para construir la imagen del cliente de Postgres.
4. *# sudo docker build -t cliente_postgres*
5. Ejecutar el siguiente comando para ejecutar el contenedor con la imagen del cliente de Postgres.
6. *# sudo docker run -it --rm cliente_postgres bash*
7. Dentro del contenedor de pgcli, ejecutar el siguiente comando.
8. pgcli 'postgresql://postgres:postgres@172.17.0.2:5432/test'
9. *# select * from estudiantes*





