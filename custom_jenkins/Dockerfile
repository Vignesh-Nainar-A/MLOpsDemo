# Use Jenkins as base image
FROM jenkins/jenkins:lts

# Switch to root user
USER root

# Install dependencies and Docker using the official script
RUN apt-get update -y && apt-get install -y \
    curl ca-certificates gnupg lsb-release && \
    curl -fsSL https://get.docker.com | sh

# Add Jenkins user to the Docker group
RUN usermod -aG docker jenkins

# Enable Docker-in-Docker
RUN mkdir -p /var/lib/docker
VOLUME /var/lib/docker
