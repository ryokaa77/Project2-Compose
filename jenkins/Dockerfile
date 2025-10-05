FROM jenkins/jenkins:lts-jdk17

USER root

# Install Node.js 16, npm, Docker CLI, curl, jq, and Snyk CLI
RUN apt-get update -qq && \
    apt-get install -y -qq curl jq ca-certificates gnupg lsb-release && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt-get install -y -qq nodejs && \
    curl -fsSL https://get.docker.com | sh -s -- --client-only && \
    npm install -g snyk && \
    rm -rf /var/lib/apt/lists/*

# Verify installation
RUN node -v && npm -v && docker --version && snyk --version && jq --version


USER jenkins
