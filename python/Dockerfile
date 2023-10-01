FROM python:3.9.10-slim-buster

RUN apt-get update && \
    apt-get -y install gcc libmariadb-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
RUN /usr/local/bin/python -m pip install --upgrade pip
RUN pip install mysql-connector-python

COPY ./python/src/ /app/

WORKDIR /app

# ここにDocker起動時に起動するpythonファイルを書く(テーブルを作ったりする)
CMD python ./make_table.py