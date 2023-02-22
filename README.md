# Hello World Minikube Application

This readme file provides instructions on how to build a Docker image and deploy the corresponding application and load balancer to Minikube. The following sections explain how to verify the deployment status of pods and services, run Minikube tunnel, browse the deployed application, and clean up after the deployment.

## 1. Build Docker Image

To build the Docker image, run the following command

```docker build -f Dockerfile -t hello-world-image .```

## 2. Deploy Application and Load Balancer to Minikube.

To deploy the application and load balancer to Minikube, apply the deployment YAML file:

```kubectl apply -f deployment.yaml```

## 3. Verify Deployment Status of Pods and Services

To verify the deployment status of the two pods and one service, run the following command:

```kubectl get deployment hello-world && kubectl get svc hello-world-service```

## 4. Run minikube tunnel

To run Minikube tunnel, simply run the following command:

```minikube tunnel```

## 5. Browse Deployed Application

Once the deployment is complete and the tunnel is running, you can browse the deployed application at http://127.0.0.1:8080

## 6. Clean up

To clean up, delete the deployment and service by running the following command:

```kubectl delete deployment hello-world && kubectl delete svc hello-world-service```