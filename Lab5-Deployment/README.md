# Application Deployment Troubleshoot Lab
Welcome to the Application Deployment Troubleshoot Lab! In this lab, you will gain hands-on experience with troubleshooting common issues that can occur during the deployment of applications in a Kubernetes cluster. Through a series of challenges, you'll have the opportunity to enhance your skills in diagnosing and resolving various deployment-related problems.

### Lab Description
In this lab, you will work with a sample application deployment running in a Kubernetes cluster. The application is designed to provide a simple HTTP server that returns a congratulatory message when accessed. Your task is to ensure that the application deploys and runs successfully without any issues.

### How to Get Started
Accessing the Lab Environment:

Use your student<x> user/password to SSH to the bastion node:
```bash
$ ssh student1@172.28.22.125
```

Get admin access to the cluster by running:
```bash
$ export KUBECONFIG=~/ocp-install/auth/kubeconfig
```
If necessery use the ssh-key file to ssh to the OCP cluster nodes:
```bash
$ ssh -i ~/ocp-install/ssh-key core@<Node-IP>
```

Start by cloning this repository to your local machine. It contains the necessary YAML files for the lab exercises.
Lab Challenges:

Create new openshift project and deploy the http-server-deployment, http-server-service and curl-client. Your goal is to troubleshoot and resolve issues that prevent the application from running correctly.

Once you have successfully resolved all the issues, verify that the HTTP server is up and running and answering to curl commands issued by the curl pod.