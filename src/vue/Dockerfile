FROM charles1416/devcontainer-images-debian:latest

RUN bash -c "echo '===== Replacing Source =====' \
    && sed -i -e 's?deb.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        -e 's?security.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        /etc/apt/sources.list \
    && apt -y update \
    && apt -y install nodejs \
    && apt -y install npm \
    && npm config set registry http://registry.npm.taobao.org \
    && npm install -g cnpm --registry=http://registry.npm.taobao.org \
    && npm install -g vue \
    && npm install -g @vue/cli \
    && npm install -g @vitejs/plugin-vue \
    && npm install -g vite \
    && npm install -g n \
    && n stable" 
