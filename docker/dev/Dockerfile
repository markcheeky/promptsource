FROM python:3.9-bullseye

ENV SHELL=/bin/bash


RUN apt-get update && apt-get install -y \
    sudo \
    python3-pip \
    python3-venv \
    apt-utils \
    git \
    wget \
    curl


ARG USERNAME=user
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME

RUN pip3 install -U pip setuptools wheel
