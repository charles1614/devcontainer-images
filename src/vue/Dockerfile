FROM charles1416/devcontainer-images-debian:latest

RUN bash -c "echo '===== Replacing Source =====' \
    && sed -i -e 's?deb.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        -e 's?security.debian.org?mirrors.tuna.tsinghua.edu.cn?g' \
        /etc/apt/sources.list \
    && apt -y update \
    && apt -y install nodejs \
    && apt -y install npm \
    && apt -y install python3-distutils \
    && apt -y install tmux \
    && npm config set registry http://registry.npm.taobao.org \
    && npm install -g cnpm --registry=http://registry.npm.taobao.org \
    && npm install -g n \
    && n stable" 

RUN sh -c "echo '===== Use Zsh =====' \
    && wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.5/zsh-in-docker.sh \
    && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting \
    && git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions \
    && sed -i 's/plugins=(git)/plugins=(git zsh-autosuggestions zsh-syntax-highlighting)/g' ~/.zshrc"
    
ENV PIP_ROOT_USER_ACTION=ignore
RUN bash -c "echo '==== Install Miniconda ====' \
    && mkdir -p ~/miniconda3 \
    && wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh \
    && bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3 \
    && rm -rf ~/miniconda3/miniconda.sh \
    && ~/miniconda3/bin/conda init bash \
    && ~/miniconda3/bin/conda init zsh"
