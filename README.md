# K3s Kubernetes Cluster using Vagrant & Ansible

## Prerequisites
- Install [Vagrant](https://www.vagrantup.com/downloads)
- Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Install [kubectl](https://kubernetes.io/docs/tasks/tools/)
- Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Setup and Run
1. **Start the Virtual Machines**
   ```sh
   vagrant up
   ```
2. **Verify Cluster Nodes**
   ```sh
   vagrant ssh master
   kubectl get nodes
   ```
3. **Run Ansible Playbook to Automate K3s Setup**
   ```sh
   ansible-playbook -i ansible/inventory.ini ansible/setup-k3s.yml
   ```
4. **Deploy Sample Application**
   ```sh
   kubectl apply -f manifests/app-deployment.yml
   ```
5. **Set Up Ingress Controller**
   ```sh
   kubectl apply -f manifests/ingress.yml
   ```
