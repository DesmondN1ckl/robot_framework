FROM mcr.microsoft.com/devcontainers/java:1-17-bookworm

# install dependencies
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      python3-pip \
      git-lfs \
      ca-certificates \
      curl \
      gnupg

RUN mkdir -p /etc/apt/keyrings

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor | tee /etc/apt/keyrings/yarn.gpg

RUN cat >/etc/apt/sources.list.d/yarn.sources <<EOF
      
RUN apt-get update
    && rm -rf /var/lib/apt/lists/*
    
RUN pip3 install --no-cache-dir --break-system-packages requests

# download WPILib extension
COPY ./get-wpilib.py /opt
RUN python3 /opt/get-wpilib.py
