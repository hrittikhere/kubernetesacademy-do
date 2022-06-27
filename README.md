# Docker Containers and Kubernetes on DigitalOcean

Link: https://kubernetesacademy.online/courses/digitalocean/

## Microservices Concepts


## Deployment Manifest: Nginx 


```bash

cat <<EOF > nginx-deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 2
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80
EOF
```