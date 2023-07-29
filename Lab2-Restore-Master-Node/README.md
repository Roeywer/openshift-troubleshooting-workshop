# OpenShift Master Restore Workshop

Welcome to the OpenShift Master Restore Workshop! In this workshop, you will learn how to restore the control plane components of an OpenShift cluster in case of a disaster scenario. This workshop assumes that you have an admin access to OpenShift cluster.

### Prerequisites
1. You have admin access to an OpenShift cluster
   
2. Confirm the cluster's health by logging in to the bastion server and running the following command to check the status of cluster operators:

```bash
oc get co
```

3. Use the installation kubeconfig file by running the following command:
```bash
export KUBECONFIG=/root/ocp-install/install/auth/kubeconfig
```

### Restore Process

During the workshop, you will simulate a failure of a master node. and resolve that by following the [Recovering an Openshift IPI master node](https://cloud.redhat.com/blog/ocp-disaster-recovery-part-2-recovering-an-openshift-4-ipi-cluster-with-the-loss-of-one-master-node)

