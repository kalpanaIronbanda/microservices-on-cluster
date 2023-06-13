Microservices on Cluster
==========================

This repository provides a guide and code samples for deploying microservices on a cluster infrastructure using Kubernetes.

Prerequisites
-------------

Before getting started, ensure that you have the following prerequisites:

Cluster Infrastructure: You should have a Kubernetes cluster available, such as Amazon Elastic Kubernetes Service (EKS) or any other.

For EKS you can follow https://github.com/kalpanaIronbanda/eks-cluster-with-terraform.git .It creates EKS cluster with automation tool terraform.

Containerization: Containerize your microservices using Docker or a containerization tool of your choice. Each microservice should be packaged as a separate container image.Push your image to ECR 
 
launch and ec2 and setup jenkins.

Create a job with pipeline and Use below repo to build and push the frontend image to ECR

 https://github.com/kalpanaIronbanda/micro-frontend.git

Create a job with pipeline and Use below repo to build and push the backend image to ECR

 https://github.com/kalpanaIronbanda/micro-backend.git

You can follow the instructions given in those repositories to push image to ECR using jenkins

Kubernetes Tools: Install kubectl and ensure it is properly configured to access your Kubernetes cluster.

Getting Started
------------------

To deploy microservices on a cluster, follow these steps:

Clone this repository: 

		git clone https://github.com/your-username/microservices-on-cluster.git

Change into the repository directory: 

		cd microservices-on-cluster

Deployment
---------------

To deploy the microservices on your cluster, follow these general steps:

Note the ECR url of your frontend image and backend

Navigate to frontend 
		cd frontend

Place the ECR url in image 

Navigate to the backend 
		cd backend

Place the ECR url in image

Modify the code according to your requirements 

Use kubectl to apply the Kubernetes configuration files to your cluster:

Navigate to target folder

		cd backend
		kubectl apply -f .

Monitor the deployment status and check the running pods,services...etc.:

		kubectl get ns
		kubectl get po -n <namespace>
		kubectl get svc -n <namespace>
		
Navigate to target folder

		cd frontend
		kubectl apply -f .

Monitor the deployment status and check the running pods,services...etc.:

		kubectl get ns
		kubectl get po -n <namespace>
		kubectl get svc -n <namespace>

Access and test the microservices using their respective service endpoints. You may need to expose the services externally or access them internally based on your cluster setup.

Cleaning Up
--------------

To remove the microservices and associated resources from your cluster, run the following command:

		kubectl delete -f <path to object yml file> -n <namespace>
		
