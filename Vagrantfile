#Author : Eko Prasetyo
#NIM : 20180801185
#Universitas Esa Unggul - Fakultas Ilmu Komputer
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
  config.vm.define "eko-loadbal" do |lb|
    lb.vm.box = "ubuntu/trusty64"
    lb.vm.network "private_network", ip: "100.100.1.10"
    lb.vm.provision "shell", path: "https://gist.githubusercontent.com/ekkoprasetyo/d570b445931caa5fa80cc1c252a077f7/raw/095afbdfda2906e30975902428003f3a04dccddf/provision-loadbal.sh"
  end

  config.vm.define "eko-web1" do |web1|
    web1.vm.box = "ubuntu/trusty64"
    web1.vm.network "private_network", ip: "100.100.1.11"
    web1.vm.provision :shell do |shell|
      shell.args = "1"
      shell.path = "https://gist.githubusercontent.com/ekkoprasetyo/166d3e635e63f1eb5dafb89ca92fddd0/raw/ca35b847f1ff7a5616c609524db62a91ac48de59/provision-web.sh"
    end
  end

  config.vm.define "eko-web2" do |web2|
    web2.vm.box = "ubuntu/trusty64"
    web2.vm.network "private_network", ip: "100.100.1.12"
    web2.vm.provision :shell do |shell|
      shell.args = "2"
      shell.path = "https://gist.githubusercontent.com/ekkoprasetyo/166d3e635e63f1eb5dafb89ca92fddd0/raw/ca35b847f1ff7a5616c609524db62a91ac48de59/provision-web.sh"
    end
  end
  
  config.vm.define "eko-mysql" do |mysql|
    mysql.vm.box = "ubuntu/trusty64"
    mysql.vm.network "private_network", ip: "100.100.1.13"
    mysql.vm.provision :shell do |shell|
      shell.args = "3"
      shell.path = "https://gist.githubusercontent.com/ekkoprasetyo/04ae58fd8c410dd6d97200d182aad636/raw/325b617ac11f6bbc89d8c1dc3cd8786ae5bb8458/provision-mysql.sh"
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
