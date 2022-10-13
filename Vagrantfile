# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.box_check_update = false
  config.vm.hostname = "vm03"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.define "vm3"
  config.vm.synced_folder ".", "/vagrant", create: true
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end  
  config.vm.provider "hyperv" do |h|
    h.enable_virtualization_extensions = true
    h.linked_clone = true
	  h.memory = "1024"
	  h.cpus = 2
  end      
end