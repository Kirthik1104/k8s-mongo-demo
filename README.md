# MongoDB & Mongo-Express on Kubernetes

This repository contains Kubernetes manifests for deploying MongoDB and Mongo-Express using Secrets and ConfigMaps for secure configuration.

## Contents

- [mongo-deployment.yaml](cci:7://file:///Users/kirthikraj/Desktop/kubernetes/mongo/mongo-deployment.yaml:0:0-0:0) — MongoDB Deployment & Service
- [mongo-express.yaml](cci:7://file:///Users/kirthikraj/Desktop/kubernetes/mongo/mongo-express.yaml:0:0-0:0) — Mongo-Express Deployment & Service
- [mongo-secret.yaml](cci:7://file:///Users/kirthikraj/Desktop/kubernetes/mongo/mongo-secret.yaml:0:0-0:0) — Kubernetes Secret for MongoDB credentials (base64 encoded)
- [config.yaml](cci:7://file:///Users/kirthikraj/Desktop/kubernetes/mongo/config.yaml:0:0-0:0) — ConfigMap for MongoDB service address

## Usage

1. Apply the secret and configmap:
    ```sh
    kubectl apply -f mongo-secret.yaml
    kubectl apply -f config.yaml
    ```
2. Deploy MongoDB and Mongo-Express:
    ```sh
    kubectl apply -f mongo-deployment.yaml
    kubectl apply -f mongo-express.yaml
    ```
3. Expose mongo-express with Minikube:
    ```sh
    minikube service mongo-express-service
    ```
4. Login to mongo-express:
    - **Username:** username
    - **Password:** password

## Notes

- The secret values are base64 encoded.
- For production, change the credentials and consider using a more secure approach.