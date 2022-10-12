```
- name: deploy a web server

      k8s:

        api_version: v1

        namespace: my-namespace

        definition:

          kind: Deployment

          metadata:

            labels:

              app: nginx

            name: nginx-deploy

          spec:

            replicas: 1

            selector:

              matchLabels:

                app: nginx

            template:

              metadata:

                labels:

                  app: nginx

              spec:

                containers:

                  - name: my-webserver

                    image: quay.io/jitesoft/nginx

                    ports:

                      - containerPort: 80

                        protocol: TCP
 ```
