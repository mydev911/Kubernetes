## Service of db-server
- on command line 
```
kubectl expose deployment db-server --type=ClusterIP --port 80 --target-port=80
```
- server port need opent (ex 80 here ) Cluster ip will be create

```
kubectl describe service db-server
```
- check endpoint 
- delete db-server and check endpoint

- check
```
curl Cluster_IP
```
- Now we create service for web-server to hit from out-side
## web-server service
#### on command line
```
kubectl expose deployment web-server --type=ClusterIP --port 80 
```
#### on yml file
- create service.yml
```
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: web-server
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```
```
kubectl apply -f service.yml
```
```
kubectl describe service
```


