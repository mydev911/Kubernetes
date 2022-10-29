### Kubernetes Deployment Strategies types
- rolling deployment ( by defult)  Maxsurge / max-unavailable
- recreate
#### Canary Deployment / blue & green Deployment / Red & black Deployment

## rolling deployment
```
apiVersion: apps/v1
kind: Deployment
metadata:
 name: nginx-deployment
 labels:
    app: ngnix
spec:
  selector:
     matchLabels:
      app: nginx
  replicas: 1
  template:
    metadata:
      labels:
        app: nginx

    spec:
      containers:
      - name: nginx
          image: nginx:1.14.2
          ports:
          - containerPort: 80
```
```
kubectl apply -f rc.yml
```
```
kubectl delete -f rc.yml
```
```
kubectl get pod,rc --show-labels
```
