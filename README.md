# Kubernetes

<img align="centre" alt="k8s" width=200 height=100 src="Images/k8s.jpg"> 

This repository contains YAML files and scripts for deploying and managing applications in a Kubernetes cluster.

## Getting Started

To get started with this project, you'll need to have a Kubernetes cluster up and running, and `kubectl` installed on your local machine.

1. Clone this repository:

``` git clone https://github.com/Vinodvarma1999/Kubernetes.git ```

2. Modify the YAML files in the `manifests` directory to match your desired application configuration.

3. Apply the YAML files to create the necessary resources in your Kubernetes cluster:

``` kubectl apply -f manifests/ ```

4. Verify that the resources have been created successfully:

```sh 
kubectl get pods
kubectl get services
kubectl get deployments
```

## Contributing

We welcome contributions to this project!


