# syntax=docker/dockerfile:1
# transigner - transcript quantification from long read sequencing data 

## PREAMBLE

## == BASE IMAGE == ##
FROM mambaorg/micromamba:alpine3.20

## Change shell to expose /bin/bash
#SHELL ["/bin/bash", "--login" ,"-c"]

## == ENV VARIABLES == ##
ENV TRANSIGNER_VERSION="1.1.3"

## == LABELS == ##
LABEL dockerfile.maintainer="Dean Bašić"
LABEL software.name="transigner"
LABEL software.developers="Hyun Joo Ji, Mihaela Pertea"
LABEL software.home="https://github.com/haydenji0731/transigner"
LABEL software.version="1.1.3"
LABEL publication.doi="https://doi.org/10.1101/2024.04.13.589356"
LABEL base.image="micromamba:alpine3.20"
LABEL python.version="3.9"

## BODY 

## Change USER
USER root

### Download transigner source 

RUN mkdir /apps 
WORKDIR /apps 

RUN wget -q https://github.com/haydenji0731/transigner/archive/refs/tags/v${TRANSIGNER_VERSION}.zip -O /apps/transigner-${TRANSIGNER_VERSION}.zip && \
    unzip /apps/transigner-${TRANSIGNER_VERSION}.zip && \
    rm /apps/transigner-${TRANSIGNER_VERSION}.zip 

WORKDIR /apps/transigner-1.1.3

# Add transigner directory to PATH, this will allow the use of eash.sh script
ENV PATH="${PATH}:/apps/transigner-1.1.3"

### Apk installs with --no-cache option to save space 
### Packages for compiling transigner, and bash to allow easy.sh to run

RUN apk add --no-cache \
    make \
    musl-dev \
    gcc \
    bash \
    libgomp 

### Create micromamba(conda) environment and install a single package into it

RUN micromamba \
    create -n transigner bioconda::minimap2  

# Activate the environment

ARG MAMBA_DOCKERFILE_ACTIVATE=1 

# Install the remainder of the packages 

RUN micromamba install --yes \ 
    bioconda::samtools \
    conda-forge::pip \
    bioconda::pysam \
    conda-forge::numpy \
    conda-forge::pandas && \
    make CFLAGS="-fopenmp" && \
    pip install --no-cache-dir . && \
    micromamba clean --all --yes && \
    chmod -R a+rX /apps 

# Add mamba packages to path 

ENV PATH="${PATH}:/opt/conda/envs/transigner/bin/"

## == CLEAN UP == ##

RUN apk del \
    make \
    musl-dev \
    gcc 

CMD ["transigner"]

# Creating an user for non root executions inside the container...
#RUN groupadd user && useradd -r -g user user && chown user:user .
#RUN addgroup -S user && adduser -S user -G user

#USER user
# END 
