# OpenShift Advanced Troubleshooting Workshop

Welcome to the OpenShift Advanced Troubleshooting Workshop! This repository contains hands-on labs designed to help you diagnose and resolve common issues encountered when deploying and securing applications on OpenShift.

## Lab Structure

- **Lab1-Deployments**: Practice troubleshooting application deployments, resolving issues, and validating successful application rollout.
- **Lab2-Securing-Service-Traffic**: Learn how to secure service traffic using OpenShift service certificates, mount secrets/configmaps, and validate secure connectivity.

Each lab contains a `README.md` with step-by-step instructions and YAML manifests for the exercises.

## Getting Started

1. **Clone this repository:**
   ```bash
   git clone <this-repo-url>
   cd Openshift-Advance-Troubleshooting
   ```
2. **Follow the instructions in each lab's README.md**
   - Start with `Lab1-Deployments/README.md`
   - Proceed to `Lab2-Securing-Service-Traffic/README.md`

## Prerequisites

- Access to an OpenShift cluster
- `oc` CLI installed and logged in
- Basic knowledge of Kubernetes and OpenShift concepts

## Example: Creating a New Project

To create a new project using your OpenShift username:
```bash
oc new-project http-server-dev-$(oc whoami)
```

## License

This workshop is for educational purposes.
