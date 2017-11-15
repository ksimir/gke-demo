# gke-demo
Simple Python WebApp + Redis Demo App to understand GKE

## Build Docker image:
```
$ docker build -t asia.gcr.io/${PROJECT_ID}/web-python:v1 .
```

## Then push the new Docker image to GCR (Google Container Repository):
```
$ gcloud docker -- push asia.gcr.io/${PROJECT_ID}/web-python:v1
```

## You can verify that the image has been successfully pushed using this commmand:
```
$ gcloud container images list-tags asia.gcr.io/${PROJECT_ID}/web-python
```


## Deploy the Web app to GKE (first deployment then service)
```
$ kubectl create -f db-deployment.yml
$ kubectl create -f db-svc.yml
$ kubectl create -f web-deployment.yml
$ kubectl create -f web-svc.yml
```

## Check that the Deployments and Services are created
```
kubectl get deployments
kubectl get svc
```
