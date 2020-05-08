# k8s-hello

## kubectl

### Basic commands

#### Help

```bash
kubectl -h
```

#### Cluster info

```bash
kubectl cluster-info
```

#### Node

```bash
kubectl get node
```

---

### Pod

#### Run pod

```bash
kubectl run hello-world --image=hello-world -it --restart=Never
or
kubectl run hello-world --image=hello-world -it --restart=Never --rm
```

#### Get pod

```bash
kubectl get pod
```

#### Describe details

```bash
kubectl describe pod hello-world
```

#### Delete pod

```bash
kubectl delete pod hello-world
```

---

### Deployment (controller)

#### Create deployment

```bash
kubectl run hello-world --image=hello-world
or
kubectl run --generator=run-pod/v1 hello-world --image=hello-world
or
kubectl create deployment hello-world --image=hello-world
```

#### Confirm all states

```bash
kubectl get all
```

#### Confirm logs

```bash
kubectl logs pod/hello-world-xxxxxxxxx
```

#### Confirm po and deployment

```bash
kubectl get deploy,po
or
kubectl get deployment,pod
```

#### Delete deployment

```bash
kubectl delete deployment hello-world
```

#### Test replica

```bash
kubectl create deployment webserver --image=nginx;
kubectl scale --replicas=5 deployment/webserver
```

##### Test deleting pod and see how it recovers

```bash
kubectl delete po webserver-7ddc8f5c98-2494d webserver-7ddc8f5c98-hw8dh;
kubectl get deploy,po
```

---

### Job

#### Create 

```bash
kubectl run hello-world --image=hello-world --restart=OnFailure
or
kubectl create job hello-world --image=hello-world
```

#### Confirm state

```bash
kubectl get jobs;
kubectl logs hello-world-xxxxx
```

#### Delete

```bash
kubectl delete job hello-world
```

#### Test failed job

```bash
kubectl create job job-1 --image=ubuntu -- "/bin/bash" -c "exit 0";
kubectl get jobs;
kubectl create job job-2 --image=ubuntu -- "/bin/bash" -c "exit 1";
kubectl get jobs;
kubectl get po;
```
