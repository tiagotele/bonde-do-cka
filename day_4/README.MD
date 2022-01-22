# Day 4

Para usar o volume no minikube:

```
minikube addons disable default-storageclass
k create -f day_4/storageclass.yaml
k create -f day_4/pv.yaml
k create -f day_4/pvc.yaml
```