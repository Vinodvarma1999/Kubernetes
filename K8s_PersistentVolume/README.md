# Managing Data Persistence in Kubernetes Deployments with Persistent Volumes and Claims

This guide will walk you through the process of creating a pod in a Kubernetes cluster, creating a file within that pod, deleting the pod, and verifying that the file still exists in a new pod that is created using the same deployment.

## Prerequisites

To follow along with this guide, you will need:

- A running Kubernetes cluster
- `kubectl` command-line tool installed on your local machine and configured to connect to your Kubernetes cluster

## Step 1: Create a Pod and Create a File

1. Apply the provided YAML file to create a deployment and a pod in the Kubernetes cluster:

``` kubectl apply -f deployment.yaml ```

2. Exec into the pod to create a file:

``` kubectl exec -it <pod-name> -- /bin/bash ```
``` echo "Hello, World!" > /data/example/hello.txt ```
``` exit ```


Replace `<pod-name>` with the name of the pod that was created by the deployment.

## Step 2: Delete the Pod by Deleting the Deployment

To simulate a failure, delete the pod by deleting the deployment that was used to create it:

``` kubectl delete deployment example-deployment ```

## Step 3: Create a New Pod and Verify that the File Exists

1. Apply the same YAML file to create a new pod with a different name, but using the same PVC as before:

``` kubectl apply -f deployment.yaml ```

2. Exec into the new pod to verify that the file still exists:

``` kubectl exec -it <new-pod-name> -- /bin/bash ```
``` cat /data/example/hello.txt ```
``` exit ```

Replace `<new-pod-name>` with the name of the new pod that was created by the deployment.

## Conclusion

In this guide, we created a pod in a Kubernetes cluster, created a file within that pod, deleted the pod, and verified that the file still exists in a new pod that is created using the same deployment. By using Persistent Volumes and Persistent Volume Claims, we were able to ensure that our data was persisted across pod failures.

