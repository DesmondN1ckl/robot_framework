FROM mcr.microsoft.com/devcontainers/java:1-17-bookworm

# install dependencies
RUN rm -f /etc/apt/sources.list.d/yarn.list /etc/apt/sources.list.d/yarn.sources

RUN apt-get update && apt-get install -y --no-install-recommends \
    python3-pip \
    git-lfs \
  && rm -rf /var/lib/apt/lists/*
    
RUN pip3 install --no-cache-dir --break-system-packages requests

# download WPILib extension
COPY ./get-wpilib.py /opt
RUN python3 /opt/get-wpilib.py
