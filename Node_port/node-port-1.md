## Node_Port

```
kubectl get node -o wide
```
```
kubectl get all -o wide
```
- create web.yml ( deployment )
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-server
  labels:
    app: web-server
spec:
  replicas: 2
  strategy:
    type: Recreate
  selector:
    matchLabels:
      app: web-service
  template:
    metadata:
      labels:
        app: web-service
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```
- create server of deployment we create (ClusterIP )
```
kubectl expose deployment Deployment_Name --type=ClusterIP
```
```
kubectl get all -o wide
```
- now we expose Node_port.. (we need to delete server we create )
```
kubectl delete service SERVICE_NAME
```
- Create NotePort
```
kubectl expose deployment Deployment_Name --type=NodePort
```





