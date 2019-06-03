FROM python:3.7.0

#-------------------
# ml-flow-server
# - add artifact store
# - add db backend store (postgres)
#-------------------

RUN mkdir /mlflow/

RUN pip install mlflow==0.9.1

EXPOSE 5000

CMD mlflow server \
    --file-store /mlflow \
    --host 0.0.0.0