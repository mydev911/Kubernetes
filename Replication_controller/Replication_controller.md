- Create a file
```
vim rc.yml
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
kubectl apply -f rc.yml
```
- To see level
```
kubectl get pod,rc --show-labels
```
- see detales
```
kubectl describe rc POD_NAME
```
- To delate
```
kubectl delete -f rc.yml
```
