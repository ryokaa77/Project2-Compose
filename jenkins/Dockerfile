FROM jenkins/jenkins:lts-jdk17

USER root

RUN apt-get update && apt-get install -y curl apt-transport-https ca-certificates gnupg && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt-get install -y nodejs docker.io && \
    node -v && npm -v && docker --version && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER jenkins
