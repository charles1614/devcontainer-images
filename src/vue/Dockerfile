FROM charles1416/devcontainer-images-debian:latest

RUN bash -c "echo '===== Replacing Source =====' \
    && sed -i -e 's?deb.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        -e 's?security.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        /etc/apt/sources.list \
    && apt -y update \
    && apt install nodejs \
    && apt install npm \
    && npm config set registry http://registry.npm.taobao.org \
    && npm install -g cnpm --registry=http://registry.npm.taobao.org \
    && cnpm install vue \
    && cnpm install @vue/cli \
    && npm install n -g \
    && n stable" 