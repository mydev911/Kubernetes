##### lecture 24
```
watch kubectl get all -o wide
```
### create web-server.yml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-server
  labels:
    app: web-server
spec:
  replicas: 1
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

### Create db-server.yml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: db-server
  labels:
    app: db-server
spec:
  replicas: 1
  strategy:
    type: Recreate
  selector:
    matchLabels:
      app: db-service
  template:
    metadata:
      labels:
        app: db-service
    spec:
      containers:
      - name: nginx
        image: nginx:1.15.1
        ports:
        - containerPort: 80
```
- Go inside web-server.yml
```
kubectl exec -it Devloyment_Name /bin/bash
```
- install curl
```
apt-get update
```
```
apt-get install curl
```
```
curl db-server_IP
```




