# hash:sha256:d9f7cb1159d40f471f51ff98fbc3ddfcaa720878136be8b1fe4c7cb6c09ca304
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.0.9-miniconda4.9.2-python3.8-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y \
        jupyterlab==3.0.9 \
    && conda clean -ya

RUN pip3 install -U --no-cache-dir \
    scikit-learn==1.3.2

COPY postInstall /
RUN /postInstall
