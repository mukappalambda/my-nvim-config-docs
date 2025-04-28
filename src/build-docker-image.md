# Building Docker Image

The aim of this note is to provide a ready-to-use Dockerfile in which the nvim config has already been set.

The primary benefit of using this Dockerfile is to quickly set up an development environment but not pollute your existing host machine. You can freely tweak its layout to suit your needs.

```dockerfile
FROM ubuntu:24.04

SHELL ["/bin/bash", "-c"]

ARG USERNAME=appuser
ENV HOME=/home/$USERNAME

RUN groupadd -g 1001 $USERNAME && \
    useradd -u 1001 -g $USERNAME -m -s /bin/bash $USERNAME && \
    apt update && \
    DEBIAN_FRONTEND=noninteractive apt install --no-install-recommends \
    curl gcc git make wget vim unzip zip python3-dev python3-venv -y && \
    apt clean && rm -rf /var/lib/apt/lists/*

USER $USERNAME

ENV NVIM_DIR="$HOME/.nvm"
ARG NVIM_VERSION=v0.10.3

WORKDIR $HOME

RUN mkdir -p $HOME/.local && \
    wget https://github.com/neovim/neovim/releases/download/"${NVIM_VERSION}"/nvim-linux64.tar.gz && \
    tar -C $HOME/.local -zxvf nvim-linux64.tar.gz && \
    rm -f nvim-linux64.tar.gz && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash && \
    source $HOME/.nvm/nvm.sh && \
    nvm install stable

ENV GOROOT="${HOME}/.g/go"
ENV PATH="$HOME/.local/nvim-linux64/bin:${HOME}/.g/bin:${GOROOT}/bin:${GOPATH}/bin:$PATH"
ENV G_MIRROR=https://golang.google.cn/dl/

RUN source $HOME/.bashrc && \
    curl -sSL https://raw.githubusercontent.com/voidint/g/master/install.sh | bash && \
    g install 1.24.2 && \
    mkdir -p $HOME/.config/nvim && \
    git clone https://github.com/mukappalambda/my-nvim-config.git $HOME/.config/nvim && \
    cd $HOME/.config/nvim && \
    git checkout develop && \
    cd $HOME && \
    echo "alias v=nvim" >> $HOME/.bashrc

WORKDIR $HOME/src

CMD ["/bin/bash"]
```

To build the image, run:

```bash
docker build -t my-nvim-config .
```

To create a container using this image, run:

```bash
docker run -it --rm my-nvim-config
```
