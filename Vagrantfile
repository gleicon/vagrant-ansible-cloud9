# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "cloud9" do |cloud9|
    cloud9.vm.box = "ubuntu/trusty64"
    cloud9.vm.network :private_network, ip: "192.168.33.21"

    cloud9.vm.provision "ansible" do |ansible| 
      ansible.playbook = "cloud9.yml"
    end 
  end

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end

end
