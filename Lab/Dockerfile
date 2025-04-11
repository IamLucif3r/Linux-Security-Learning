FROM ubuntu:22.04

# Default Environment Variables
ENV USER=developer
ENV PASSWORD=lab123
ENV WORKDIR=/home/${USER}/workspace

RUN apt update && apt install -y \
    curl wget git sudo nano unzip tar linux-tools-common\
    python3 python3-pip \
    build-essential ca-certificates gnupg \
    strace lsof htop sysdig \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash $USER && echo "${USER}:${PASSWORD}" | chpasswd && adduser ${USER} sudo

RUN curl -fsSL https://code-server.dev/install.sh | sh

USER $USER

RUN mkdir -p $WORKDIR

EXPOSE 8080

WORKDIR $WORKDIR

CMD ["code-server", "--bind-addr", "0.0.0.0:8080", "--auth", "none"]
