# k8s-deployment-restart-cron

# Kubernetes CronJob for Restarting Deployment

This project provides a setup for a Kubernetes CronJob to restart a deployment in a specified namespace using a service account with appropriate permissions.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Step 1: Apply the Role](#step-1-create-a-role) -> `kubectl apply -f Role.yaml`
  - [Step 2: Apply the RoleBinding](#step-2-create-a-rolebinding) -> `kubectl apply -f RoleBind.yaml`
  - [Step 3: Apply the CronJob](#step-3-create-the-cronjob)-> `kubectl apply -f CronJob.yaml`
  - [Step 4: Apply the ServiceAccount](#step-3-create-the-serviceAccount)-> `kubectl apply -f ServiceAccount.yaml`
- [Verify Permissions](#verify-permissions)
- [License](#license)

## Prerequisites

- Kubernetes cluster
- kubectl configured to interact with your cluster
- Permissions to create roles, role bindings, and cron jobs in the cluster

# Verify permissions
`kubectl auth can-i get deployments --as=system:serviceaccount:namespace_of_service_account:service-deployment-restart -n deployment_namespace`

`kubectl auth can-i update deployments --as=system:serviceaccount:namespace_of_service_account:service-deployment-restart -n deployment_namespace`
