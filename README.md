###  Kubernetes Cluster Setup and App Deployment with Minikube

## Tools Used
- **Minikube**: to create a local Kubernetes cluster
- **kubectl**: command-line tool to interact with Kubernetes
- **Docker**: to manage container images

## Step-by-Step Procedure

### 1. Install Minikube and Start Cluster
- Installed Minikube on local machine.
- Started the cluster using:
  ```
  minikube start --driver=docker
  ```
- Verified the cluster is running by checking the node status.

### 2. Create Deployment YAML
- Created a `deployment.yaml` file describing the app’s deployment.
- Used the official `nginx:latest` image in a simple 2-replica deployment.
- Applied the deployment to the cluster:
  ```
  kubectl apply -f deployment.yaml
  ```

### 3. Expose Application Using Service YAML
- Created a `service.yaml` file to expose the app using a NodePort service.
- Applied the service with:
  ```
  kubectl apply -f service.yaml
  ```

### 4. Verify Pods and Services
- Checked running pods to ensure they are up and ready:
  ```
  kubectl get pods
  ```
- Verified service and noted the NodePort:
  ```
  kubectl get services
  ```

### 5. Scale the Deployment
- Scaled the deployment to increase pods:
  ```
  kubectl scale deployment deployment.yaml --replicas=3
  ```
- Verified the new pods are running successfully.

### 6. View Logs and Details
- Used:
  ```
  kubectl describe pod nginx-deployment-bf744486c-fw82
  ```
  to view detailed info and events.
- Checked container logs:
  ```
  kubectl logs nginx-deployment-bf744486c-fw82
  ```

## Deliverables
- `deployment.yaml` and `service.yaml` files used for app deployment.
- Outputs:
  - Pod status using `kubectl get pods`

s<img width="1067" height="179" alt="Screenshot 2025-09-29 200349" src="https://github.com/user-attachments/assets/81e3bc3e-45cc-446e-9abe-d88dee2afece" />

  - Service status using `kubectl get services`


<img width="1023" height="160" alt="Screenshot 2025-09-29 200359" src="https://github.com/user-attachments/assets/ee7a1f68-a718-45d8-b5ae-4ddd7f27d1f2" />

  - Scaling results after running `kubectl scale`


<img width="964" height="117" alt="Screenshot 2025-09-29 200511" src="https://github.com/user-attachments/assets/bb8ff2a4-c3ed-4a07-a2b9-7cca6c985efc" />

## Conclusion
This project helped understand how to:
- Set up a local Kubernetes cluster with Minikube.
- Create and deploy apps using deployment manifests.
- Expose apps using Kubernetes services.
- Scale applications dynamically.
- Troubleshoot using pod descriptions and logs.

