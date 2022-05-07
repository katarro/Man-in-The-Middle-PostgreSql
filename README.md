# Tarea_Redes

1. Se creó correctamente la imagen de postgres desde el dockerfile.
2. Esta imagen se subió a docker.hub con la siguiente imagen, "docker pull katarro/server_postgres"
3. Se creó un docker-compose, en el está la configuración de docker y montando la imagen anterior.
4. Al ejecutar el comando para levantar el contenedor, este no se levanta.
5. Comando: docker-compose up -d postgres

Una vez instalada la imagen de docker, correr el siguiente comando:
docker run -d --rm --name postgres -e POSTGRES_PASSWORD=pass -p 5432:5432 postgres
-d:     Ejecuta en segundo plano.
--rm:   Hace que cuando salgamos del contenedor, éste se elimine y no ocupe espacio en nuestro disco.
--name: Nos permite asignarle un nombre a nuestro contenedor.
-e:     Es para pasarle al contenedor variables de entorno.
-p:     Seleccionamos un puerto.

El contenedor de Server_Postgres, se levanta, pero no corre en 2do plano