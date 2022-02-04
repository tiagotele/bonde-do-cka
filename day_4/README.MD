# Day 4

Para usar o volume no minikube:

```
minikube addons disable default-storageclass
k create -f day_4/storageclass.yaml
k create -f day_4/pv.yaml
k create -f day_4/pvc.yaml
```

## CronJob
minikube start --profile bonde-do-cka --kubernetes-version 1.22.2  --driver=docker --nodes 3
k create -f primeiro-cron.yaml
k get cronjobs
k get cj
k describe cj giropops-cron
k get jobs --watch
k get pods
k logs <POD_NAME>
k logs <POD_NAME>
k describe pod <POD_NAME>

## Secrets
```
echo -n "giropops strigus girus" > secret.txt
cat secret.txt
k get secrets
k create secret generic my-secret --from-file secret.txt
k get secrets
k describe secret my-secret
k get secrets my-secret -o yaml

k create -f test-secret.yaml
k describe pod test-secret
k exec -it test-secret sh

k create secret generic my-literal-secret --from-literal user=linuxtips --from-literal password=catota

k create -f test-secret-env.yaml
k exec -it teste-secret-env sh
```


## Configmap

