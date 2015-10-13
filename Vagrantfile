# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.ssh.forward_agent = true

  config.vm.network "private_network", ip: "33.33.33.100"
  config.vm.network "forwarded_port", guest: 3000, host: 3001 # Rails

  config.vm.synced_folder "./api.emberchat.com", "/srv/api.emberchat.com"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = "2"
    vb.memory = "2048"
  end

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true
  # config.vm.provision "shell" do |s|
  #   s.inline = "sudo npm install -g n"
  #   s.inline = "sudo n stable"
  #   s.inline = "sudo npm install -g ember-cli"
  #   s.inline = "sudo npm install -g bower"
  # end
end
