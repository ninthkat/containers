FROM pytorch/pytorch:2.0.1-cuda11.7-cudnn8-devel

RUN conda install -c conda-forge -y jupyterlab

RUN useradd -ms /bin/bash jovyan

WORKDIR /home/jovyan

USER jovyan

EXPOSE 8888

ENV PIP_USER=1

ENTRYPOINT /opt/conda/bin/jupyter-lab --ip 0.0.0.0

