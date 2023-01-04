![image](https://user-images.githubusercontent.com/71556060/210015967-60c7a17f-4f4d-4417-8d69-d9748c18e907.png)

## Manage Containerized Apps with Kubernetes Engine

### What you will learn?
you will learn how to deploy a containerized application with GKE in less than 30 minutes.  
Follow the steps below to set up your lab environment.

### Set a default compute zone
---------------------TASK = 1 ---------------------------
**Set the default compute region,**
```
gcloud config set compute/region us-east4
gcloud config set compute/zone us-east4-b
```

### Create a GKE cluster
---------------------TASK = 2 ---------------------------
**Create a cluster**
```
gcloud container clusters create --machine-type=e2-medium --zone=us-east4-b lab-cluster 
```

0 / 25

### Get authentication credentials for the cluster
---------------------TASK = 3 ---------------------------
**Authenticate with the cluster:**
```
gcloud container clusters get-credentials lab-cluster 
```

### Deploy an application to the cluster
---------------------TASK = 4 ---------------------------
```
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0
```

0 / 25

**create a Kubernetes Service,**
```
kubectl expose deployment hello-server --type=LoadBalancer --port 8080
```
**To inspect the Service,**
```
kubectl get service
```
**Note:** _It might take a minute for an external IP address to be generated. Run the previous command again if the EXTERNAL-IP column status is pending._
```
http://[EXTERNAL-IP]:8080
```

0 / 25

### Clean up: Delete the cluster
---------------------TASK = 5---------------------------
```
gcloud container clusters delete lab-cluster 
```
0 / 25


**Congratulations!**
You have just deployed a containerized application to Kubernetes Engine!
