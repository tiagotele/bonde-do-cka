# Notas de estudo

## Subindo Minikube
```bash
minikube start --profile bonde-do-cka --kubernetes-version 1.22.2  --driver=docker
```

### Criando pod manualmente
```
 kubectl run nginx --image nginx --port=80
```

### Criando deployment
```
 kubectl create -f meu_primeiro_deployment.yaml
```

### Expondo component no cluster
kubectl expose deployment nginx

>Default é ClusterIP


### Obter o IP dos pods
kubectl get endoints