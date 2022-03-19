# Setup plain kubernetes

You can use this ansible script to setup vanilla kubernetes (using kubeadm) on any public clouds. This script has been primarily tested in a private cloud though. It sets up 1 master node and 3 worker nodes.

## 1. Pre-requisites

1. 4 machines are available for kubernetes setup
2. ansible is setup on ansible-controller VM (different from the above 4 machines)
3. ssh keys are copied to the 4 machines so that they are accessible by ansible without password

## 2. Install Kubernetes using kubeadm

Change the IP addresses of the 4 machines in the 'hosts' file and then run the following:

```
ansible-playbook -i hosts install-k8s.yaml
```

Kubernetes would be ready in about 30 minutes. You can ssh into the master node and check if everything is working fine:

```
kubectl get nodes
```
