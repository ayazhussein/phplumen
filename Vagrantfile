# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "web1" do |web|
    web.vm.box = "ubuntu/xenial64"
    web.vm.hostname = 'web1'

    web.vm.network "public_network"
    web.vm.synced_folder ".", "/app/work"
    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "web1"]
    end
  end
  config.vm.define "web2" do |web|
    web.vm.box = "ubuntu/xenial64"
    web.vm.hostname = 'web2'

    web.vm.network "public_network"
    web.vm.synced_folder ".", "/app/work"
    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "web2"]
    end
  end

  config.vm.provision "docker"
end
