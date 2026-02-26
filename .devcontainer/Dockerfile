FROM mcr.microsoft.com/devcontainers/java:1-17-bookworm

# install dependencies
RUN mkdir -p /etc/apt/keyrings /etc/apt/sources.list.d
RUN curl -fsSL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor > /etc/apt/keyrings/yarn.gpg
RUN echo > /etc/apt/sources.list.d/yarn.sources <<'EOF'
    Types: deb
    URIs: https://dl.yarnpkg.com/debian
    Suites: stable
    Components: main
    Signed-By: /etc/apt/keyrings/yarn.gpg
    EOF
    
RUN apt update
RUN apt install -y python3-pip git-lfs
RUN pip3 install --break-system-packages requests

# download WPILib extension
COPY ./get-wpilib.py /opt
RUN python3 /opt/get-wpilib.py