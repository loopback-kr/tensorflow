FROM tensorflow/tensorflow:2.0.0-gpu-py3-jupyter

# Change Ubuntu repository address to DaumKaKao
RUN sed -i 's/archive.ubuntu.com/mirror.loopback.kr/g' /etc/apt/sources.list

# Install essential packages
RUN apt update && \
    apt install -y \
        git \
        vim \
        tree \
        wget \
        zip \
        unzip \
        libglu1-mesa-dev \
        libglib2.0-0

# Configure default Pypi repository address and default progress bar style
RUN mkdir ~/.pip && \
    echo -e \
"[global]\n"\
"index-url=http://mirror.loopback.kr/pypi/simple/\n"\
"trusted-host=mirror.loopback.kr\n"\
"progress-bar=emoji"\
        > ~/.pip/pip.conf && \
    pip install --upgrade pip && \
    pip install --no-cache-dir \
        matplotlib \
        numpy

# Add alias
RUN alias l="ls -alh --full-time" && \
    alias cls='clear'

# Delete unnecessary data
RUN rm -rf /var/lib/apt/lists/*

# Write maintainer information
LABEL maintainer="LIM HYUN SEOK <contact@loopback.kr>"
