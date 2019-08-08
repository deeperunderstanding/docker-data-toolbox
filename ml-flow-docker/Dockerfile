FROM python:3.7.0

RUN pip install mlflow boto3
RUN pip install psycopg2

EXPOSE 5000

RUN mkdir -p /server
WORKDIR /server
COPY wait-for-it.sh /server

RUN chmod +x /server/wait-for-it.sh

#might not need that since artifacts go to the client
#RUN mkdir /mlflow/

CMD ./wait-for-it.sh postgres:5432 -- mlflow server \
    --backend-store-uri postgresql://postgres:admin@postgres:5432/mlflow \
    --default-artifact-root s3://${ARTIFACT_AWS_BUCKET}/artifacts \
    --host 0.0.0.0
