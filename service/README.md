# Service

## Cluster IP

### Create deployment and service

```bash
kubectl apply -f deploy.yml;
kubectl apply -f svc.yml;
kubectl get all;
```

### Check from interactive container

```bash
kubectl run -it busybox --restart=Never --rm --image=busybox sh
```

#### Inside container

```bash
wget -q -O - http://web-service
```

### Get env variable

```bash
env | grep WEB_SERVICE
```

### Delete deployment and service

```bash
kubectl delete -f .
```

---

## Session Affinity

TBD.

---

## Node Port

### Create deployment and service

```bash
kubectl apply -f deploy.yml;
kubectl apply -f svc-np.yml;
kubectl get svc;
```

### Confirm from host machine

```bash
curl http://localhost:portnumber/
```

### Delete deployment and service

```bash
kubectl delete -f deploy.yml;
kubectl delete -f svc-np.yml;
```

---

