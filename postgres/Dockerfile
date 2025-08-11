FROM postgres:15-alpine

ENV POSTGRES_DB=myapp
ENV POSTGRES_USER=dbuser
ENV POSTGRES_PASSWORD=dbpass

COPY ./init-scripts/ /docker-entrypoint-initdb.d/

COPY postgresql.conf /usr/local/share/postgresql/postgresql.conf.sample

RUN mkdir -p /var/lib/postgresql/data && \
    chown -R postgres:postgres /var/lib/postgresql/data

EXPOSE 5432

USER postgres

CMD ["postgres", "-c", "config_file=/usr/local/share/postgresql/postgresql.conf.sample"]