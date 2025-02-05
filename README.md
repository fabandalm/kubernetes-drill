# kubernetes-drill

## k8s-data-01-setup
Run docker-compose to test node application.
```
docker-compose up -d --build
```

List docker images
```
docker images
```

Docker image name (root folder name and service name) <br>
<b>root folder name:</b> k8s-data-01-setup <br>
<b>service name:</b> stories
```
k8s-data-01-setup-stories
```

Run docker-compose down
```
docker-compose down
```

Remove all stopped containers
```
docker container prune
```

## k8s-data-02-deploy-svc

Build a docker image to push to docker hub
```
docker build -t fabandalm/k8s-data-demo:1.0 .
```

Push to docker hub
```
docker push fabandalm/k8s-data-demo:1
```

Deploy to Kubernetes Cluster

```
kubectl apply -f=service.yaml -f=deployment.yaml 
```

Manually Port Forward for LoadBalancer

```
kubectl port-forward svc/story-service 32114:80
```

To access use the following URL

```
http://localhost:32114/story
```
