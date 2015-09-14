# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.7.2"

Vagrant.configure(2) do |config|

  config.ssh.insert_key = true

  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false
  config.vm.define "froide_vm"

  config.vm.network "private_network", ip: "192.168.51.51"
  config.vm.network "forwarded_port", guest: 80, host: 50000, auto_correct: true

  config.vm.provider "virtualbox" do |vm|
    vm.name = "froide_vm"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/froide.yml"
    ansible.verbose = "v"
  end
end
