FROM continuumio/miniconda3
RUN apt-get update && apt-get install -y git

RUN conda install -c conda-forge shap  # binary pkg not available in pip
RUN pip install mlflow==2.2.2 psycopg2-binary pymysql boto3
RUN pip install mlflow==2.2.2
RUN pip install boto3

RUN cd /home && git clone https://github.com/mlflow/mlflow-example.git \
    && cd mlflow-example && git checkout v1.0.0 \
    && sed -i 's/mlflow/mlflow\=\=2.2.2/' conda.yaml \
    && echo "  - python<3.11" >> conda.yaml \
    && echo "  - boto3" >> conda.yaml 
