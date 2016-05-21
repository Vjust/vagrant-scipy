# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  # config.vm.box_check_update = false
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"
  #
  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
     vb.memory = "2048"
  end
  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y build-essential python-dev python-virtualenv
     sudo apt-get install -y tmux git emacs tree
     sudo apt-get install -y libpng-dev libjpeg8-dev libfreetype6-dev
     sudo apt-get install -y tcl-dev tk-dev
     sudo apt-get install -y libblas-dev liblapack-dev gfortran
     mkdir work && cd work
     cd ~/work
     virtualenv -p python2 env
     source env/bin/activate
     pip install --upgrade ipython[all]
     pip install numpy 
     pip install pandas 
     pip install matplotlib
     pip install scipy 
  SHELL
end
