# MDB CE Self-Serve POC

Welcome to the **MDB CE Self-Serve POC** project! This repository contains a proof-of-concept (POC) for a self-serve solution designed for MongoDB Community clusters running on Kubernetes. 

## Overview

The solution is built to operate seamlessly on Kubernetes and consists of the following components:

- **[mdb-self-serve-poc-api](https://hub.docker.com/r/sebastianrichter/mdb-self-serve-poc-api)**: The backend API that handles requests and manages interactions with the MongoDB database.
- **[mdb-self-serve-poc-ui](https://hub.docker.com/r/sebastianrichter/mdb-self-serve-poc-ui)**: The frontend user interface that allows users to interact with the self-serve solution.
- **[mongo](https://hub.docker.com/_/mongo)**: The datastore used to store application data.

## Prerequisites

Before you get started, ensure you have the following installed:

- [Minikube](https://minikube.sigs.k8s.io/docs/start/) - for running Kubernetes locally.
- [Helm](https://helm.sh/docs/intro/install/) - for managing Kubernetes applications.
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) - the command-line tool for interacting with Kubernetes clusters.

## Getting Started

Follow these steps to set up the self-serve solution on your local Kubernetes cluster:

1. **Start Minikube**: Allocate resources for your Minikube cluster.
   ```sh
   minikube start --cpus=4
   ```
2. **Install the MongoDB Community Operator**: Use Helm to install the MongoDB Community Operator.
   ```sh
   helm install community-operator mongodb/community-operator
   ```
3. **Deploy the Application**: Apply the deployment configuration to your Kubernetes cluster.
   ```sh
   kubectl apply -f deployment.yaml
   ```
4. **Expose the Services**: Create a tunnel to access the services running in your Minikube cluster.
   ```sh
   minikube tunnel
   ```

## Accessing the Application
Once the services are up and running, you can access the UI through your web browser. The URL will typically be http://localhost.

After creating a new cluster, open a new terminal window and run `kubectl get mdbc -w -o yaml` to observe cluster creation.

