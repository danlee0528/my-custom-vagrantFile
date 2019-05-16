Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise64"
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
  # Customize the amount of memory on the VM:
     vb.memory = "1024"
  end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y git vim
     apt-get install -y golang-go haskell-platform mit-scheme swi-prolog
    
     # install python 2.7
     sudo add-apt-repository ppa:deadsnakes/ppa
     sudo apt-get update
     sudo apt-get install python2.7

     # install Remote VS code 
     sudo wget -O /usr/local/bin/rmate https://raw.github.com/aurora/rmate/master/rmate
     sudo chmod a+x /usr/local/bin/rmate
     ssh -R 52698:localhost:52698 127.0.0.1
    
     # install python-pip
     sudo apt-get install python-pip


  SHELL

  config.vm.box_check_update = true

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

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  
  # View the documentation for the provider you are using for more
  # information on available options.


end
