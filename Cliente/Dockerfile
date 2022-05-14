FROM python:3.8
ENV TZ=America/Santiago
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt update
RUN apt-get install -y \
    build-essential \
    curl \
    apt-utils
RUN apt-get install -y python3-pip
RUN apt-get install -y python-dev libpq-dev libevent-dev
RUN pip install pgcli

CMD pgcli