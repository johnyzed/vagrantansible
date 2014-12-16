# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  
  config.vm.define "front" do |front|
    front.vm.box = "hashicorp/precise32"
    front.vm.provision "ansible" do |ansible|
        ansible.playbook = "Ansible/front.yml"
    end
    front.vm.network "private_network", ip: "192.168.10.10"
  end

  config.vm.define "back" do |back|
    back.vm.box = "hashicorp/precise32"
    back.vm.provision "ansible" do |ansible|
        ansible.playbook = "Ansible/back.yml"
    end
    back.vm.network "private_network", ip: "192.168.10.11"
  end

  config.vm.define "db" do |db|
    db.vm.box = "hashicorp/precise32"
    db.vm.provision "ansible" do |ansible|
        ansible.playbook = "Ansible/dbs.yml"
    end
    db.vm.network "private_network", ip: "192.168.10.12"
  end

  config.ssh.forward_agent = true

end
