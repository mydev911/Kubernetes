```
apiVersion: apps/v1

kind: Deployment

metadata:

  name: my-webserver

spec:

  selector:

    matchLabels:

      run: my-webserver

  replicas: 1

  template:

    metadata:

      labels:

        run: my-webserver

    spec:

      containers:

      - name: my-webserver

        image: nginx

        ports:

        - containerPort: 80
```
