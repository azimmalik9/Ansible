# -*- mode: ruby -*-
# vi: set ft=ruby :
#11-12

Vagrant.configure(2) do |config|
	 config.vm.box = "chad-thompson/ubuntu-trusty64-gui"
	 config.vm.synced_folder "shared", "/tmp/shared"
	 
	 config.vm.provider "virtualbox" do |vb|
	 vb.memory = 4096
	 vb.cpus=2
	 end
	 
	 config.vm.define "ansiMasterAM" do |masterAM|
		masterAM.vm.hostname = "masterAM.qac.local"
		masterAM.vm.network :public_network, ip: "192.168.1.58"
		masterAM.vm.provision "shell", path: "masterBootstrap.sh"
		
	end 
	
	config.vm.define "ansiAgentAM" do |agentAM|
		agentAM.vm.hostname = "agentAM.qac.local"
		agentAM.vm.network :public_network, ip: "192.168.1.59"
		agentAM.vm.provision :shell, path: "agentBootstrap.sh"
		
	end 
end