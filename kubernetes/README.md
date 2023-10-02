
## ddosify

<https://github.com/ddosify/alaz>

```bash
helm repo add ddosify https://ddosify.github.io/ddosify-helm-charts/
helm repo update

kubectl create namespace ddosify
helm upgrade --install --namespace ddosify ddosify ddosify/ddosify --wait

# Add a cluster on the Observability page of your Self-Hosted frontend. You will receive a Monitoring ID and instructions.

export MONITORING_ID=xxxxxxxxxx
export BACKEND_HOST=http://backend.ddosify.svc.cluster.local:8008
helm upgrade --install --namespace ddosify alaz ddosify/alaz --set monitoringID=$MONITORING_ID --set backendHost=$BACKEND_HOST
```