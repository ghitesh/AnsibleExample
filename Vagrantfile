# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  
  #master1.vm.box = "centos/7"
  config.vm.box = "centos/7"
    config.vm.define "ansiblecontroller" do |ansiblecontroller|
	ansiblecontroller.vm.network "public_network", ip: "192.168.0.11",  bridge: "en1: Wi-Fi (AirPort)"
  	
  	ansiblecontroller.vm.synced_folder "/Users/hitesh389138/Vagrant/ansible/stom/", "/home/vagrant/ansible"
  	
	#master1.vm.network "private_network", ip: "192.168.33.121"
	ansiblecontroller.vm.provider "virtualbox" do |vb|
     vb.memory = "1536"
     #vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     #vb.customize ["modifyvm", :id, "--name", "bastion"]
     #vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
   end
  end
  
  config.vm.define "target1" do |target1|
  	
	#master1.vm.network "private_network", ip: "192.168.33.121"
	target1.vm.network "public_network", ip: "192.168.0.21",  bridge: "en1: Wi-Fi (AirPort)"
	target1.vm.network :forwarded_port, guest: 80, host: 4567
	target1.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
     #vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     #vb.customize ["modifyvm", :id, "--name", "bastion"]
     #vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
   end
  end
  
  config.vm.define "target2" do |target2|
  	
	#master1.vm.network "private_network", ip: "192.168.33.121"
	target2.vm.network "public_network", ip: "192.168.0.22",  bridge: "en1: Wi-Fi (AirPort)"
	target2.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
     #vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     #vb.customize ["modifyvm", :id, "--name", "bastion"]
     #vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
   end
  end
  
  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
