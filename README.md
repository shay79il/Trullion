# Trullion Assignment


## Prerequisites

Ensure you have the following installed on your machine:

•   [Git](https://git-scm.com/downloads)

•   [Docker](https://docs.docker.com/get-started/)

•   [Minikube](https://minikube.sigs.k8s.io/docs/start/)

•	[Kubectl](https://kubernetes.io/docs/tasks/tools/)

•	[Helm](https://helm.sh/docs/intro/install/)


## How To Run

1. Clone the repository


2. Start minikube
```bash
minikube start --driver=docker
```

3. Enable Ingress Addon
```bash
minikube addons enable ingress
```

4. Run minikube tunnel
```bash
minikube tunnel --cleanup
```

5. Install Helm Chart
```bash
helm upgrade --install helloworld .
```

6. Add DNS record to /etc/hosts
```bash
sudo tee -a /etc/hosts > /dev/null <<< "127.0.0.1  app1.local"
sudo tee -a /etc/hosts > /dev/null <<< "127.0.0.1  app2.local"
```

7. Access the Application
   - Wait for a couple of minutes 
   - Open your browser and navigate to [app1.local](http://app1.local/create)
   - Open your browser and navigate to [app2.local](http://app2.local/create)

## Cleanup

To stop the application and clean up resources:
```bash
helm uninstall helloworld
minikube delete
```