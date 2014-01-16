# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "master" do |master|
    master.vm.box = "base"
    master.vm.network "private_network", ip: "192.168.10.2",
	virtualbox__intnet: "mynetwork"

    config.vm.provision "shell",
   	 inline: "echo master | tee /etc/hostname ; mkdir -p /home/vagrant/.ssh/ ; cp /vagrant/id_rsa* /home/vagrant/.ssh/"
  end

  config.vm.define "client1" do |client1|
    client1.vm.box = "base"
    client1.vm.network "private_network", ip: "192.168.10.11",
	virtualbox__intnet: "mynetwork"

    config.vm.provision "shell",
	 inline: "echo client1 | tee /etc/hostname ; cat /vagrant/id_rsa.pub | tee -a /home/vagrant/.ssh/authorized_keys"
  end
  config.vm.define "client2" do |client2|
    client2.vm.box = "base"
    client2.vm.network "private_network", ip: "192.168.10.12",
	virtualbox__intnet: "mynetwork"

    config.vm.provision "shell",
   	 inline: "echo client2 | tee /etc/hostname ; cat /vagrant/id_rsa.pub | tee -a  /home/vagrant/.ssh/authorized_keys"
  end

  config.vm.define "client3" do |client3|
    client3.vm.box = "base"
    client3.vm.network "private_network", ip: "192.168.10.13",
	virtualbox__intnet: "mynetwork"

    config.vm.provision "shell",
   	 inline: "echo client3 | tee /etc/hostname ; cat /vagrant/id_rsa.pub | tee -a /home/vagrant/.ssh/authorized_keys"
  end
end
