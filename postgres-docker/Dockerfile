FROM postgres:alpine

#The default postgres image runs init.sql in the below folder on startup
#yeah but seems like you can't really do it after starting the db ...
COPY init.sql /docker-entrypoint-initdb.d/