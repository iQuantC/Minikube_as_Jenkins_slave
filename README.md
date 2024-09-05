# How to Use Minikube Kubernetes Cluster as Jenkins Slave

## 1. Start a Minikube Cluster Using Docker Driver
  ```
  minikube start
  ```

## 2. Run Jenkins Container on minikube network
  ```
  docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_vol:/var/jenkins_home --network minikube jenkins/jenkins:lts 
  ```

## 3. If you are using a cloud instance, allow inbound traffic from port 8080. Public_IP:8080 on browser to open Jenkins UI.

## 4. Modify the kube config file with the contents for ca.crt, client.crt, and client.key. Don't forget to "-data" to certificate-authority, client-certificate, and client-key.

##5. Build a simple job in Jenkins.
