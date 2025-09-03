# Application Deployment Troubleshooting Lab

Welcome to the **Application Deployment Troubleshooting Lab**! In this lab, you'll gain hands-on experience diagnosing and resolving common issues that can occur during application deployments in an OpenShift (OCP) cluster. Through a series of practical challenges, you'll enhance your troubleshooting skills and deepen your understanding of OCP deployments.

## Lab Overview

You will work with a sample application designed to run in an OpenShift cluster. The application consists of a simple HTTP server that returns a congratulatory message when accessed. Your goal is to ensure the application deploys and runs successfully.

---

## Getting Started

1. **Clone the Repository**

   Clone this repository to your local machine. It contains all the necessary YAML files for the lab exercises.

   ```sh
   git clone <repository-url>
   cd Openshift-Advance-Troubleshooting
   ```

2. **Lab Challenges**

   - **Create a New OpenShift Project**
     
     ```sh
     oc new-project http-server-test-$(oc whoami)
     ```
   - **Deploy the Application**
     
     Apply the following YAML files:
     - `http-server-test.yaml`
     - `curl-client-deployment.yaml`

     ```sh
     oc apply -f http-server-test.yaml
     oc apply -f curl-client-deployment.yaml
     ```
   - **Troubleshoot**
     
     Investigate and resolve any issues preventing the application from running correctly.

3. **Validation**

   After resolving the issues, verify that the HTTP server is up and running:
   - Use the `curl-client` pod to send a curl request to the HTTP server.
   - Ensure it returns the message:
     
     ```text
     Congratulations!! The deployment is working!
     ```

4. **Production Deployment**

   - **Create a Production Project**
     
     ```sh
     oc new-project http-server-prod-$(oc whoami)
     ```
   - **Deploy to Production**
     
     Apply the production YAML file:
     - `http-server-prod.yaml`

     ```sh
     oc apply -f http-server-prod.yaml
     ```
   - **Test Connectivity**
     
     Use the `curl-client` from the previous task to connect to the production HTTP server and verify the response.

     
   - Ensure it returns the message:
     
     ```text
     Congratulations!! The deployment is working!
     ```

---

## Tips
- Review the provided YAML files for misconfigurations or missing resources.
- Use `oc get pods`, `oc logs`, and `oc describe` to help diagnose issues.
- Refer to the OpenShift documentation if you get stuck.

---

Happy troubleshooting!

