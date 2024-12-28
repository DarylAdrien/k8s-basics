# Kubernetes Project with Pod, Deployment, and NodePort Service

This repository contains a basic Kubernetes setup including configurations for a Pod, a Deployment, and a NodePort Service. The project demonstrates fundamental Kubernetes concepts and is designed to be run locally using Minikube for testing.

---

## **Project Structure**

1. **`pod.yml`**:
   - Defines a simple Pod that runs a specified Docker image.
   - Serves as the foundation of the Kubernetes setup.

2. **`deployment.yml`**:
   - Configures a Deployment that provides features like auto-healing and scaling.
   - Ensures high availability and fault tolerance for the application.

3. **`service.yml`**:
   - Exposes the Deployment using a NodePort Service.
   - Makes the application accessible externally through a Node's IP and a specific port.

---

## **Prerequisites**

- **Minikube**: Install Minikube to set up a local Kubernetes cluster. Follow the [official guide](https://minikube.sigs.k8s.io/docs/start/) for installation.
- **Kubectl**: Install the Kubernetes command-line tool. Refer to the [kubectl installation guide](https://kubernetes.io/docs/tasks/tools/).

---

## **Setup Instructions**

1. Start Minikube:
   ```bash
   minikube start
   ```

2. Apply the Pod configuration:
   ```bash
   kubectl apply -f pod.yml
   ```

3. Apply the Deployment configuration:
   ```bash
   kubectl apply -f deployment.yml
   ```

4. Apply the Service configuration:
   ```bash
   kubectl apply -f service.yml
   ```

5. Verify the resources:
   ```bash
   kubectl get pods
   kubectl get deployments
   kubectl get services
   ```

6. Access the application:
   - Use the NodePort assigned by the Service. To find the NodePort:
     ```bash
     kubectl get svc
     ```
   - Access the application at `http://<NodeIP>:<NodePort>`. For Minikube, use:
     ```bash
     minikube service <service-name>
     ```

---

## **Features**

- **Pod**: Runs a containerized application using a Docker image.
- **Deployment**: Provides auto-healing to maintain desired Pod state.
- **Service**: Exposes the application externally using NodePort mode.

---

## **Testing and Validation**

- Ensure all resources are running:
  ```bash
  kubectl get all
  ```
- Monitor logs for troubleshooting:
  ```bash
  kubectl logs <pod-name>
  ```

---

## **License**

This project is open-source and available for educational purposes. Feel free to modify and use it for learning Kubernetes.

