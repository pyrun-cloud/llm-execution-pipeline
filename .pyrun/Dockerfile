# Python 3.12
FROM public.ecr.aws/docker/library/python:3.12-slim

RUN apt-get update \
 && apt-get install -y sudo curl pciutils lshw

RUN adduser --disabled-password --gecos '' docker
RUN adduser docker sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER docker

RUN pip install --upgrade --ignore-installed pip wheel six setuptools \
    && pip install --upgrade --no-cache-dir --ignore-installed \
	ollama \
    ipykernel \
    ipywidgets \
    python-dotenv

RUN sudo apt-get update