# Questions

## Quick practice 12/02/2022

### Run pods and services
1 Create a single pod with nginx running with version 1.15.0. 

```
k run nginx --image=nginx:1.15.0
```

2 Change nginx image from previous pod with version 1.17.0

```
k edit pod nginx
```

3 Expose last pod as NodePort

```
k expose pod nginx --port 8080 --target-port 8081
```

### Label nodes and assing pods into each node
4 Label nodes on this with this 'description' labels with these keys: 'node-master', 'node-a' and 'node-b'

```
k label node bonde-do-cka description=master
k label node bonde-do-cka-m02 description=node-a
k label node bonde-do-cka-m03 description=node-b
```

5 Create a nginx deployment to run on 'node-a' only.
```
k create -f nginx-deployment.yaml
```

6 Create a prometheus DaemonSet to run on all pods.
```
k create -f daemonset.yaml
```

7 Create a pvc, pv and nginx with this volumes attached.

8 Create secret from file with content `name=prometheus-configmap`. Create Deployment with environment variable with content of this secret.

9 Create configmap from file with content `name=prometheus-env`. Create Deployment with environment variable with content of this secret.