# Application Deployment Troubleshoot Lab
Welcome to the Application Deployment Troubleshoot Lab! In this lab, you will gain hands-on experience with troubleshooting common issues that can occur during the deployment of applications in a Kubernetes cluster. Through a series of challenges, you'll have the opportunity to enhance your skills in diagnosing and resolving various deployment-related problems.

### Lab Description
In this lab, you will work with a sample application deployment running in a Kubernetes cluster. The application is designed to provide a simple HTTP server that returns a congratulatory message when accessed. Your task is to ensure that the application deploys and runs successfully without any issues.

### How to Get Started
1. Accessing the Lab Environment:

* Use your student<x> user/password to SSH to the bastion node:
```bash
$ ssh student<x>@172.28.22.125
```

* Get admin access to the cluster by running:
```bash
$ export KUBECONFIG=~/ocp-install/auth/kubeconfig
```
* If necessery use the ssh-key file to ssh to the OCP cluster nodes:
```bash
$ ssh -i ~/ocp-install/ssh-key core@<Node-IP>
```

2. Clone this repository to your local machine. It contains the necessary YAML files for the lab exercises.

3. Lab Challenges:

* Create a new OpenShift project.
* Deploy the `http-server-deployment`, `http-server-service`, and `curl-client` yamls. 
* Troubleshoot and resolve issues preventing the application from running correctly.

4. Validating Completion:

After resolving the issues, verify that the HTTP server is up and running.
Use the curl-client pod to send a curl command to the HTTP server and ensure it returns the congratulatory message.