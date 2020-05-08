# Pod

## Hello pod

### Apply manifest

```bash
kubectl apply -f nginx-pod.yml
```

### Delete manifest

```bash
kubectl delete -f nginx-pod.yml
```

### Get wider info

```bash
kubectl get po nginx -o wide
```

### Test nginx

```bash
curl -m 3 http://10.1.0.39/
```

Note that this fails as service is not configured.

### Create interactive pod and test connection

```bash
kubectl run busybox --image=busybox --restart=Never --rm -it sh;
wget -q -O - http://10.1.0.39/
```

---

## hc-probe

### Build apl image

```bash
docker build -t maho/webapl:0.1 .
```

### Apply manifest and check status

```bash
kubectl apply -f webapl-pod.yml
kubectl get po
kubectl logs webapl
kubectl describe po webapl
```

---

## init-sample

### Apply manifest and check

```bash
kubectl apply -f init-sample.yml
kubectl get po
kubectl exec -it init-sample -c main sh
kubectl delete -f init-sample.yml
```

Note that option c is specifying the container name.

---

## side-car

### Build image

```bash
docker build -t maho/c-cloner:0.1 .
```

### Apply manifest and check pod

```bash
kubectl apply -f webserver.yml
kubectl get po
kubectl get po -o wide
```

### Check inside

```bash
kubectl run busybox --image=busybox --restart=Never --rm -it sh
wget -q -O - http://10.1.0.46
```

### Delete manifest

```bash
kubectl delete -f webserver.yml
```
