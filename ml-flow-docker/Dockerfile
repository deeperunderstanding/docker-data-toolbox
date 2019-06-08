FROM python:3.7.0

#-------------------
# ml-flow-server
# - add artifact store
# - add db backend store (postgres)
#-------------------

RUN pip install mlflow==1.0.0
RUN pip install psycopg2

EXPOSE 5000

RUN mkdir -p /server
WORKDIR /server
COPY . /server

#RUN apt install netcat
RUN chmod +x wait-for-it.sh

RUN mkdir /mlflow/

CMD ./wait-for-it.sh postgres:5432 -- mlflow server \
    --backend-store-uri postgresql://postgres:admin@postgres:5432/mlflow \
    --default-artifact-root /mlflow \
    --host 0.0.0.0
