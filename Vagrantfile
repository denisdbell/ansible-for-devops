	# -*- mode: ruby -*-
	# vi: set ft=ruby :
	VAGRANTFILE_API_VERSION = "2"

	

	Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
		config.ssh.insert_key = false
	    config.vm.provision "shell", path: "provision.sh"
		config.vm.provider :virtualbox do |vb|
		vb.customize ["modifyvm", :id, "--memory", "256"]
	end
	# Application server 1.
	config.vm.define "app1" do |app|
		app.vm.hostname = "orc-app1.dev"
		app.vm.box = "geerlingguy/centos7"
		app.vm.network :private_network, ip: "192.168.60.4", :netmask => "255.255.0.0"
	end
	# Application server 2.
	config.vm.define "app2" do |app|
		app.vm.hostname = "orc-app2.dev"
		app.vm.box = "geerlingguy/centos7"
		app.vm.network :private_network, ip: "192.168.60.5", :netmask => "255.255.0.0"
	end
	# Database server.
	config.vm.define "db" do |db|
		db.vm.hostname = "orc-db.dev"
		db.vm.box = "geerlingguy/centos7"
		db.vm.network :private_network, ip: "192.168.60.6", :netmask => "255.255.0.0"
	end
end