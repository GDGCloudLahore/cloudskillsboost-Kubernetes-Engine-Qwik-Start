![image](https://user-images.githubusercontent.com/71556060/210015967-60c7a17f-4f4d-4417-8d69-d9748c18e907.png)

**What you will learn?**
you will learn how to deploy a containerized application with GKE in less than 30 minutes. Follow the steps below to set up your lab environment.

### Creating a Kubernetes Engine cluster
---------------------TASK = 1---------------------------
```
gcloud config set compute/region us-east4
gcloud config set compute/zone us-east4-b
gcloud container clusters create --machine-type=e2-medium --zone=us-east4-b lab-cluster 
```
0 / 25

### Create a new Deployment - hello-server
---------------------TASK = 1---------------------------
```
gcloud container clusters get-credentials lab-cluster 
```
---------------------TASK = 1---------------------------
```
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0
```
0 / 25

### Create a Kubernetes Service
---------------------TASK = 1---------------------------
```
kubectl expose deployment hello-server --type=LoadBalancer --port 8080
kubectl get service
http://35.245.46.200:8080
```
0 / 25

Clean up: Delete the cluster
---------------------TASK = 1---------------------------
```
gcloud container clusters delete lab-cluster 
```
0 / 25


**Congratulations!**
You have just deployed a containerized application to Kubernetes Engine!
