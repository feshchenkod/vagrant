# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure("2") do |config|
	config.vm.define "kali" do |kali|
	kali.vm.box = "kalilinux/rolling"
	kali.vm.hostname = 'kali'
	kali.vm.network :private_network, ip: "192.168.56.101"
	kali.vm.provider :virtualbox do |vb|
		vb.customize ["modifyvm", :id, "--memory", 2048]
		vb.customize ["modifyvm", :id, "--name", "kali"]
		end
#	kali.vm.provision "shell", inline: <<-SHELL
#		mkdir -p ~root/.ssh
#		cp ~vagrant/.ssh/auth* ~root/.ssh
#		sh /vagrant/script.sh
#	SHELL
	end

	config.vm.define "cent" do |cent|
	cent.vm.box = "centos/7"
	cent.vm.hostname = 'cent'
	cent.vm.network :private_network, ip: "192.168.56.102"
	cent.vm.provider :virtualbox do |vb|
		vb.customize ["modifyvm", :id, "--memory", 1024]
		vb.customize ["modifyvm", :id, "--name", "cent"]
		end
#	cent.vm.provision "shell", inline: <<-SHELL
#		mkdir -p ~root/.ssh
#		cp ~vagrant/.ssh/auth* ~root/.ssh
#		sh /vagrant/script.sh
#	SHELL
	end
end
