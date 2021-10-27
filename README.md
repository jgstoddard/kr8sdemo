# kr8sdemo
Cluster app for demo-ing kr8s

# Installation:

This demo app assumes you have Docker and Kubernetes installed on your local machine

After cloning the repo: 

Step 1: Install [Skaffold](https://skaffold.dev/docs/install/#standalone-binary) following directions for your Operating System.  (Homebrew is recommended for MacOS)

Step 2: Install [Nginix Ingress](https://kubernetes.github.io/ingress-nginx/deploy/)

```console
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.0.4/deploy/static/provider/cloud/deploy.yaml
```
Step 3: Create monitoring namespace in kubernetes cluster

```console
kubectl create namespace monitoring
```

Step 4: Deploy all monitoring objects to cluster.  From kr8sdemo root directory, run the following command in terminal:

```console
kubectl apply -f infra/monitoring
```

Step 5: Run Skaffold. From root directory

```console
skaffold dev
```

To access Grafana metrics, visit http://localhost:32000
To access kr8sserver API, send requests to http://localhost:31000/api/