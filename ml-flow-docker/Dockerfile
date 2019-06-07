FROM python:3.7.0

#-------------------
# ml-flow-server
# - add artifact store
# - add db backend store (postgres)
#-------------------

RUN mkdir /mlflow/

RUN pip install mlflow==1.0.0
RUN pip install psycopg2

EXPOSE 5000

CMD mlflow server \
    --backend-store-uri postgresql://postgres:admin@postgres:5433/mlflow \
    --default-artifact-root /mlflow \
    --host 0.0.0.0
