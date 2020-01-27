# -*- mode: ruby -*-
# vi: set ft=ruby :

#Virtual machine 1

Vagrant.configure("2") do |config|
 config.vm.define "ubuntu vm" do |vm1|
 vm1.vm.hostname = "ubuntu-vm"
 vm1.vm.box = "ubuntu/bionic64"
 vm1.vm.network "private_network", ip: "192.168.33.10"
 vm1.vm.network "forwarded_port", guest: 80, host: 8080

  vm1.vm.provider "virtualbox" do |vb|
  vb.name = "ubuntu vm"
  vb.gui = false
  vb.memory = "1024"

   end



#install Apache server 
    vm1.vm.provision "shell", run: "always", inline: <<-SHELL
   echo "Hello from Ubuntu VM"
    apt-get update
    apt-get install apache2 -y
   SHELL

end


#virtual machine 2

config.vm.define "centos vm" do |vm2|
 vm2.vm.hostname = "centos-vm"
 vm2.vm.box = "centos/7"
 vm2.vm.network "private_network", ip: "192.168.33.20"

  vm2.vm.provider "virtualbox" do |vb|
  vb.name = "centos vm"
  vb.gui = false
  vb.memory = "1024"
   end
 
    vm2.vm.provision "shell", run: "always", inline: <<-SHELL
   echo "Hello from CentOS VM"
   SHELL
 end

end
