# K8S-Vagrant-Ansible
Create a K8S virtual environment with Vagrant and Ansible

## Requirements
  - Vagrant (https://www.vagrantup.com/downloads.html)
  - VirtualBox (https://www.virtualbox.org/wiki/Downloads)
  
## Instructions
  1. Clone the git repo
  2. While in the local repo directory run: vagrant up 
  3. Connect the the K8S master node with: vagrant ssh master
  
### Changing the K8S environment - servers.yml 
  You can change the resulting k8s environment by updating the servers.yml file
  #### Avilable parameters:
  host_name - change the name of a spesific host 
  ip_address - change the ip address of a spesific host
  cpus - change the number of CPU cores allocated to a spesific host
  ram - change the amount of allocated RAM to a spesific host
