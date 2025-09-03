# OpenShift Service Serving Certificate Workshop

This workshop guides you through enabling secure HTTPS communication between pods in OpenShift using Service Serving Certificates. You will annotate a service, mount certificates, and validate secure connectivity with a curl client.

## Prerequisites
- OpenShift CLI (`oc`) installed and configured
- Access to an OpenShift cluster

---

## Workshop Overview
You will:
1. Create a new OpenShift project
2. Deploy a simple HTTP/HTTPS server
3. Deploy a curl client pod for testing
4. Annotate the service to generate a Service Serving Certificate
5. Mount certificates and validate secure HTTPS communication

---

## Step 1: Create a New Project
```bash
oc new-project https-server-project-$(oc whoami)
```

---

## Step 2: Deploy the HTTP/HTTPS Server
Apply the server deployment and service manifests:
```bash
oc apply -f http-server.yaml
oc apply -f http-server-service.yaml
```

---

## Step 3: Deploy the Curl Client
Deploy the curl client pod:
```bash
oc apply -f curl-client.yaml
```
Test connectivity (replace `<service-name>` and `<port>` as needed):
```bash
oc exec -it <curl-pod> -- curl -v https://<service-name>:<port>
```
- Did the HTTPS connection succeed?

---

## Step 4: Annotate the Service for Certificate Generation
Annotate the service to request a signed certificate:
```bash
oc annotate service <service-name> service.beta.openshift.io/serving-cert-secret-name=https-server-certs
```
Reference: [OpenShift Docs: Add Service Certificate](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/security_and_compliance/configuring-certificates#add-service-certificate_service-serving-certificate)

Verify the secret was created:
```bash
oc get secret https-server-certs
```

---

## Step 5: Mount Certificates and Enable HTTPS

### Server
- Mount `tls.crt` to `/app/fullchain.pem`
- Mount `tls.key` to `/app/privkey.pem`

Update your deployment YAML accordingly.

### Curl Client
- Mount the service CA certificate configmap
- Use curl with the `--cacert` flag:
```bash
curl --cacert /certs/service-ca.crt https://<service-name>:<port>
```

---

## Completion
If the curl command returns a valid response over HTTPS, you have successfully enabled secure service-to-service communication in OpenShift!

---

## Troubleshooting Tips
- Check pod logs for errors
- Ensure secrets and configmaps are mounted correctly
- Validate service endpoints and ports

---

Happy troubleshooting!
