FROM mcr.microsoft.com/devcontainers/java:1-17-bookworm

# install dependencies
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      python3-pip \
      git-lfs \
      ca-certificates \
    && rm -rf /var/lib/apt/lists/*
    
RUN pip3 install --no-cache-dir --break-system-packages requests

# download WPILib extension
COPY ./get-wpilib.py /opt
RUN python3 /opt/get-wpilib.py
