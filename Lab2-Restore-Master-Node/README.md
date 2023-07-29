# OpenShift Master Restore Workshop

Welcome to the OpenShift Master Restore Workshop! In this workshop, you will learn how to restore the control plane components of an OpenShift cluster in case of a disaster scenario. This workshop assumes that you have an admin access to OpenShift cluster.

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
* Before starting check the clusterOperator status by running:
  ```bash
  $ oc get co
  ```

### Restore Process

During the workshop, you will simulate a failure of a master node. and resolve that by following the [Recovering an Openshift IPI master node](https://cloud.redhat.com/blog/ocp-disaster-recovery-part-2-recovering-an-openshift-4-ipi-cluster-with-the-loss-of-one-master-node)

