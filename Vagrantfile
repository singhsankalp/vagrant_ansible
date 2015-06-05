# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/playbook.yml"
    ansible.sudo = true
    ansible.inventory_path = "provision/ansible_hosts"
  end

  config.vm.define "master" do |worker|
    worker.vm.box = "ubuntu/trusty64"
    worker.vm.network :private_network, ip: "192.168.3.25"
    worker.vm.hostname = "master"
  end

  config.vm.define "slave" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.network :private_network, ip: "192.168.3.26"
    web.vm.hostname = "slave"
  end

end
