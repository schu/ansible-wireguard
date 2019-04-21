# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # With "only" 512MB of memory we happen to see
  # '/tmp/vagrant-shell: line 1: 3149 Killed dnf --refresh install -y python'
  config.vm.provider "virtualbox" do |v|
    v.memory = 640
  end
  config.vm.define "node-1" do |c|
      c.vm.box = "ubuntu/bionic64"
      c.vm.provision "shell", inline: "apt-get update && apt-get install -y python"
      c.vm.provision "ansible", become: true, verbose: "v", playbook: "playbook-vagrant-test.yml"
      c.vm.network "private_network", ip: "192.168.234.55"
  end
  config.vm.define "node-2" do |c|
      c.vm.box = "fedora/29-cloud-base"
      c.vm.provision "shell", inline: "dnf install -y python"
      c.vm.provision "ansible", become: true, verbose: "v", playbook: "playbook-vagrant-test.yml"
      c.vm.network "private_network", ip: "192.168.234.66"
  end
  config.vm.define "node-3" do |c|
      c.vm.box = "debian/stretch64"
      c.vm.provision "shell", inline: "apt-get update && apt-get install -y python"
      c.vm.provision "ansible", become: true, verbose: "v", playbook: "playbook-vagrant-test.yml"
      c.vm.network "private_network", ip: "192.168.234.77"
  end
end
