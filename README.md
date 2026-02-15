# lab
Yup!  All exploratory labs.

Inspired by Miischa van den Burg - Thank you Sir!
https://github.com/mischavandenburg/lab

# Setting up Prometheus via helm
https://github.com/prometheus-community/helm-charts
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update

helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace=monitoring --create-namespace

helm upgrade prometheus-stack prometheus-community/kube-prometheus-stack -n monitoring --values values.yaml
```

# Recap
* Deployment
* Service
* Storage

# Next up

## Ingress
** ingressClass: traefik
** expose mealie

## beyond
** GitOps
** Certificate Management
** Databases
** On-prem with k3s and Talos

