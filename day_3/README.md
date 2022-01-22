# Day 3

## Deployment

Controle do Replicaset.

É possível fazer rollback.

Quando se cria deployment é criado um ReplicaSet.

>TODO: Estudar melhor Label e node Selector.

> Antigamente havia o RC(ReplicationController).

```
k get pods -l dc=UK    
k get pods -l dc=NL
k get pods -L dc
k get replicasets -l dc=NL
```

Label pode ser aplciado em qq componentes: pod, deployment, nó, etc.

```
k label nodes bonde-do-cka-m02 disk=SSD
k label nodes bonde-do-cka-m03 disk=HDD
k label nodes bonde-do-cka-m02  --list
k label nodes bonde-do-cka-m03 disk=SSD --overwrite
k label nodes bonde-do-cka-m02  --list
```

Remover label de todos os nós   
k label nodes dc- --all

## ReplicaSet

Controlar Pods com uma certa qunatidade.

## DeamonSet
Igual ao ReplicaSet mas sem número de réplicas. Usado quando se quer que a aplicação fique em todos os nós do cluster.
```
k rollout history ds  <NAME>
k rollout history ds <NAME> --revision <REVISION_NUMBER>
k rollout undo ds <NAME> --to-revision <REVISION_NUMBER>
```


### Canary Deployment

```
k create -f day_3/app-v1.yml
k create -f day_3/service-app.yml
k create -f day_3/app-v2-canary.yml
k apply -f day_3/app-v2.yml
k rollout history deployment giropops-v2
```

