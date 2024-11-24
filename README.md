# Focus.io Kubernetes Operator

This repository contains the Kubernetes operator for **Focus.io**, a container-based application and resource management platform. This operator automates the installation, configuration, and management of services related to **Focus.io** in a Kubernetes cluster.

## Description

The **Focus.io** operator aims to simplify the deployment and management of essential resources for the platform. Some of its key functionalities include:

- **Automated ArgoCD Installation and Configuration**: Installs and configures ArgoCD in the Kubernetes cluster with default settings.
- **Application Management**: Automates the creation, update, and management of applications within **Focus.io**.
- **Scalability and Extensibility**: The operator is designed to be easily extendable, allowing you to add more components or services in the future, such as **Prometheus**, **Grafana**, etc.

## Key Features

- Automated installation of **ArgoCD**.
- Deployment of **Focus.io** services and resources.
- Flexibility to extend the operator to additional components like **Prometheus** and **Grafana**.
- Efficient management and monitoring of applications.
- Integration with Kubernetes CRDs for declarative resource management.

## Prerequisites

Before using this operator, make sure you have the following prerequisites:

- A running Kubernetes cluster.
- `kubectl` configured and connected to your Kubernetes cluster.
- [Helm](https://helm.sh/docs/intro/install/) installed for managing additional services and components.
- Basic knowledge of Kubernetes, CRDs, and Helm.

## Installation

### Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/focus-operator.git
cd focus-operator
```

### Step 2: Install the Operator in Kubernetes
To install the operator in your Kubernetes cluster, run the following command:

```bash
kubectl apply -f deploy/operator.yaml
```
This will apply the necessary manifests to deploy the operator.

### Step 3: Configure the Operator

You can configure the operator using Custom Resource Definitions (CRDs). Create a YAML configuration file defining the resources the operator will manage. Here is an example configuration:

```bash
apiVersion: focus.io/v1alpha1
kind: FocusApp
metadata:
  name: my-focus-app
spec:
  argoCD:
    enabled: true
    version: "v2.0.0"
  additionalServices:
    - prometheus
    - grafana
```
Apply the configuration with the following command:

```bash
kubectl apply -f your-focus.yaml
```

The operator will install and configure ArgoCD, as well as any additional services such as Prometheus and Grafana as specified in the configuration.

## Contributing

We welcome contributions to improve the Focus.io Kubernetes Operator. If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Make your changes and write tests.
4. Submit a pull request with a clear description of your changes.
