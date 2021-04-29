# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
  Vagrant.configure("2") do |config|

    config.vm.box = "generic/ubuntu2004"

    config.vm.define :devops do |machine|
        machine.vm.disk :disk, size: "10GB", name: "extra_storage"
        machine.vm.hostname = "devops"
        machine.vm.network "forwarded_port", guest: 8080, host: 7000
        machine.vm.network "forwarded_port", guest: 80, host: 7001
        machine.vm.network "private_network", ip: "192.168.99.20"
    end

    config.vm.provision :ansible do |ansible|
        #ansible.verbose = "-v"
        ansible.playbook = "playbook.yml"
        #ansible.galaxy_role_file = "requirements.yml"
        ansible.inventory_path = "inventory.yml"
       # ansible.galaxy_role_file = "requirements.yml"
        #ansible.galaxy_command = "ansible-galaxy install --role-file=%{role_file} --roles-path=%{roles_path}"
    end

#     config.vm.define "node2" do |machine|
#         machine.vm.network "forwarded_port", guest: 80, host: 8082
#         machine.vm.network "private_network", ip: "172.17.177.22"
#     end
#
#     config.vm.define "node3" do |machine|
#         machine.vm.network "forwarded_port", guest: 3306, host: 8082
#         machine.vm.network "private_network", ip: "172.17.177.23"
#     end

    config.vm.provider :virtualbox do |vb|
      vb.name = "vagrant"
      vb.gui = false
      vb.memory = "2048"
      vb.cpus = "2"
    end
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  #config.vm.box = "base"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = true

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
#   config.vm.network "forwarded_port", guest: 80, host: 8080
#   config.vm.network "forwarded_port", guest: 8080, host: 8081
#   config.vm.network "forwarded_port", guest: 8000, host: 8082
#   config.vm.network "forwarded_port", guest: 8000, host: 8083

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

end

