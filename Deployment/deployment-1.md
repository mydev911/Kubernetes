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
- show lable
```
kubectl get pods --show-labels
```

## Roll-out /  
### Option-1
- Change ngnix version on yml file
```
kubectl apply -f deployment.yml --record=true
```
- when you have multiple update. you can check previous update history with revision
```
kubectl rollout history Deployment_name --revision=1
```
### roll-out
```
kubectl rollout undo Deployment_Name --to-revision=2
```
### Option-2
```
kubectl set image Deployment_Name nginx=nginx:1.12.1 --record=true
```
### ErrImagePull  and status -- ImagePullBackOFF
- just put worng image / worng version / Version is avelable
### Option -3

## How to pause Rollout process
```
kubectl rollout pause Deployment_name
```
```
kubectl rollout resume Deployment_Name
```

