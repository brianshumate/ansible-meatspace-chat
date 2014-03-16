# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile for bootstrapping a Meatspace Chat instance on Mac OS X with
# Vagrant provider and Ansible provisioiner on Ubuntu virtual machine

VAGRANTFILE_API_VERSION = "2"
BOX_MEM = ENV['BOX_MEM'] || "1024"
BOX_NAME =  ENV['BOX_NAME'] || "ringtail64"
BOX_URI = ENV['BOX_URI'] || "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-13.04_chef-provisionerless.box"
BOT_HOST = ENV['BOT_HOST'] || "vagrant_hosts"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define :meatspace-chat do |meatspace-chat_config|
    meatspace-chat_config.vm.box = BOX_NAME
    meatspace-chat_config.vm.box_url = BOX_URI
    meatspace-chat_config.vm.network :private_network, ip: "10.1.1.40"
    meatspace-chat_config.vm.hostname = "meatspace-chat.local"
    meatspace-chat_config.ssh.forward_agent = true
    meatspace-chat_config.vm.provider "virtualbox" do |v|
      v.name = "meatspace-chat"
      v.customize ["modifyvm", :id, "--memory", BOX_MEM]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
      v.customize ["modifyvm", :id, "--cpus", "1"]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    end
    meatspace-chat_config.vm.provision :ansible do |ansible|
      ansible.inventory_path = BOT_HOST
      ansible.playbook = "site.yml"
      ansible.limit = "all"
    end
  end
end

