# -*- mode: ruby -*-
# # vi: set ft=ruby :
# Configure K8S Environment

# Specify minimum Vagrant version and Vagrant API version
Vagrant.require_version ">= 1.9.7"
VAGRANTFILE_API_VERSION = "2"

# Require YAML module
require 'yaml'

# Read YAML file with box details
servers = YAML.load_file('servers.yml')

Vagrant.configure(VAGRANTFILE_API_VERSION) do | config |
 config.vm.box = "ubuntu/xenial64"
 config.vm.box_version = "20181212.0.0"

 servers.each do | servers |
   config.vm.define servers["hostname"] do | srv |
     srv.vm.hostname = servers["hostname"]
     srv.vm.box = servers["box"]
     srv.vm.network "private_network", ip: servers["ip_address"]
     srv.vm.provider "virtualbox" do | vb |
       vb.memory = servers["ram"]
       vb.cpus = servers["cpus"]
     end
     srv.vm.provision "ansible_local" do |ansible|
       ansible.playbook = "install-docker.yml"
     end
     srv.vm.provision "ansible_local" do |ansible|
       ansible.playbook = "k8s-common.yml"
     end
     srv.vm.provision "ansible_local" do |ansible|
       ansible.playbook = servers["playbook"]
     end
   end
 end
end
