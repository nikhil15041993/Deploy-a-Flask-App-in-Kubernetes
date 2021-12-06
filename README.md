# Deploy-a-Flask-App-in-Kubernetes
# Start minikube

If you installed Minikube locally, run the following command:

$minikube start

# Create a Dockerfile

```
FROM python:3.7
RUN mkdir /app
WORKDIR /app/
ADD . /app/
RUN pip install -r requirements.txt
CMD ["python", "/app/app.py"]

```

## build the docker image

```
docker build -t <image name> .
```

now that the docker image has been created we can move on to create Kubernetes files

## Create K8s Deployment file

To create a deployment use the command
```
kubectl apply -f deployment.yaml
```

to view this open minikube dashboard
```
minikube dashboard
```

 run our application by using following command 
```
minikube service <service name>
```
