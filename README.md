[![CircleCI](https://dl.circleci.com/status-badge/img/gh/iavinash/Operationalize-Machine-Learning-Microservice/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/iavinash/Operationalize-Machine-Learning-Microservice/tree/main)
# Operationalize Machine Learning Microservice

## Project Overview
Deploy a containerized Python flask application to serve out predictions (inference) about housing prices through API calls. It uses a a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features.

### Project Procedure
* Test project code using linting
* Complete a Dockerfile to containerize this application
* Deploy containerized application using Docker and make a prediction
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate the code has been tested



---
## Getting Started
### Setup the Environment

* Create a virtualenv and activate it
```
python3 -m venv <your_venv>
source <your_venv>/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python3 app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Installation Steps

To install `kubectl` on an AWS Cloud9 instance, you can follow these steps:

1. **Open Your AWS Cloud9 Environment**:
    - Log in to the AWS Management Console.
    - Navigate to the AWS Cloud9 service.
    - Open the Cloud9 environment that you want to work in.

2. **Update and Upgrade Packages**:
   Before installing `kubectl`, it's a good practice to update and upgrade your package repositories to ensure you have the latest package information. Run the following commands in your Cloud9 terminal:

   ```bash
   sudo yum update -y
   ```

3. **Download and Install `kubectl`**:
   You can download and install `kubectl` using the `curl` command. Here are the steps to do so:

   ```bash
   # Download the kubectl binary
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

   # Make the kubectl binary executable
   chmod +x kubectl

   # Move kubectl to a directory in your PATH
   sudo mv kubectl /usr/local/bin/
   ```


4. **Verify the Installation**:
   To verify that `kubectl` has been successfully installed, you can run the following command to check its version:

   ```bash
   kubectl version --client
   ```

   This should display the `kubectl` client version without any errors.

That's it! You should now have `kubectl` installed and ready to use on your AWS Cloud9 environment. You can configure `kubectl` to interact with your Kubernetes clusters as needed.

### Minikube Installation Steps
To install Minikube on an AWS Cloud9 environment, you can follow these steps:

1. **Install Minikube**:
   You can install Minikube by downloading the binary and placing it in a directory in your `PATH`. Here are the steps to do that:

   ```bash
   # Download the latest Minikube binary
   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

   # Make the Minikube binary executable
   chmod +x minikube-linux-amd64

   # Move Minikube to a directory in your PATH
   sudo mv minikube-linux-amd64 /usr/local/bin/minikube
   ```

   This script downloads the latest Minikube binary for Linux x86_64, makes it executable, and moves it to a directory in your system's PATH.

2. **Start Minikube**:
   You can start Minikube by running the following command:

   ```bash
   minikube start
   ```

   This command initializes and starts a single-node Kubernetes cluster using Minikube. It might take a few moments to download the necessary components.

3. **Verify Minikube**:
   After Minikube is started, you can verify its status by running:

   ```bash
   minikube status
   ```

   This command should show that Minikube is running.

4. **Use Minikube with kubectl**:
   Minikube configures `kubectl` to use the newly created cluster. You can interact with your Minikube cluster using standard `kubectl` commands.

   For example, to check the nodes in the Minikube cluster, you can run:

   ```bash
   kubectl get nodes
   ```

That's it! You should now have Minikube up and running in your AWS Cloud9 environment, and you can use it to develop and test Kubernetes applications locally.