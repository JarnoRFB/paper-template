FROM thomasweise/texlive

ARG uid
ARG gid

RUN apt-get update \
    && apt-get install -y bash git vim fish \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -g ${gid} developer \
    && useradd -g developer -u ${uid} -m developer

USER developer

RUN mkdir -p ~/.ssh \
    && mkdir -p ~/.vscode-server \
    && echo 'eval `ssh-agent -s`' >> ~/.profile

ENV HOME=/home/developer
ENV SHELL=/usr/bin/fish
