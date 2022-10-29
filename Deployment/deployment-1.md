```
vim deployment.yml
```
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
- apply
```
kubectl apply -f deployment.yml
```
```
kubectl apply -f deployment.yml --record=true
```
```
kubectl rollout history
```
- first time deployment
```
kubectl describe Deployment_Name
```
- delete
```
kubectl delete -f deployment.yml
```



