# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # copied directly from vagrant init chef/centos-6.5
  config.vm.box = "bento/centos-6.7"

  # auto-update guest additions so we can ssh into the box
  config.vbguest.auto_update = true

  # change memory size
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end

  # Oracle port forwarding
  config.vm.network "forwarded_port", guest: 11521, host: 21521

  # run setup.sh
  config.vm.provision "shell", path: "setup.sh"

  # proxy
  #config.proxy.http     = "http://proxy:port"
  #config.proxy.https    = "http://proxy.port"
  #config.proxy.no_proxy = "localhost,127.0.0.1"
end
