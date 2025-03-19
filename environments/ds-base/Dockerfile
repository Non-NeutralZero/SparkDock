# Pinning Args here for easier editing
ARG BASE_CONTAINER=debian:11
ARG PYTHON_VERSION=3.9

ENV LANG=C.UTF-8 LC_ALL=C.UTF-8
ENV PATH /opt/conda/bin:$PATH

FROM $BASE_CONTAINER

USER root

RUN apt-get update --yes && apt-get upgrade --yes && \
    # installations
    apt-get install -y --no-install-recommends \
    bzip2 \
    ca-certificates \
    git \
    libglib2.0-0 \
    libsm6 \
    libxcomposite1 \
    libxcursor1 \
    libxdamage1 \
    libxext6 \
    libxfixes3 \
    libxi6 \
    libxinerama1 \
    libxrandr2 \
    libxrender1 \
    mercurial \
    openssh-client \
    procps \
    subversion \
    locales \
    sudo \
    tini \
    wget && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen


# CONDA and Mamba installs
ARG ANACONDA_URL="https://repo.anaconda.com/archive/Anaconda3-2023.03-1-Linux-x86_64.sh"
ARG CONDASHA256SUM="95102d7c732411f1458a20bdf47e4c1b0b6c8a21a2edfe4052ca370aaae57bab"

RUN wget "${ANACONDA_URL}" -O anaconda.sh -q && \
    echo "${CONDASHA256SUM} anaconda.sh" > shasum && \
    sha256sum --check --status shasum && \
    /bin/bash anaconda.sh -b -p /opt/conda && \
    rm anaconda.sh shasum && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "conda activate base" >> ~/.bashrc 

RUN conda install -c conda-forge mamba

CMD [ "/bin/bash" ]