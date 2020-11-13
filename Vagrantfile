# -*- mode: ruby -*-
# vi: set ft=ruby :

$bootstrap = <<SCRIPT
sudo apt-get update
sudo apt-get -fuy -o Dpkg::Options::='--force-confold' install git

git clone https://github.com/zardus/ctf-tools.git /home/vagrant/ctf-tools/
/home/vagrant/ctf-tools/bin/manage-tools -s setup
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu18"
  config.vm.hostname = "ctf-tools"
  config.vm.provision "shell", privileged: false, inline: $bootstrap
  config.vbguest.installer_arguments = []
  config.vm.synced_folder "~/Vagrants/sharespace", "/home/vagrant/sharespace"
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end
  config.disksize.size = "25GB"
end
