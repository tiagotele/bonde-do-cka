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

## Limitando recursos

[Unidades de CPU e Memória que o k8s utiliza](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/#resource-units-in-kubernetes)


Estressando a aplicação. Após um exce -it no pod, instalar o app stress:
```
apt-get update && apt-get install -y stress
```

estressar o pod:

```
stress --vm 1 --vm-bytes 505M 
```


### Taint
```
kubectl taint node <NODE_NAME> key1=value1:NoSchedule
```

ou para todos os nós

```
kubectl taint nodes --all <NODE_NAME> key1=value1:NoSchedule
```