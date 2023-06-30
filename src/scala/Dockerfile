FROM ghcr.io/charles1614/devcontainer-images/debian:latest

# RUN curl -s "https://get.sdkman.io" | bash 
ARG JDK_VERSION=11.0.12-open
ARG MAVEN_VERSION=3.8.8
ARG SCALA_VERSION=2.12.10

# sdkman 
RUN bash -c "echo '===== Replacing Source =====' \
    && sed -i -e 's?deb.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        -e 's?security.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        /etc/apt/sources.list \
    && apt -y update \
    && echo '===== Install sdkman dependencies =====' \
    && apt -y install git curl zip unzip \
    && echo '===== Instal sdkman =====' \
    && curl -s 'https://get.sdkman.io' | bash \
    && source '$HOME/.sdkman/bin/sdkman-init.sh' \
    && echo '===== Install OpenJDK ${JDK_VERSION}' ===== \
    && sdk install java ${JDK_VERSION} \
    && echo '===== Install Maven ${MAVEN_VERSION} =====' \
    && sdk install maven ${MAVEN_VERSION} \
    && sdk install mvnd \
    && echo '===== Install Scala ${SCALA_VERSION} =====' \
    && sdk install scala ${SCALA_VERSION} \
    && rm -rf $HOME/.sdkman/archives/* \
    && rm -rf $HOME/.sdkman/tmp/*"