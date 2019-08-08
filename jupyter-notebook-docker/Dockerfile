# Base Image: jupyter/scipy-notebook 
# - contains most common libspandas numpy, matplotlib etc. 
# - also dask is already included 
# - lab is enabled
# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
FROM jupyter/scipy-notebook

#TODO just extend from the tf image instead

USER $NB_USER

RUN conda install --quiet --yes \
    'tensorflow=1.13*' \
    'keras=2.2*' \
    'mlflow'

RUN conda install --quiet --yes pytorch-cpu torchvision-cpu -c pytorch

RUN pip install influxdb boto3

RUN conda install --quiet --yes \
    'arrow' \
    'requests'

RUN conda clean --all -f -y && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER
