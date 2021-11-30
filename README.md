# Open-Insights

**Jenkins installation:**

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



