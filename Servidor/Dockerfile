FROM ubuntu:latest
ENV TZ=America/Santiago
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt update
RUN apt-get -y install \
    autoconf automake build-essential expect libgnutls28-dev \
    libident-dev libpam-dev pkg-config libwrap0-dev
RUN apt-get -y install wget
RUN apt -y install vim
RUN apt -y install sudo
RUN apt -y install gcc

#copia la carpeta de la app dentro del contenedor
ADD . /tarea_redes
#Esteblece el directorio predeterminado donde se ejecutará
WORKDIR /tarea_redes
#Establece la variable de entorno
ENV HOME /tarea_redes

#Instalacion
RUN wget https://ftp.postgresql.org/pub/source/v14.2/postgresql-14.2.tar.bz2
RUN tar -xvf postgresql-14.2.tar.bz2

WORKDIR $HOME/postgresql-14.2

RUN ./configure --without-readline --without-zlib
RUN make && su && make install && adduser postgres

EXPOSE 5432

#sudo docker build -t server_postgres .
#autoconf: Configura automaticamente el codigo fuente de un software para adaptarlo a cualquier sistema unix.
#automake: Produce un gestor de paquetes portables.
#build-essential: Paquete que incluye una collecion de compiladores.
#expect: Controla el dialogo entre programas.