# K8S-Vagrant-Ansible
Create a K8S virtual environment with Vagrant and Ansible

## Requirements
  - Vagrant (https://www.vagrantup.com/downloads.html)
  - VirtualBox (https://www.virtualbox.org/wiki/Downloads)
  
## Instructions
  - Clone the git repo
  - To start the environment - while in the local repo directory run: vagrant up
  - To connect the the K8S master node - while in the local repo directory run: vagrant ssh master
  - To destroy the environment - while in the local repo directory run: vagrant destroy
  
## Advanced Settings - Changing the K8S environment - servers.yml 
  You can change the resulting k8s environment by updating the servers.yml file
  ### Avilable parameters:
  - host_name - change the name of a spesific host 
  - ip_address - change the ip address of a spesific host
  - cpus - change the number of CPU cores allocated to a spesific host
  - ram - change the amount of allocated RAM to a spesific host
