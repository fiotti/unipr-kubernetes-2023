Demo Kubernetes
===============

Questo repository permette di configurare il deployment di un microservizio
con la relativa configurazione, un service, ed un ingress.


## Installazione

Nginx
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.3/deploy/static/provider/cloud/deploy.yaml
```

Microservizio
```bash
kubectl create namespace my-namespace
kubectl apply -f 0_my-service-configmap.yml
kubectl apply -f 1_my-service-deployment.yml
kubectl apply -f 2_my-service-service.yml
kubectl apply -f 4_my-service-ingress.yml
```


## Disinstallazione

Microservizio
```bash
kubectl delete all --all -n my-namespace
kubectl delete namespace my-namespace
```

Nginx
```bash
kubectl delete all --all -n ingress-nginx
kubectl delete namespace ingress-nginx
```
