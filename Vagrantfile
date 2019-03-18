# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  (1..3).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.box = "centos/7"
      node.vm.hostname="node#{i}"
      node.vm.network "private_network", ip: "192.168.90.1#{i}"
      node.vm.provider "virtualbox" do |v|

            # setup vm name
            v.name = "kube-node#{i}"

            # setup vm memory
            v.memory = 2048

            # setup vm cpu core num
            v.cpus = 1
        end
      # node.vm.synced_folder "/synced_folder", "/home/vagrant/share"

      node.vm.provision "shell", inline: <<-SHELL
        sudo yum update
        curl -fsSL https://get.docker.com -o get-docker.sh
        sudo sh get-docker.sh
        sudo usermod -aG docker ${USER}
        sudo systemctl start docker.service
        sudo systemctl enable docker.service
      SHELL
    end
  end
end
