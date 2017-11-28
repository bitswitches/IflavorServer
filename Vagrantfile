# -*- mode: ruby -*-
# vi: set ft=ruby :

project_name = File.basename(Dir.getwd)
vagrant_static_ip = ENV["VAGRANT_STATIC_IP"] ? ENV["VAGRANT_STATIC_IP"] : "192.168.33.10"
# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "cent7.3"
  config.vm.box_download_checksum = "8e75e46d39f925ddbc073ea542b15158358ed57ed830b461d9110c0e657e6091"
  config.vm.box_download_checksum_type = "sha256"
  config.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.3/vagrant-centos-7.3.box"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: vagrant_static_ip

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder "./", "/#{project_name}"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true

    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus = 4
  end

  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "" # VAGRANT_HTTP_PROXY
    config.proxy.https    = "" # VAGRANT_HTTPS_PROXY
    config.proxy.ftp      = "" # VAGRANT_FTP_PROXY
    config.proxy.no_proxy = "" # VAGRANT_NO_PROXY = localhost,127.0.0.1
  end

  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL

  # config.vm.provision "shell", inline: <<-SHELL
  # SHELL

  # config.vm.provision "shell", run: 'always', inline: <<-SHELL
  # SHELL


  # memo: ansible-playbook -i hosts/local nginx.yml --connection=local
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "site.yml"
    ansible.install_mode = "pip"
    ansible.version = "latest"
    ansible.limit = "all"
    ansible.raw_arguments = ["--connection=local"]
    ansible.inventory_path = "hosts/local.yml"
    ansible.provisioning_path = "/#{project_name}/ansible"
    ansible.galaxy_role_file = "/#{project_name}/ansible/requirements.yml"
    ansible.galaxy_roles_path = "/#{project_name}/ansible/galaxy"
    ansible.config_file = "/#{project_name}/ansible/ansible.cfg"
  end

end
