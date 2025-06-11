# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "master" do |master|
  # config.vm.synced_folder "./AppHost", "/vagrant/HostApplication"
      master.vm.box = "ubuntu/jammy64"
      master.vm.network "private_network", ip: "192.168.56.108"
      master.vm.hostname = "master-node"
      master.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = "1"
        vb.name = "master"
      end
      master.vm.provision "shell", path: "docker-setup.sh"
    end
 
    config.vm.define "worker1" do |worker1|
      worker1.vm.box = "ubuntu/jammy64"
      worker1.vm.hostname = "worker1-node"
      worker1.vm.network "private_network", ip: "192.168.56.109"
      worker1.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
        vb.name = "worker1"
      end
      worker1.vm.provision "shell", path: "docker-setup.sh"
    end
 
    config.vm.define "worker2" do |worker2|
      worker2.vm.box = "ubuntu/jammy64"
      worker2.vm.hostname = "worker2-node"
      worker2.vm.network "private_network", ip: "192.168.56.110"
      worker2.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
        vb.name = "worker2"
      end
      worker2.vm.provision "shell", path: "docker-setup.sh"
    end
end
