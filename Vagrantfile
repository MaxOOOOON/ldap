# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.define "ipaserver" do |server|
      config.vm.box = 'centos/8'
    
      server.vm.host_name = 'ipaserver'
    
      server.vm.network "forwarded_port", guest: 80, host: 8081
      server.vm.network :private_network, ip: "10.0.0.20"
      server.vm.hostname = "ipa-server.otus.local"

      server.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      end
    end
    
      config.vm.define "ipaclient" do |client|
        client.vm.box = 'centos/8'
        client.vm.host_name = 'ipaclient'
        client.vm.network :private_network, ip: "10.0.0.21"
        client.vm.hostname = "ipa-client.otus.local"

        client.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        end
      end
    
      config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook.yml"
        ansible.become = "true"
      end


    end