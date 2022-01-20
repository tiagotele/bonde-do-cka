# Day 1

## Services

Tipos de service: `ClusterIP`, `NodePort`, `LoadBalancer`

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

### Criando service a partir de um service criado dinamicamente
```
k get services nginx -o yaml > meu_primeiro_service.yaml
```

### Exportando svc como sendo NodePort
k expose deployment nginx --type=NodePort


> Range de portas do NodePort do svc: 30k at[e 32k]

> Múltiplos yamls podem ficar em umúnico arquivo separadando os yamls por 3 hífens: `---`