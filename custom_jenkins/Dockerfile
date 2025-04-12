# Use the Jenkins LTS image as the base
FROM jenkins/jenkins:lts

# Switch to root to install Docker and dependencies
USER root

# Install Docker Engine (updated method for Debian)
RUN apt-get update -y && \
    apt-get install -y ca-certificates curl gnupg lsb-release && \
    mkdir -p /etc/apt/keyrings && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
    $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null && \
    apt-get update -y && \
    apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin && \
    apt-get clean

# Add Jenkins user to the Docker group
RUN groupadd -f docker && \
    usermod -aG docker jenkins

# Create Docker directory and volume for Docker-in-Docker (optional)
RUN mkdir -p /var/lib/docker
VOLUME /var/lib/docker

# Switch back to Jenkins user
USER jenkins



