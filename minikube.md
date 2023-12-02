To install Minikube and `kubectl` on an AWS Ubuntu instance, you can follow these steps:

### Installing kubectl

1. **Update the package list:**

```bash
sudo apt-get update
```

2. **Download and install kubectl:**

```bash
sudo apt-get install -y apt-transport-https ca-certificates curl

# Download the latest release with the command:
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Validate the binary (optional)

#Download the kubectl checksum file:
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

# Validate the kubectl binary against the checksum file:
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check

# If valid, the output is:
kubectl: OK
#If invalid, it will show a different hash in the output.

#Install kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

#Test to ensure the version you installed is up-to-date:
kubectl version --client
```
### Installing Docker
```bash
sudo apt-get install -y docker.io

#Start and Enable Docker Service:
sudo systemctl start docker
sudo systemctl enable docker
#Add docker user to 
sudo usermod -aG docker ubuntu

```


### Installing Minikube

1. **Download the Minikube binary:**

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64


# Make the binary executable
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

2. **Start Minikube:**

```
minikube start 
```
