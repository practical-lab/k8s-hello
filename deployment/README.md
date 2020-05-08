# Deployment

## Hello deployment

### Apply deployment

```bash
kubectl apply -f nginx-deployment.yml
```

### Get states

```bash
kubectl get deploy;
kubectl get rs;
kubectl get po -o wide;
```

---

## Scale

### Confirm pod and apply scaled

```bash
kubectl get po;

kubectl apply -f scale-deployment.yml;
or
kubectl scale --replicas=10 deployment.extensions/web-deploy
```

---

## Rollout

### Confirm pod and apply rollout

```bash
kubectl describe deployment web-deploy;
kubectl apply -f rollout-deployment.yml;
kubectl get po;
```

---

## Rollback

### Apply rollback

```bash
kubectl rollout undo deployment web-deploy;
kubectl get po;
```

---
