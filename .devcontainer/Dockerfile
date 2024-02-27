# Use an official Python base image with the latest version
FROM python:3.12-slim

# Install basic tools
RUN apt-get update && apt-get install -y \
    curl \
    git \
    vim \
    bash-completion \
    && rm -rf /var/lib/apt/lists/*

# Install kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# Install Helm
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 \
    && chmod 700 get_helm.sh \
    && ./get_helm.sh

# Set the default shell to bash instead of sh
SHELL ["/bin/bash", "-c"]
