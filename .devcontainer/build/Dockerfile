# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.155.1/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"

ARG user=unknown
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    docker.io \
    openssh-client socat build-essential

RUN mkdir /root/tools

WORKDIR /tmp

RUN curl -# -OL https://github.com/adoptium/temurin11-binaries/releases/download/jdk-11.0.12%2B7/OpenJDK11U-jdk_x64_linux_hotspot_11.0.12_7.tar.gz
RUN curl -# -OL https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u302-b08/OpenJDK8U-jdk_x64_linux_hotspot_8u302b08.tar.gz
RUN tar -C /root/tools -xzf OpenJDK11U-jdk_x64_linux_hotspot_11.0.12_7.tar.gz
RUN tar -C /root/tools -xzf OpenJDK8U-jdk_x64_linux_hotspot_8u302b08.tar.gz

ENV PATH=$PATH:/root/.jenv/bin:/root/tools/jdk8u302-b08/bin