# nginx-monitoring

## Overview

This project aims to monitor the nginx web server using Prometheus and Grafana.

## Prerequisites
- Kubernetes cluster
- Helm
- kubectl

## Installation

1. Clone the repository: `git clone https://github.com/omeritzhaki320/nginx-monitoring.git`
2. Install the nginx deployment using the following command:
    - `kubectl apply -f nginx-deployment.yaml`
    - `kubectl apply -f nginx-configmap.yaml`
    - `kubectl apply -f nginx-hpa.yaml`
3. Install Prometheus and Grafana using the following commands:
   - `helm install prometheus ./prometheus -f ./prometheus/values.yaml`
   - `helm install grafana ./grafana -f ./grafana/values.yaml`

## Usage
1. Access Grafana: `http://localhost:3000`
2. Access Prometheus: `http://localhost:9090`

## Cleanup
- `kubectl delete -f nginx-deployment.yaml`
- `kubectl delete -f nginx-configmap.yaml`
- `kubectl delete -f nginx-hpa.yaml`
- `helm uninstall prometheus`
- `helm uninstall grafana`

