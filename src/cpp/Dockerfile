ARG VARIANT=11-slim
ARG BASE_IMAGE=debain
FROM ${BASE_IMAGE}:${VARIANT}

RUN apt-get update \
        && export DEBIAN_FRONTEND=noninteractive \
        && apt-get -y install --no-install-recommends clang-format