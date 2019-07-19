# Postgres Deployment on Kubernetes cluster with Persistent storage 
This repository will enables to deploy Postgres on Kubernetes with Persistent storage 
Disclaimer : This templates tested on GCP cloud and AWS cloud as well
#### Step # 1 Create ConfigMaps for credentials of postgress    
    kubectl apply -f postgres-configmap.yml
    
#### Step # 2 Create Persistent Volume 
    kubectl apply -f 001-storage-class.yml

#### Step # 3 Create Persistent Volume Claim 
    kubectl apply -f 002-storage-class-pvc.yml

#### Step # 4 Create Postgres deployment 
    kubectl apply -f deployment.yml

#### Step # 5 Create Service to expose Postgres to other Pods.
    kubectl apply -f deployment.yml

#### Verify Postgres PODs
    mansoor@LARC-MANSOOR ~/Documents/prometheus/prometheus $ kubectl get pods |grep psql            
    psql-sendder-689bbfffbb-ns4gs       1/1     Running   0          27m
