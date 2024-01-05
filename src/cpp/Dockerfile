ARG VARIANT=22.04
ARG BASE_IMAGE=ubuntu
FROM ${BASE_IMAGE}:${VARIANT}

RUN apt-get update \
        && export DEBIAN_FRONTEND=noninteractive \
        && apt-get -y install --no-install-recommends clang-format unzip