# Open-Insights

**1. **Jenkins installation:****

Step 1 — Installing Jenkins on Kubernetes
Create Namespace for Devops tools

kubectl create namespace jenkins

cd Open-Insights/jenkins/

kubectl create -f jenkins.yaml --namespace jenkins
kubectl get pods -n jenkins


cd Open-Insights/jenkins/jenkins-service.yaml
Now create the Service in the same namespace
kubectl create -f jenkins-service.yaml --namespace jenkins
kubectl get services --namespace jenkins


Step 2 — Accessing the Jenkins UI
In this step, you will access and explore the Jenkins UI. Your NodePort service is accessible on port 30000 across the cluster nodes. You need to retrieve a node IP to access the Jenkins UI.

for AWS use the public IP and open the 30000 port in security group

http://<public-ip>:30000

kubectl get pods -n jenkins


kubectl logs jenkins-id -n jenkins
you will get jenkins password

*************************************************************
  
Jenkins initial setup is required. An admin user has been created and a password generated.
Please use the following password to proceed to installation:

jenkins--password

This may also be found at: /var/jenkins_home/secrets/initialAdminPassword

*************************************************************


**2. **Nexus OSS 3 Installation****
  
  Setup Nexus OSS On Kubernetes
  
 Goto the Nexus directory for the nexus deployment.
  
  cd Open-Insights/nexus3/
  
  kubectl create -f .
  
  the nexus deploymen and service will be deployed on the jenkins namespace
  
  open nexus url with the AWS public ip eposed on port 32000. open the port 32000 in AWS securrity group
  
  http://54.173.129.176:32000/
  
  *************************************************************
  
  3**. SonarQube Deployment on K8s**
  
  goto to SonarQube directory for deployment yamls.
  
  cd Open-Insights/sonarqube/

  deploy the PVC for postgres , postgres pod for sonarqube data storage.
  deploy sonarQube and expose the sonar qube using the service and ingress
  
  kubectl create -f .
  
  
  
  
  
  
  
