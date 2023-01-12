FROM nvidia/cuda:11.3.0-cudnn8-runtime-ubuntu20.04

RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y wget

RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN bash Miniconda3-latest-Linux-x86_64.sh -b -p /miniconda
ENV PATH=$PATH:/miniconda/pcondabin:/miniconda/bin

RUN conda update -n base -c defaults conda
RUN conda create -n release python=3.6

SHELL ["conda","run","-n","release","/bin/bash", "-c"]

COPY environment environment
RUN conda install --yes --file environment/conda.txt
RUN conda install -c rdkit rdkit nox cairo
RUN conda install pytorch=1.10.1 torchvision=0.11.2 -c pytorch -c conda-forge
RUN pip install -r environment/pip.txt

WORKDIR /home

RUN git clone https://github.com/isayev/ReLeaSE.git .

ENTRYPOINT ["conda", "run", "-n", "release", "jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]