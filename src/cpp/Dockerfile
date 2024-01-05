ARG VARIANT=noetic-ros-base-focal
ARG BASE_IMAGE=ros
FROM ${BASE_IMAGE}:${VARIANT}

RUN apt-get update \
        && export DEBIAN_FRONTEND=noninteractive \
        && apt-get -y install --no-install-recommends clang-format unzip