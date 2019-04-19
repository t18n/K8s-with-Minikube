# Local K8s with Minikube and Hyperkit

This project is to quickly create a K8s cluster on local machine with Minikube.

Note: This instruction is on Mac OS

## Prerequisite
- Homebrew installed
- Hypervisor installed (Virtualbox, Hyperkit, etc.)

## Get started
1. Install `kubectl` and `Hyperkit` with `Homebrew`
   `brew install kubernetes-cli hyperkit && kubectl version`
   
2. Install [Minikube](https://github.com/kubernetes/minikube) with `Homebrew`
   `brew cask install minikube`

3. Set Minikube driver to `Hyperkit` (default is `Virtualbox`)
   `minikube config set vm-driver hyperkit`

4. Create a Minikube node
   `minikube start`

5. Clone this repo
   `git clone git@github.com:turbothinh/K8s-with-Minikube.git && cd K8s-with-Minikube`

6. Config objects to the cluster
   `kubectl apply -f client-pod.yaml && kubectl apply -f client-node-pod.yaml`

7. Check if everything is working correctly using Minikube dashboard
   `minikube dashboard`

8. Get all the running services on Minikube
   `minikube service list` and copy the __*client-node-pod*__ url on the table

9. Connect to the cluster
    Open browser and enter the copied URL. Walla!
    