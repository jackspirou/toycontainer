# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "ubuntu-xenial"
  config.vm.network "public_network", ip: "192.168.0.131"
  config.vm.synced_folder ".", "/home/ubuntu/toycontainer", create: true

  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu-xenial64"
    vb.gui = false
    vb.memory = "2048"
    vb.cpus = 2
  end

  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y whois git htop golang-go
     sudo useradd -m -p `mkpasswd password_here` -s /bin/bash user_here
     sudo usermod -a -G sudo user_here
  SHELL

end
