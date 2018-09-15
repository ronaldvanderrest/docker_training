FROM postgres:9.6

WORKDIR /usr/share/postgresql/9.6
COPY *.conf ./
WORKDIR /docker-entrypoint-initdb.d
COPY init-db.sql init-db.sql
ENV POSTGRES_USER="gordonuser" POSTGRES_DB="ddev"

