# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "base"

    config.vm.box_url = "http://files.vagrantup.com/precise32.box"

    config.vm.provision :shell, :path => "install.sh"

    config.vm.network :private_network, {
      ip: "10.96.48.24",
    }
    
    #to access vm by localhost:8080
    #config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.provider "virtualbox" do |vb|
    vb.name = "laravel"
    
    vb.customize ["modifyvm", :id, "--accelerate3d", "off"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--vtxvpid", "off"]
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
  end
end
