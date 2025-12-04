# Install Docker

sudo apt update
sudo apt install -y docker.io

# Add your user to docker group

sudo usermod -aG docker $USER
newgrp docker

# Start Minikube with Docker driver

minikube start --driver=docker --memory=1024mb --cpus=1

## After initail the cluster, next time we just using command to start or stop minikube normaly

minikube start

minikube stop
