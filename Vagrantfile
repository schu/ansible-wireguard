# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "node-1" do |c|
      c.vm.box = "ubuntu/xenial64"
      c.vm.provision "shell", inline: "apt-get update && apt-get install -y python"
      c.vm.provision "ansible", playbook: "playbook-vagrant-test.yml"
      c.vm.network "private_network", ip: "192.168.234.55"
  end
  config.vm.define "node-2" do |c|
      c.vm.box = "fedora/27-cloud-base"
      c.vm.provision "shell", inline: "dnf --refresh install -y python"
      c.vm.provision "ansible", playbook: "playbook-vagrant-test.yml"
      c.vm.network "private_network", ip: "192.168.234.56"
  end
end
